---
title:  "Implementing Binary Search in JavaScript"
date:   2014-12-06
summary: "This morning I worked through the binary search tutorial in the Algorithms class on Khan Academy. The concepts were familiar from when I took MIT's Introduction to Computer Science and Programming on EdX, but this time I learned to implement the algorithm in JavaScript rather than Python..."
tags: 
  - JavaScript
  - Algorithms
---
This morning I worked through the binary search tutorial in the <a title="Binary Search on Khan Academy" href="https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/" target="_blank">Algorithms</a> class on Khan Academy. The concepts were familiar from when I took MIT's Introduction to Computer Science and Programming on EdX, but this time I learned to implement the algorithm in JavaScript rather than Python.

I also learned a quick way to unit test a function in JavaScript by using Program.assertEqual():

Here's the <a title="Binary Search Algorithm code on GitHub" href="https://github.com/AbbyJonesDev/JSAlgorithms/blob/master/binary_search.js" target="_blank">code</a> for the algorithm with a few tests. (Hit the link to get the code on GitHub.)

``` js
/* Returns either the index of the location in the array,
 or -1 if the array did not contain the targetValue */
var doSearch = function(array, targetValue) {
  var min = 0;
  var max = array.length - 1;
  var guess;
  var numGuesses = 0;

  while(max <= min) {
    numGuesses ++;
    guess = Math.floor((min + max) / 2);
    if ( array[guess] === targetValue ) {
      println(numGuesses);
      return guess;
    } else if ( array[guess] < targetValue ) {
      min = guess + 1;
    } else {
      max = guess - 1;
    }
  }
  println(numGuesses);
 return -1;
};

var primes = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37,
   41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97];

var result = doSearch(primes, 73);
println("Found prime at index " + result);
// Quick tests to verify results 
Program.assertEqual(doSearch(primes, 73), 20);
Program.assertEqual(doSearch(primes, 7), 3);
Program.assertEqual(doSearch(primes, 25), -1);
```