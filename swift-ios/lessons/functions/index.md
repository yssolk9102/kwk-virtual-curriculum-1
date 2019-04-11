# Functions

## Learning Goals

* Students will be able to use function syntax to package a set of commands, including arguments and return values
* Students will be able to follow the flow of arguments throughout a function

## Technical Vocabulary

* Function
* Argument
* Return Value
* Declare
* Call (a function)
* Code Block

## What is a function?

You can think of a function as action in our code. A function has a specific job, and it sits around waiting to be asked to do it's job. It can have a very small job (add two numbers together) or a very big job (find the standard deviation of 1 million numbers). We get to write them so we have control over what their jobs are.

You may have seen these before - in JavaScript they are also called functions; in Ruby they are called methods. This is the meat of a program - without functions we can't do much.

Today, we will go through the syntax of functions in Swift, and make sure you have everything you need to start writing them! Let's pretend we have a robot who is going to help us run a dog walking service.

## Functions

Some people describe functions as 'packages of commands' - we usually group a few commands into one function. The function name should describe what it's job is. Today, we are going to write a walkDog function, which will give a set of commands to the robot to walk a dog.

```swift
func walkDog() {  

}
```

### Turn & Talk
With your partner, talk about, then write down a list of the steps in walking a dog.

Then we will create a class list of steps to walk our dog, that will eventually go into our `walkDog` function!

## Syntax

To declare a function, we start with the `func` keyword. Then, like a variable, we choose the name of the function. After the functions name, we see `()`, an opened and closed parenthesis with nothing inside (for now). Lastly, we open up a `code block` with the `{}` curly braces. All the code that we want executed with this function must live inside of the code block.

```swift
func walkDog() {
  // steps
  // go
  // here
}
```

### Practice

In an Xcode Playground, write this same `walkDog` function. Instead of `//steps //go //here` write print statements for each of the steps we wrote out on the board. Run the code. It should do ... nothing, for now.

Why don't we see our print statements? One really convenient thing about function is that they don't do their job until they are told to. We can give them a set of commands, and tell them to hang on to that information until we tell them to run. This command, telling them to run, is called **calling a function**.  The great thing about this is we can run a function multiple times! Check out the syntax to call a function:

```swift
func walkDog() {
  print("Put on leashes")
  print("walk forward")
  // etc...
}

walkDog()
```

Again, if a function is only declared, it will not do it's job. We have to call it to tell it it's time to do it's job. We can call a function as many times as you want. Add a call to your function and make sure it runs!

### Practice - Round 2

Write two more functions - one for making a bowl of cereal and the other, you pick. Each function should print out at least one statement. Verify your functions are working by calling them.

**Explore:** What happens if you call your function on line 2, then declare it on line 4?

## Arguments

If we are really going to have this robot help out, we need it to be a little 'smarter'. We need it to know that if there are two dogs, it needs to put two leashes on, bring two poops bags, etc.

We can make functions a little 'smarter' with something called **arguments**. It allows us to give a function special information. Using this information, it may make slightly different calculations or give us different outputs. Take a look at the code below, then we'll talk about what's happening:

```swift
func walkDog(numberOfDogs : Int) {
  print("There are \(numberOfDogs) dogs in the house")
}

walkDog(numberOfDogs : 4)
```

For the `walkDog` problem we've been working on, we'd like to tell the robot we have a certain number of dogs. In the examples above, we want to tell it we have 4 dogs. We have to change the code in two places to pass information to functions:
- **In the function declaration.** Notice the `()` parentheses are no longer empty, they now contain `numberOfDogs : Int`. This is telling the computer that we are expecting some information when the function is called. Specifically, we are expecting one piece of information, an integer. That integer has a variable name which we defined as `numberOfDogs`.
- **In the function call.** Notice the `()` parentheses are no longer empty, they now contain `numberOfDogs : 4`. This is telling the function that for this time it is run, we want the `numberOfDogs` to have the value of 4.

### Practice

Write a function called `hello` that takes one argument, a string. In the code block, print out "Hello, Amy" assuming that "Amy" is the string passed in as an argument.

## Return Values

We won't always just use functions to print things to the console - we'll have many functions that have different jobs, all working together to create one big program. Part of the way they do this is by **returning** a value. Return values can be any data type - strings, integers, arrays, and more. Check out this code below:

```swift
func walkDogs(numberOfDogs : Int) -> Int {

  return numberOfDogs
}

walkDogs(numberOfDogs : 3)
```

You probably observed two new things in this function:
- `-> Int` in between our parentheses and opening curly brace for the code block. This syntax indicates that we plan to return an Integer from this function.
- the `return` keyword. Up until now, we've been printing inside of functions, which is cool, but do really make powerful programs, we need to return. Over the next couple of days, you'll see the power of `return`. Keep in mind: `return` should almost always be used on the last line of the function.

### Practice

Inside your `walkDog` function, create a `lengthOfWalk` variable that multiplies the number of dogs by 15. Then on the next line, return `lengthOfWalk`. Now run the function.

Explore:
* What happens if you forget to include to `-> Int` in your function declaration?
* What happens if you forget to use the `return` keyword, when you have `-> Int` in the declaration?

## How to use Return Values

If you are wondering... This is all great - but where did that return value _go_? Who sees it? What can we do with it? ... this section is for you. Sometimes we have many functions working together. Below is a simpler example, where we take the return value of a function and use it to write a custom sentence for our robot:

```swift
func walkDog(numberOfDogs : Int) -> Int {
  var lengthOfWalk = numberOfDogs * 15
  return lengthOfWalk
}

let minutesToWalk = walkDog(numberOfDogs : 3)
print("Please walk the dogs. I will expect to see you complete that task in \(minutesToWalk) minutes!")
```

The "let" was used because minutes to walk is not changed. If you are curious, try starting with var then noticing the warning Xcode throws.

## Technical Vocabulary

* Function
* Argument
* Return Value
* Declare
* Call (a function)
* Code Block

## Practice

### Part 1: Functions

* With your partner, brainstorm another task you'd like to have this robot complete. You should agree on using the same task that way you can check in with each other throughout the lab. Once you've decided on it, share with an instructor to make sure it will work for all activities, then go to the next step
* In your notebook, write out the small steps that your robot needs to take in order to complete the task
* In your playground declare and call the function - the code block should be empty
* To make 100% sure you are calling it correctly, write a print statement into the code block and make sure that appears in your console
* Now, write a print statement for each of the commands you wrote down in your notebook. Are they all printing out as expected?

### Part 2: Arguments

* Building off of your function already written - what information could you give this function to show different situations?
* Comment out your first function, and start over. This time, your function declaration should ask for an argument. It doesn't necessarily have to be an integer like the class example!
* Finish writing your function
* Call your function - a few times, passing in different arguments each time

### Part 3: Return Values

* With your partner, decide what information you want to return out of your function. What data type is most appropriate (string, integer, etc.)?
* In the declaration, tell your function you plan to return a value
* Use the return keyword to return the desired value
* Check yourself: did you return a number like "4" or a string like "Good job!"? To make this function dynamic, we should probably be returning a _variable_ that is storing something your calculated based on the argument passed in. Look back at the class example if you are stuck on this part!
* Call your function - a few times, passing in different arguments each time. STOP!
* Before you run your code, talk with your partner - what is the expected output/return value?

### Part 4: Multiple Arguments

* What is another argument that could be passed in your function? Try it out! Not sure what the syntax looks like? You got this. Remember, strong developers are strong googlers, so feel free to look for examples online.
* Can you have more than 1 return value? How do you know?