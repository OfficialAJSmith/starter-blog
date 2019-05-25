---
title: 'This Weeks Progress #2    '
date: 2019-05-25T01:31:38.061Z
image: /images/whats-new-orig_orig.png
published: false
---
<br>
&emsp; Another week has gone by and I'm to tell you a few things I learned.      
There's not much to report but I did work on Udacity course and read some JavaScript articles on [Dev.to](https://dev.to).<br><br>
&emsp;So one of the articles I read was something that was not new to JavaScript but it was new to me. This feature known as .some( ) is used to check against an array to learn about data in an array. The example used which is at the bottom of this [article](https://dev.to/mattsparks/quick-javascript-tip-the-some-method-207j) is what I will be showing you. So lets say you want to know if a price of a certain item in the array goes above 20 dollars. Here is a bit of code to highlight my example. <br>
```
const prices = [5, 8, 11, 10, 25];
const aboveTwenty = prices.some((price) => price > 20); //check the array for prices over 20

console.log(aboveTwenty); // true ```
