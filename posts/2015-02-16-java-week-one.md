---
title:  "Java Week One"
date:   2015-02-16
summary: ""
tags:
  - Learning to Code
  - Java
---
It's been exactly one week since <a href="http://www.amazon.com/Head-First-Java-Kathy-Sierra/dp/0596009208" rel="nofollow">Head First Java</a> and <a href="http://www.amazon.com/Core-Java-I--Fundamentals-9th/dp/0137081898" rel="nofollow">Core Java</a> arrived on my doorstep. I finished reading through chapter 5 of Head First Java last night, and this morning I typed up the code for the SimpleDotComGame, compiled it, and played a quick game against the computer. I won!

Coming from Ruby, Java is a big change. I've never worked with a strongly-typed or compiled language before. It's not as scary as it looked from a distance, though. The Head First style can be a little annoying at times, but they explain concepts well, and it's been a gentle introduction to the language. To reinforce the syntax, I've been reading the code samples "out loud" (in my head) and talking myself through what the pieces do. For example:
<pre class="highlight"><code> public String checkYourself(String stringGuess) {...}
</code></pre>
<em>a public method that returns a String... The method is called checkYourself, and it takes a String argument called stringGuess...</em>

It seems strange that methods don't start with the <em>def</em> keyword, so I have to think twice to recognize a method vs. a variable declaration. Aside from the explicit type declarations, there are a lot of similarities between the syntax of Java and JavaScript. (Duh, right?) Spending more time with JavaScript recently is making Java easier to read/type.

I have <a href="https://eclipse.org/" rel="nofollow">Eclipse</a> installed, but for this first program, I just used <a href="http://www.sublimetext.com/2" rel="nofollow">Sublime Text</a> and the Terminal. I learned some cool things about the compiler:
<ul>
  <li>It provides helpful error messages with specific line numbers.</li>
  <li>It doesn't like single quotes around strings.</li>
  <li>It won't compile an existing class that references another class you haven't written yet.</li>
  <li>When both classes exist, it compiles them at the same time.</li>
</ul>
I found it interesting that I didn't have to explicitly import one class into another in order for them to work together. They just needed to be in the same directory. It's also interesting that everything in Java is wrapped in a class. Ruby and Python are both object-oriented languages, but it's possible to write scripts in a functional way without using classes. It seems like that's impossible in Java, at least in a strict sense. I kind of like that. It's stretching my thinking about object-oriented programming. The next chapter in the book is about the Java API and how to reuse existing classes in the Java library. Looking forward to it.

Many thanks to my kind friends on Twitter who recommended these books and cheered me on when I asked for suggestions to help me get started. It's amazing to be surrounded by so many great people on this journey of learning and growing as a developer.