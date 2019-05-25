---
title: 'This Weeks Progress #2    '
date: 2019-05-25T01:31:38.061Z
image: /images/whats-new-orig_orig.png
tags:
  - JavaScript
  - Dev.to
published: true
---
<br>
&emsp; Another week has gone by and I'm here to tell you a few things I learned.      
There's not much to report but I did work on a Udacity course and read some JavaScript articles on [Dev.to](https://dev.to).
<br>

&emsp;So one of the articles I read was something that was not new to JavaScript but it was new to me. This feature known as .some( ) is used to check against an array to learn about data in an array. The example used which is at the bottom of this [article](https://dev.to/mattsparks/quick-javascript-tip-the-some-method-207j) is what I will be showing you. So lets say you want to know if a price of a certain item in the array goes above 20 dollars. Here is a bit of code to highlight my example. 
<br>

```
const prices = [5, 8, 11, 10, 25]; //an array
const aboveTwenty = prices.some((price) => price > 20); //check the 
array for prices over 20

console.log(aboveTwenty); // true 

```
<br>
&emsp; Now for some insight into the [Udacaity](http://udacity.com) I am working through for JavaScript. To save us both time I will just go over one bit that stumped me a bit due to over thinking and trying to make it more complex (It's a normal trend I am trying to fix). The section was on conditionals such as if, else and else if statements. For the exercise I was suppose to write a block of code that used if, else and else if to find rather a number was odd using the modulo operation. While this should of been simple from the start I miss read an instruction which is where the trouble started. After messing around with it awhile, I decided to start over and reread the requirements to pass the quiz. And wouldn't you know, it just clicked and I got it done. Here is the bit of code I came up with.
<br>
```
var number = 5;

if (number%2 === 1) {
    console.log('odd');
}
else if(number%2 !== 1){
    console.log('even');
}
 else {
    console.log(number);
 }

```
<br>
For those wondering what the modulo function does, it finds the remainder after division. In this block of code I use strict comparing to get the logic to work. The === makes so it states that is has to be equal to be truthy or else it's falsy. That makes !== mean it has to absolutely be not equal to be truthy otherwise it's falsy. Here is a small table to help clarify it more.
<br>
```
1 == true     => true
true == true  => true
1 === true    => false
true === true => true
```
<br>
&emsp;That concludes my lessons this week and I hope you enjoy my coding information. If anything seems wrong or you would like to discuss this more hit me up on twitter [@officalajsmith](https://twitter.com/officalajsmith). 
