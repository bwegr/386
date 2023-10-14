---
layout: post
title:  "How to Create Wordle with Python"
author: Brandon Wegrowski
description: "Welcome Post to the 386 Blog - Data Science Process"
image: "/assets/code.jpg"
--- 

Wordle has become a global phenomenon, with millions of people playing it every day. Much of its enjoyment comes from its simplicity  - just guess a five-letter word. If you're a programming enthusiast, this may make it a great target for duplicating and you might find even more enjoyment by creating a Wordle game with code. In this blog post, we'll walk you through the steps involved in creating a simple Wordle game in Python.

*Disclaimer: This tutorial assumes a basic understanding of Python*

#### **Getting Started**

To get started, pull up a blank .py file in your favorite IDE.

This Wordle will be a very simple, bare-bones version, so feel free to add to it. We will only need to import the random package but feel free to import other packages like string, Theme, and Console to spice up the output in the terminal and make it actually look more like the Wordle game.

```python
import random
```

#### **Function 1**
The structure of our code takes the form of 3 functions. The first two functions will be used within the third function (the main function) which will simulate the Wordle experience for us.

Function #1 has only one line of code that will randomly choose a word from whatever list of words is passed to it.

```python
def choose_random_word(word_list):
  # Chooses a random word from the given word list
  return random.choice(word_list)

```

#### **Function 2**
Function #2 takes two inputs: a guess, and the random word (which is the correct answer the player is trying to guess). It checks to see if that guess is correct and then returns a list of five colors corresponding to the correctness of each letter in that word. As those who have played Wordle know, green indicates the letter is correct and in the correct position, yellow indicates the letter is correct but in the wrong position, and gray indicates the letter is incorrect. Thus, receiving an output of "green, green, green, green, green" indicates that your guess was the correct word.


```python
def check_guess(guess, random_word):
  colors = []
  for i in range(len(guess)):
    if guess[i] == random_word[i]:
      colors.append("green")
    elif guess[i] in random_word:
      colors.append("yellow")
    else:
      colors.append("gray")

  return colors

```

#### **Function 3**
We will now create our #3 - and final - function, which is our main function to execute the game, and actually uses the previous two functions within it. 
In this function, we define the list of words manually, but feel free to import your own list of words (the official list of words has been leaked on the internet and is available publicly). The guess is checked for length, the colors are printed, and then the game is terminated after either a correct guess or 6 incorrect guesses, whichever comes first.

```python
def main():
  """Plays a game of Wordle."""

  # Create a word list.
  word_list = ["hello", "world", "test", "wordle", "filter", "found", "wrong", "right"]

  # Choose a random word.
  random_word = choose_random_word(word_list)

  # Start the game loop.
  guesses = []
  while len(guesses) < 6:
    guess = input("Guess a word: ")

    # Check the player's guess.
    colors = check_guess(guess, random_word)

    # Add the guess to the list of guesses.
    guesses.append((guess, colors))

    # Print the colors of the squares.
    for color in colors:
      print(color, end=" ")

    print()

    # If the player guessed the word correctly, end the game.
    if guess == random_word:
      break

  # If the player runs out of guesses, end the game.
  if len(guesses) == 6:
    print("Game over! The word was " + random_word)

if __name__ == "__main__":

```

#### **Have Fun!**
Now run your code and enjoy playing Wordle, then have your friends try it and add more features to make it even better!

![image](https://github.com/bwegr/386/assets/67449500/089f7725-acf8-4521-bed8-a3f2e44b8acb)







