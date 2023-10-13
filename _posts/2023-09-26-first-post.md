---
layout: post
title:  "How to Create Wordle with Python"
author: Brandon Wegrowski
description: "Welcome Post to the 386 Blog - Data Science Process"
image: "/assets/code.jpg"
--- 

Wordle has become a global phenomenon, with millions of people playing it every day. Much of it's enjoyment comes from its simplicity  - just guess a five letter word. If you're a programming enthusiast, this may make it a great target for duplicating and you might find even more enjoyment by creating a Wordle game with code. In this blog post, we'll walk you through the steps involved in creating a simple Wordle game in Python.

*Disclaimer: This tutorial assumes a basic understanding of Python*

To get started, pull up a blank .py file in your favorite IDE.

This Wordle will be a very simple, bare-bones version, so feel free to add to it. We will only need to import the random package, but feel free to import other packages like string, Theme, and Console to spice up the output in the terminal and make it actually look more like the Wordle game

```python
import random
```

The structure of our code takes the form of 3 functions. The first two functions will be used within the third function (the main function) which will simulate the Wordle experience for us.

Function #1 has only one line of code that will randomly choose a word from whatever list of words is passed to it.

```python
def choose_random_word(word_list):
  # Chooses a random word from the given word list
  return random.choice(word_list)

```





```python
def check_guess(guess, random_word):
  # Checks the player's guess against the random word.
  # Returns a list of colors, where each color represents the correctness of the corresponding letter in the guess.

  # Green: The letter is correct and in the correct position.
  # Yellow: The letter is correct but in the wrong position.
  # Gray: The letter is incorrect.

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




```python
import random
```




```python
import random
```


My favorite department at BYU is the <a href="https:statistics.byu.edu" target="_blank">Statistics Department</a>






