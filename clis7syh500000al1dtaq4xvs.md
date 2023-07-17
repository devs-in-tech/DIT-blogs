---
title: "Learn Simple Animation Using JS"
seoTitle: "javascript animation"
seoDescription: "animation in javascript"
datePublished: Mon Jun 12 2023 02:08:09 GMT+0000 (Coordinated Universal Time)
cuid: clis7syh500000al1dtaq4xvs
slug: learn-simple-animation-using-js
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689612998664/6260128e-3ac0-4467-8e7b-5a300972796c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686493813113/e7b56384-cff5-47b8-879e-1a139241111c.png
tags: webdevelopment, javascript, animation, devsintechblogs

---

# Overview

Hello readers we are here with another blog on an interesting topic, you will learn how to make a simple animation using one of the most popular programming languages of all time "JavaScript". Animation makes a lot of difference in designing any website of our choice.

Through this, you will get a basic understanding of how to animate HTML elements.

# What is animation?

![Question Mark GIFs | Tenor](https://media.tenor.com/tkYDskXjHbYAAAAC/question-mark-animation.gif align="center")

As for flow let's spend some time on what is animation.

There are plenty of definitions for this but here we go

> **The art of making inanimate objects appear to move**.

In simple language, we are making the element/objects appear to move.

But again making complex animation is quite hard just by using only programming languages.

So, in this blog, we are only focusing on getting you an overview understanding of animation. Let's dive !!

# Slide an Element

In this section, we will learn how to slide an element. For this, we will imagine like after clicking the button we want to slide the element in any one of the directions(UP, DOWN, LEFT, RIGHT)

First design a button and a div element the purpose of these two elements is after clicking the button the div element has to slide any one of the directions accordingly.

```xml
<button id="myButton">Right</button>
<div id="myDiv"></div>
```

We named the button Right for explanatory purposes we are trying to slide the div element to the right side. Style the div element of your choice.

The final result will be.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686225875035/9d675a46-442a-46f4-9c0e-ee6de318b5d9.png align="center")

Here is the most important part of the animation.

First, we have to select these two elements by using any one of the element selector ways.

[Types of Element selector in JS](https://malavibolg.hashnode.dev/element-selector)

```javascript
let myButton = document.getElementById("myButton");
let myDiv = document.getElementById("myDiv");
```

Our main aim is we need to slide the div after clicking the button. For this, we need to add the event listener to the button. It can be done as shown below.

```javascript
myButton.addEventListener("click", myAnimation)
//it was telling that after clicking the button it will invoke a function called myAnimation
```

Let's have a break and just understand one of the important methods which is also the heart of animation.

## setInterval() method

It is a method used to call a function repeatedly call a function or execute a code snippet, with a fixed time delay between each call. It returns an interval ID

> syntax: setInterval ( callBackFunction/expression, delay)

```javascript
function myAnimation(){
    let timeId = null 
    let x = 0
    let y = 0
    
    timeId = setInterval(frame, 5)
    function frame(){
        if (x >= 50){
            clearInterval(timeId)
        }
        else{
            x +=1
            myDiv.style.left = x + "px"  
        
        }
    }
}
```

In the below if condition we are telling that if the x-axis of the element exceeds the 50px we are telling the stop moving the slide by using the clearInterval( ) method

```javascript
if (x >= 50){
    clearInterval(timeId)
}
```

Otherwise, we are telling you to update the x-axis by a single pixel ahead. One more thing updating how many pixels for every 5 milli second is our choice.

```javascript
else{
    x +=1 
    myDiv.style.left = x + "px"  
}
```

Here is the great catch think about it.

Great! let me tell you to slide the element to the right side we are styling the div element with the "LEFT" position property.

If you know the answer I am super happy to discuss it with you in the chat! Have a nice discussion &lt;3

So, if you want to move the element diagonally do change both x & y axes.

```javascript
else{
    x +=1
    y +=1
    myDiv.style.left = x + "px"  
    myDiv.style.top = y + "px"
}
//move the div element diagonally
```

# Rotate an Element.

In this section, we will look into how to rotate an element.

In general, rotation involves degrees right!? The same thing is true for JS element rotation.

In simple terms, it is the same as sliding but instead, we use only degrees. The code snippet looks like this.

```javascript
function myAnimation(){
    let timeId = null 
    let degrees = 0
    timeId = setInterval(frame, 5)
    console.log(timeId)
    function frame(){
        if (degrees >=360){
            clearInterval(timeId)
        }
        else{
            degrees +=1
            myDiv.style.transform = "rotateX("+degrees+"deg)"
        }
    }
}
```

The if condition states that we need to rotate the element to the full 360 degrees. Again we can even change degrees accordingly.

```javascript
 if (degrees >=360){
            clearInterval(timeId)
 }
```

Else condition has one of the weird syntaxes but never mind it is supposed to have like that only.

```javascript
else{
    degrees +=1
    myDiv.style.transform = "rotateX("+degrees+"deg)"
}
```

This is how we can rotate the element.

> To get a better understanding of the things I stated above do play around the element by changing the values and adding the new element.
> 
> **Experimenting is one of the best ways to learn and get a grip on the concept.**

# Scaling an Element.

In simple words scaling is nothing but we are trying to increase or decrease the element in a predefined size. Although the syntax looks similar to the previous two with a little bit of difference.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686362815039/4864449d-01ce-4988-9545-17eb7b93feb4.png align="center")

***<mark>Before scaling the element</mark>***

```javascript
function myAnimation(){
    let timeId = null 
    let scaleX = 1
    let scaleY = 1
    
    timeId = setInterval(frame, 5)
    console.log(timeId)
    function frame(){
        if (scaleX >2 ){
            clearInterval(timeId)
        }
        else{
            scaleX +=0.01
            myDiv.style.transform = "scale("+scaleX+","+scaleY+")"
        }
    }
}
```

In the below if condition scaleX&gt; 2 means we want to scale the element along the x-axis until it reaches 200 %

```javascript
if (scaleX >2 ){
            clearInterval(timeId)
}
```

Otherwise, we are increasing the size of the element by one percent for every 5 milliseconds.

```javascript
else{
    scaleX +=0.01
    myDiv.style.transform = "scale("+scaleX+","+scaleY+")"
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686362856390/2b0f738a-919f-4322-9766-1990a919c0e2.png align="center")

***<mark>After scaling the element</mark>***

# Play Around

As of now, these are the 3 basic animations in JavaScript my small advice would just be to mix all these things and try to create another weird animation to see what will happen.

I am telling you this is the best way to get a better understanding of the things we are currently learning.

![Children-playing GIFs - Get the best GIF on GIPHY](https://media0.giphy.com/media/cMALqIjmb7ygw/giphy.gif align="center")

# Wind-up

That's it about the blog hope you learn and get to know something new from my blog. If you like the blog and want content like this please follow the DevinTech community and be involved in our amazing community we are thrilled to be a part of your journey.

Discord -[DevsInTech](https://discord.gg/hj3vTyr8G5)

Twitter - [DevsInTech](https://twitter.com/devs_in_tech)

If you want to make the connection with the writer of the content here you GO.

Twitter - [Malavi Pande](https://twitter.com/molavi_418)