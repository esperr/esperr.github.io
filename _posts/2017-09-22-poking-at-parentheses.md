---
layout: post
title:  "Poking at Parentheses"
date:   2017-09-22
categories: programming
---
Software Projects are sometimes 99% done, but they're rarely completely finished. This is particularly true when the process of developing something new causes you to go back and reevaluate earlier design decisions.

The first iteration of [PubVenn](https://pubvenn.appspot.com/) was geared towards maximizing the number of possible terms for any simple search (in order to maximize the number of pretty circles that could be drawn). To this end, it cheerfully ignored such details as parentheses. So any search along the lines of

>  ((heart disease OR stroke) AND sodium) AND (diet OR food)

would search every single term. So the five individual parts of our search would be "heart disease", "stroke", "sodium", "diet" and "food".

A little more than a year ago, a helpful correspondent noted that more complex PubMed searches often involve parentheses, so it might be nice for PubVenn to reflect that fact. After some careful thought (and much perusal of code snippets on [Stack Overflow](https://stackoverflow.com/)), I landed on the following:
~~~~
termsarray = [];
while ((term.lastIndexOf("(")) > -1) {
      var n = term.lastIndexOf("(");
      for(var i=n; i < term.length; i++){
      	if(term.charAt(i) == ')'){
          parenTerm = term.substring(n+1,i);
          termsarray.push(parenTerm);
          termPartone = term.substring(0,n);
          termParttwo = term.substring(i+1);
          term = termPartone + termParttwo;
          console.log(term);
        }
      }
    }
~~~~
(*note*: All code adheres to the [XKCD Code Quality Guidelines](https://xkcd.com/1513/))


This of course finds the last iteration of a "(" in the string, counts along until it finds a matching ")", and snips the stuff in-between (and then repeats the process with the next "(" until it can't find any more). So our example

>  ((heart disease OR stroke) AND sodium) AND (diet OR food)

...becomes a search for the three pieces: "heart disease OR stroke", "sodium" and "diet OR food".

This does a better job of representing parentheses in a search, and *almost* matches the behavior of a PubMed search. And so for a while, that was plenty good enough.

Sharp-eyed observers will note however, that this isn't quite right. "Sodium" should be searched together with "heart disease OR stroke" instead of hanging out by itself. When developing [Search Workbench](https://searchworkbench.info/), I realized that if I was going to reuse the logic for PubVenn to show comparisons between searches, I would have to reckon with figuring out nested parentheses.

We could think about doing basically the same thing as above, but making sure that instead of blindly snipping *anything* between two parentheses, we are careful to count along and not actually cut until we have an even number of them on each side of the string we're snipping:
~~~~
termsarray = [];
findParens(term);
function findParens() {
if ((term.lastIndexOf(")")) > -1) {
  var n = term.indexOf("(");
  for(var i=n; i < term.length; i++){
    if(term.charAt(i) == '(') { parensdex+=1 }
    if(term.charAt(i) == ')') { parensdex-=1 }
    if( parensdex == 0 && /\(/g.test(term) ) {
      parenTerm = term.slice(n,i+1);
      termsarray.push(parenTerm);
      termPartone = term.slice(0,n);
      termParttwo = term.slice(i+1);
      term = termPartone + termParttwo;
      findParens(term);
    }
  }
  } else { return; }
}
~~~~

In this way, we finally end up with "(heart disease OR stroke) AND sodium" and "diet OR food". Having searches behave this way means that it would be easy to wrap an entire search in a set of parentheses if we wanted to compare it as a unit with another search. But that is a matter for another post...
