## Concepts of Functional Programming in Javascrip

### What is functional programming?
![](https://www.hexacta.com/wp-content/uploads/2015/11/Functional-programming.jpg)

***Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia***

### What is a pure function and how do we know if something is a pure function?

![](https://cdn-images-1.medium.com/max/1600/0*a_yub2gTwY-1eK8j.png)

***The first fundamental concept we learn when we want to understand functional programming is pure functions.***

 ***But what does that really mean? What makes a function pure? So how do we know if a function is pure or not? Here is a very strict definition of purity: It returns the same result if given the same arguments (it is also referred as deterministic) It does not cause any observable side effects It returns the same result if given the same arguments***

 ### What are the benefits of a pure function?
 
 ***The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:***

***`Given a parameter A → expect the function to return value B`***

***`Given a parameter C → expect the function to return value D`***

***A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.***

### What is Immutability?

 ***Unchanging over time or unable to be changed***

### what is Referential transparency?

 ***Passing 2 as a parameter of the square function will always returns 4. So now we can replace the square(2) with 4. That's it! Our function is referentially transparent.***

 `pure functions + immutable data = referential transparency`




