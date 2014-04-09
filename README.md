# Intro to JavaScript

Today we're going to learn JavaScript! You've used
[Scratch](http://scratch.mit.edu), [Blockly](https://code.google.com/p/blockly/)
or completed some lessons on [Code.org](learn.code.org/hoc/1), and now it's time
to move beyond that. We'll review the concepts demonstrated in editors like
Scratch and then start writing **actual** code in JavaScript.

Topics we'll be covering:

* Functions: what are they? how do we use them?
* Variables: how do we store things? what are variables used for?
* Control statements (if, else, while): how can we use these to write complex programs?

## Let's review block puzzles!

Before we write any code, let's review what we've learned previously. We're
going to look at some simple puzzles on Code.org. Go this  [this
link](http://learn.code.org/s/1/level/2) in your browser. In order to solve
these puzzles, we need to drag the “blocks” from our toolbox out into our
workspace, and combine pieces to get our red Angry Bird to the green Pig. Are
there any of you who know how to solve this problem and want to come up and
demonstrate for the rest of us?

Let's take a few minutes now and go through a few more of these puzzles, and
then we're going to talk about how these work. If you've done these puzzles
before, go ahead and jump to [some harder
puzzles](http://learn.code.org/s/1/level/24). 

Ok, stop on whatever puzzle you made it to, and let's chat for a minute. Notice
the link at the top right of your puzzle, in the purple area, that says “Show
Code”? Go ahead and click that. What we're looking at here is the actual code,
JavaScript, that makes our Angry Bird move. Here's what mine looks like for
Puzzle 5:

```javascript
moveForward();
turnLeft();
moveForward();
turnRight();
moveForward();
```

These lines of code are calling out to other parts of our program and saying
things like "move the Angry Bird forward" or "turn the Angry Bird to the right".
These “other parts of our program”, does anybody know what they're called? 

*Functions*! Functions are one of the most basic, but most **important**
*concepts in programming.

We're going to talk more about functions in a bit, but *first* we're going to
write our first program in JavaScript: a game!

## Getting Started

Open up your preferred browser and go to [JS Bin](http://jsbin.com/). Click at
the top-left where it says "Bins" and then choose "New" to give us a blank
canvas.

![](http://cl.ly/image/3V1M3C0k2w3c/Image%202014-04-08%20at%209.48.32%20AM.png)

At the top, in the center, we're also going to make sure that "JavaScript" and
"Console" are the only tabs highlighted blue. Once you have the correct ones
selected you should see your screen divided into two parts: "JavaScript" on the
left and "Console" on the right. We're ready to write some code!

![](http://cl.ly/image/46282v3m0o2b/Image%202014-04-08%20at%209.52.27%20AM.png)

We're going to learn the basics of JavaScript by writing a very simple game. Who
here has played Rock, Paper, Scissors before? Probably almost all of you, right?
Well today we're going to write a program that allows us to play Rock, Paper,
Scissors against the computer.

Let's start out by asking the player if they want to play. With
JavaScript we can ask the user something using “prompt“. On the left side of our
screen, let's add the following:

```javascript
prompt("Would you like to play Rock, Paper, Scissors?")
```

Now, let's run our program.

> **To run your program:** On your keyboard press Command+Enter, or click the
> “Run” button near the top-right of the screen.

As you saw, `prompt` allowed us to ask the player the answer to a question, but
right now nothing happens! Somehow we want to be able to capture the player's
answer and do something with it. In order to do this, we're going to need to
learn about something called…

## Variables!

In programming, variables let us store things: words, sentences, one number,
even a *thousand* numbers. When we create variables we give them a name,
something that makes sense to us. The name of a variable can be just about
anything, but you might have *many* variables in one program, so it's helpful to
name them well so that when you see them later, you know what they're used for.

Let's create our first variable to store the player's response to “Do you want
to play a game?” In JavaScript we define variables with `var` (like
**var**iable), followed by the name of our variable, and then a `=` symbol.
After the `=`, we type in whatever we want to store in that variable!

In our program, let's create our first variable, I'm going to call mine
`readyToPlay`, and in the variable I'm going to store the result of our
`prompt`.

```javascript
var readyToPlay = prompt("Would you like to play Rock, Paper, Scissors?")
```

To make sure that we're storing the player's response correctly, we can show the
content of our `readyToPlay` variable in the console. I'm going to add another
line to my program, so now it looks like this:

```javascript
var readyToPlay = prompt("Would you like to play Rock, Paper, Scissors?")

console.log(readyToPlay)
```

> `console.log` will take a variable and display it on the right side of our 
> screen in the “console” area. So if I run my program and answer the question 
> like this…
> 
> ![](http://cl.ly/image/2m2f2o3e3Q2O/Image%202014-04-08%20at%209.30.45%20AM.png)
> 
> …what do you think is going to be shown in the console?

Now that we have the user's response, we have to *do* something with it. Which
means it's time to learn about…

## `if` statements!

*Decisions*. We make them all day. Some of you might have chosen what to wear
this morning, or what to eat for breakfast. In programming we can make simple
decisions using `if` statements. That is to say: **if** something is true, we
will take a certain course of action.

In our game we want to display a message to the player depending on how they
answer our question. Let's add some code to our program.

```javascript
var readyToPlay = prompt("Would you like to play Rock, Paper, Scissors?")

if (readyToPlay === "yes") {
	console.log("Get ready!")
}
```

We've added an `if` statement to check whether our variable, `readyToPlay`, is
*equal to* `"yes"`. If it is, we use `console.log` to tell the player “Get
ready!”

Notice how in order to check if `readyToPlay` and `"yes"` were equal we used *three*
equal signs, instead of one like we did when storing our variable? In
programming, *one* equals sign is used for storing things, but *three*
equals signs are used for *comparing* things.

Now that we know if the player wants to play, let's add to our game. To do this,
we're going to learn about something else, something we mentioned earlier.

## Functions!

Ok, I have a question for everybody: who knows what a “verb” is? Who can give me
an example of a verb?

It can help to think of “functions” in programming as verbs, because they represent
*actions*. When we use a function, we're telling our program to do something.
We all, as humans, have our own set of functions too. Who here knows how to ride
a bike? In programming, we might write that like this:

```javascript
rideBike()
```

Or, how about Minecraft? Does anybody here play Minecraft? So you all have a 
function that looks like this:

```javascript
playMinecraft()
```

It's easy to spot functions in our program because they have two parentheses
after their name, like this: `()`. Those parentheses also let us hand off values
to functions that the function can use to run. For example, if you wanted to 
play Minecraft for 60 minutes, you might pass `60` to your function like this:

```javascript
playMinecraft(60)
```

The code here is only piece of the puzzle though. What we're doing here is
running our functions. When we run a function in programming, we say that
we're *calling* it. The other piece is the function itself! Let's write one.

In our program, we're going to add a function that we will *call* to start our
game. First, let's modify our program to call the function when the player
has told us that they want to play.

```javascript
var readyToPlay = prompt("Would you like to play a game?")

if (readyToPlay === "yes") {
  play()
}
```

Go ahead and run your program, and what happens in the console on the right?
What does it say in red after “ReferenceError”? That's because we haven't yet
*defined* our function. In other words, we haven't taught our program how to
perform the “start” action. Time to write the function!

At the top of our program, let's add this:

```javascript
function play () {
  console.log("Get ready!")
}
```

Now when we run our program and answer “yes”, what happens in the console?

Now that we've written a function of our own, you might have noticed that we 
were *already* using some functions in our program, but I just wasn't calling
them that. For example, `console.log` is a function, and so is `prompt`. These
are functions that are given to us by the browser, so we didn't have to write
them ourselves.

## Using built-in browser functions

Ok, so the next thing we want to do in our game is ask the player to choose
between three options: "Rock", "Paper", or "Scissors". Does anybody see a way
that we can do this that we've already learned?

If you were thinking of using `prompt`, that's right! In the `play` function
we created, let's ask the user, and store their response in a variable, just
like we did before.

```javascript
function play () {
	console.log("Get ready!")
	
	var playerChoice = prompt("Rock, paper, or scissors?")
}
```

After that, we need to have the computer choose as well, and we're going to do
that with the help of one of those functions provided to us by the browser.

The function `Math.random()` will generate a random number between 0 and 1. With
that in mind, does anybody have any ideas about how we could use that random
number to simulate the computer making a choice?

First, let's add to our `play` function. We're going to create another variable
and assign to it a random number using the function I mentioned above. I'm also
using `console.log` to output the number that we generate. After you add the
new piece to our program, run it, and look at what gets printed in the console.

```javascript
function play () {
	console.log("Get ready!")
	
	var playerChoice = prompt("Rock, paper, or scissors?")
	var computerChoice = Math.random()
	
	console.log(computerChoice)
}
```

## `if/else` statements

In order to simulate a choice by the computer, we're going to use another `if`
statement, but we need to use a slightly different one. In addition to saying
*if something is true then do this thing*, we can also say *if something is
true then do this thing, but **otherwise** do this other thing*. In programming
we call this an `if/else` statement. We can also use multiple `if` blocks with
`else if`.

In order to have the computer choose "rock", "paper" or "scissors", we're going
to say this:

* **IF** the random number is less than 0.33, the choice is "rock"
* **ELSE IF** the random number is less than 0.66, the choice is "paper"
* **ELSE** the choice is "scissors"

Since our random number is between 0 and 1, we're dividing the largest possible
number, 1, into three equal parts of approximately 0.33. Depending on what
*range* the generated number is in, we can say that, for example, anything *less*
than 0.33 is equal to "rock", anything *greater* than 0.33 but *less* than 0.66
is equal to "paper", and anything *greater* than 0.66 is "scissors".

Let's add this code to our program:

```javascript
function play () {
	console.log("Get ready!")
	
	var playerChoice = prompt("Rock, paper, or scissors?")
	var computerChoice = Math.random()
	
	if (computerChoice < 0.33) {
		computerChoice = 'rock'
	} else if (computerChoice < 0.66) {
		computerChoice = 'paper'
	} else {
		computerChoice = 'scissors'
	}
	
	console.log(computerChoice)
}
```

Depending on the value of `computerChoice`, we're changing the value of the
variable to either "rock", "paper" or "scissors". Run your program again and
see what gets printed in the console. What did the computer choose?

## Determining the winner

Ok, so we're really close, right? The player has chosen an option, and we had
the computer choose as well using random numbers. The last step is to *compare*
the two choices and see who won! In order to do this we're going to write
another function.

Remember earlier when I gave the example of a function called `playMinecraft`
and showed how we could pass a number to it, like `playMinecraft(60)`? This
is what we call `passing arguments` in JavaScript. We're going to write a
function that will compare the two choices, the player's choice and the
computer's choice, and we're going to *pass* those choices to the function.

We'll start by *calling* the function from `play`:

```javascript
function play () {
	console.log("Get ready!")
	
	var playerChoice = prompt("Rock, paper, or scissors?")
	var computerChoice = Math.random()
	
	if (computerChoice < 0.33) {
		computerChoice = 'rock'
	} else if (computerChoice < 0.66) {
		computerChoice = 'paper'
	} else {
		computerChoice = 'scissors'
	}
	
	compare(playerChoice, computerChoice)
}
```

We added the line at the bottom, a call to a function called `compare`. We're
passing our two variables to the function, inside the parentheses. This is
just like how when we call `console.log` we pass in some words to print to
the console.

Now let's write our function. We'll add this under our `play` function, *outside*
of the curly braces.

```javascript
function compare (choice1, choice2) {
	
}
```

When we pass arguments into a function, we can name them whatever we want
inside of the function. In our function above, even though *we* know that 
`choice1` is the player's choice and `choice2` is the computer's choice, the
function doesn't care which one is which, it will just compare the two and tell
us the winner.

Before we check for a winner, let's check for a tie.

```javascript
function compare (choice1, choice2) {
	if (choice1 === choice2) {
		return "It's a tie!"
	}
}
```

`return`? What is this? Ok, so remember how when we call `prompt` or
`Math.random` we are able to assign the result to a variable? That's because
those functions *return* a value. When a function *returns* a value, it doesn't
care what that value is used for, only that it's giving back a result of some
kind. It's up to us to use that value for something useful.

Ok, who can explain to everybody the rules of Rock, Paper, Scissors? How do
you figure out who won?

We're going to write all of those rules out as code, and we're going to need
to use everything we've learned so far. I'm going to give you a hint, but then
we're going to work through them on our own.

First, we'll look at the value of `choice1`, and then compare it to `choice2`
to figure out which of the choices won. In order to do this, we'll need to use
*nested* `if/else` statements. Here's how we would start this:

```javascript
function compare (choice1, choice2) {
	if (choice1 === choice2) {
		return "It's a tie!"
	}
	
	if (choice1 === "rock") {
		if (choice2 === "paper") {
			return "Rock won!"
		} else {
			return "Scissors won!"
		}
	} else if () {
		// What goes here?
	} else {
		// What goes here?
	}
}
```

In the first part of our `if/else` statement we're saying that *when* `choice1`
is "rock" we also want to check the value of `choice2`. So if `choice1` is
"rock", who can tell us the two possible values of `choice2`?

One thing to note: when a function *returns* a value, it doesn't run any code
that comes after the return. So, at the beginning of our function when we check
for a tie, if the choices match each other and we return, our `if` statement
under that will not run. By the time we get to our second `if` statement we
already know that the choices can't be equal to one another.

Since know that, in the first part of our `else if` statement, `choice2` can
only be "paper" or "scissors", we can figure out which choice won by nesting
an if statement. If `choice1` is "rock" and `choice2` is "paper", then we return
"Rock won!". *Otherwise* we return "Scissors won!" because it is the only other
possible option.

We're going to take some time and work on the rest of this ourselves and in a
bit we'll add some improvements to our game. Make sure to ask mentors for help
if you get stuck!

## Remaining

- Improvements
  - logging out the two choices and the winner
	- clear console at start (`console.clear()`)
