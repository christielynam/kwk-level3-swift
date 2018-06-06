footer: KWK Swift/iOS: Data Types and Variables
slidenumbers: true

# Data Types and Variables

---

# Learning Goals

* Students will be able to differentiate strings, integers, floats and doubles.
* Students will be able to create and modify variables

---

# Strings

* A string is a series of characters.

* In every day words, it's just a bunch of text. This includes letters, numbers, and symboles. We are able to tell when something is a string because it's in between two quotation marks.

* For example, `"Hello, world."` is a string. `"puppies"`. is also a string. And so is `"1234"`. 

---

# Numbers

* First we had text, and now we have numbers. But we have to think about numbers slightly differently in Swift. Which is hard. It's natural to think, "What do you mean I have to think about numbers different? They're like, _numbers_. I know how numbers work."

* In the most simple terms possible, we have two kinds of numbers, Integers and Doubles.

---

# Integers

Integers are what we would think of as whole numbers. They can be positive or negative or zero. So, 1, 3, 4, -56 and 0 are all integers. The official definition of an integer is that it is a whole number that has no fractional compinent. So what about numbers that do have a fractional component...

---

# Float and Double

* Swift gives you two data types with which to store numbers that have a fractional component, which we can refer to as numbers with decimals. They can be positive or negative. 

* Examples would be 1.1, 42.45, 3.14, -123786234.64 and so forth. 

* The TL;DR is that Doubles have more accuracy than Floats, and you get to choose how much accuracy you want - how many decimal places you can use if you want.  

*Use Double because you'll just get more accuracy that way.

---

# Turn and Talk

* Turn to a new best friend and explain the difference between an Integer and a Float and Double

---

# Variables

* So now that we know a few data types, we want to talk about how we can work with them. And we use variables for that.

* Variables are these things that we use in order to reference and label information that we're going to use in our programs. 

* But why should we use variables? First they're kind of a shortcut. Let's say we were working with our address and it's a string, "1313 Mockingbird Lane" it would be annoying to have to type that in every time we wanted to use it. 

---

# Variables

```
var address = "1313 Mockingbird Lane"
```

* What we've done in that line of code above is told the computer, "Hey, I want you to create a variable called address, and I want you to store in it the string, "1313 Mockingbird Lane". 

---

# Variables

```
var address = "1313 Mockingbird Lane"
```

* We use the `var` keyword here to tell the computer that in this following bit of code, we are going to declare a variable. We have to declare variables before we use them. 

---

# Variables 

* After we declare a variable, we can change the contents of the variable at will. If we were to move from 1313 Mockingbird Lane to 254 Ocean Avenue, we would do this:

```
address = "254 Ocean Avenue"
```

---

# Turn and Talk

With your new best friend, can you come up with some other variables and the sorts of things they might hold? Try to come up with variables that would be both numbers and text!	