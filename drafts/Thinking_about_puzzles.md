---
title: Thinking about puzzles
layout: singlePost
comments: true
---

I've been thinking about puzzle games, how to create them in a way that is both sustainable and fun. Sustainable in this case is 
having a method of creating new puzzles without spending too much time on it. Fun is a lot more open concept.

There is a myriad of puzzle types, there are puzzles in form of questions, pieces on a board, colors, lines and many many more.

Puzzles that are play on words, or out of the box puzzles (the ones that usually stretch and exploit definitions) are not easy to be 
made into a program given the evaluation of the solutions are too open.

Since my endgoal is to make puzzles for smartphones, I decided to focus on the puzzles that can be easily verified by an algorithm.

For this, I am trying to come up with common characteristics between puzzles and a method to grow puzzles organically from a starting idea.

This is what I came up with.

## Define a statefull scenario

## Define state transitions

both directions(do undo)

## Define a final state

Define a statefull scenario
Define state transitions, both directions(do undo) 
Define a final state

Ex

States 1,0
Transition flip
Transition undo flip
Final state
00
Shuffled
10
Solution
Flip first
00

State 1,0
Trasintion move up down left right
Transition undo move up down left right
Final state
00
01
Shuffled
10
00

Second is more fun because first can be solved with a single transition

Puzzle parameters 

Possible final states
Possible transitions
Amount of state changed with transition
Possible transitions after transition
the interface - purposefully bad or good

To be relatable:
- Must be intuitive or a cycle
- Usually analogous to reality

Easy puzzle
Many final states accepted
Only few transitions possible
Transition changes a single item
Possible transition includes undo

Hard puzzle
One final state accepted
Many transitions possible
Each transition changes the whole state
Undo not possible with a single transition or at all

To be fun
Teach a new mechanic
Subvert a learned mechanic
Appear easy but be hard in practice
Having a symmetric answer 
Having an unexpected solution


An example from easy to hard

Using any operation go from zero to over 1000
0
+1001
Limiting transition
Cannot use sum
(0^0)*5000
Limit solution
Odd number bigger than 1000 smaller than 1010
And so on
Unintuitive solution
Use only subtraction
0--1003