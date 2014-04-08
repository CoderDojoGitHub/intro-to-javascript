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

We're going to learn the basics of JavaScript by writing a very simple game.
Let's start out by asking the player if they want to play. With
JavaScript we can ask the user something using “prompt“. On the left side of our
screen, let's add the following:

```javascript
prompt("Would you like to play a game?")
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
var readyToPlay = prompt("Would you like to play a game?")
```

To make sure that we're storing the player's response correctly, we can show the
content of our `readyToPlay` variable in the console. I'm going to add another
line to my program, so now it looks like this:

```javascript
var readyToPlay = prompt("Would you like to play a game?")

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
will do one thing, but if it's **not** true, we will do something
else.

In our game we want to display a message to the player depending on how they
answer our question. Let's add some code to our program.

```javascript
var readyToPlay = prompt("Would you like to play a game?")

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
  console.log("Get ready!")
  start()
}
```

Go ahead and run your program, and what happens in the console on the right?
What does it say in red after “ReferenceError”? That's because we haven't yet
*defined* our function. In other words, we haven't taught our program how to
perform the “start” action. Time to write the function!

At the top of our program, let's add this:

```javascript
function start () {
  console.log("It's time to play Rock, Paper, Scissors!")
}
```

Now when we run our program and answer “yes”, what happens in the console?

## Outline (still to write)

- Rock, Paper, Scissors (is the game we're building)
- Comparison in `if` statements: `if (choice < 0.3) { }`
- if/else if/else statements
