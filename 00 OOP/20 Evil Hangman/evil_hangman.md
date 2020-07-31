# Evil Hangman

## tl;dr

Implement a program that allows someone to play Evil Hangman against the computer.

	$ python hangman.py
	WELCOME TO EVIL HANGMAN >=)
	I have a word in my mind of 8 letters.
	Guess a letter: a
	That's not in the word >=)
	Guess a letter: n
	It's in the word :(
	_____N__
	Guess a letter: ...

## Background

It's hard to write computer programs that are able to play games. When we as humans sit down to play a game, we can draw on past experience, adapt to our opponents' strategies, and learn from our mistakes. Computers, on the other hand, blindly follow a preset algorithm that (hopefully) causes them to act somewhat intelligently. Though computers have bested their human masters in some games, most notably chess and go, the programs that do so often draw on hundreds of years of human game experience and use extraordinarily complex algorithms and optimizations to out-calculate their opponents.

While there are many viable strategies for building competitive computer game programs, there is one approach that has been fairly neglected in modern research --- _cheating_. Why spend all the effort trying to teach a computer the nuances of strategy when you can simply write a program to play dirty and win handily all the time? In this assignment, you will build a mischievous program that bends the rules of Hangman to trounce its human opponent time and time again. In doing so, you'll cement your skills with abstract data types and iterators, and will hone your general programming savvy. Plus, you'll end up with a piece of software which will be highly entertaining. At least, from your perspective.

Fundamental to the game is the fact the first player accurately represents the word she has chosen. That way, when the other players guess letters, they can reveal whether that letter is in the word. But what happens if the first player doesn't do this? This gives the player who chooses the hidden word an enormous advantage. For example, suppose that you're the player trying to guess the word, and at some point you end up revealing letters until you arrive at this point with only one guess remaining:

	DO–BLE

There are only two words in the English language that match this pattern: "doable" and "double." If the player who chose the hidden word is playing fairly, then you have a fifty-fifty chance of winning this game if you guess 'A' or 'U' as the missing letter. However, if your opponent is cheating and hasn't actually committed to either word, then there is no possible way you can win this game. No matter what letter you guess, your opponent can claim that they had picked the other word, and you will lose the game. That is, if you guess that the word is "doable," they can pretend that they had committed to "double" the whole time, and vice-versa.

## Example

Let's illustrate this technique with an example. Suppose that you are playing Hangman and it's your turn to choose a word, which we'll assume is of length four. Rather than committing to a secret word, you instead compile a list of every four-letter word in the English language. For simplicity, let's assume that English only has a few four-letter words, all of which are reprinted here:

	ALLY  BETA  COOL  DEAL  ELSE  FLEW  GOOD  HOPE  IBEX

Now, suppose that your opponent guesses the letter 'E.' You now need to tell your opponent which letters in the word you've "picked" are E's. Of course, you haven't picked a word, and so you have multiple options about where you reveal the E's. If you'll notice, every word in your word list falls into one of five "word families":

- `----`, which contains the word `ALLY`, `COOL`, and `GOOD`.
- `-E--`, containing `BETA` and `DEAL`.
- `--E-`, containing `FLEW` and `IBEX`.
- `E--E`, containing `ELSE`.
- `---E`, containing `HOPE`.

Since the letters you reveal have to correspond to some word in your word list, you can choose to reveal any one of the above five patterns. There are many ways to pick which pattern to reveal – perhaps you want to steer your opponent toward a smaller family with more obscure words, or toward a larger family in the hopes of keeping your options open. In this assignment, in the interests of simplicity, we'll instruct you on the latter approach and always choose the largest of the remaining word families. You are free to take another more complicated approach later, but try this one first. In this case, it means that you should pick the pattern `----`. This reduces your word list down to:

	ALLY  COOL  GOOD

and since you didn't reveal any letters, you would tell your opponent that their guess was wrong.

Let's see a few more examples of this strategy. Given this three-word word list, if your opponent guesses the letter `O`, then you would break your word list down into two families:

- `-OO-`, containing COOL and GOOD.
- `----`, containing ALLY.

The first of these families is larger than the second, and so you choose the pattern `-OO-`, revealing two O's in the word and reducing your list down to:

	COOL GOOD

But what happens if your opponent guesses a letter that doesn't appear anywhere in your word list? For example, what happens if your opponent now guesses 'T'? This isn't a problem. If you try splitting these words apart into word families, you'll find that there's only one family --- the one with the pattern `----` in which T appears nowhere and which contains both COOL and GOOD. Since there is only one word family here, it's trivially the largest family, and by picking it you'd maintain the word list you already had.

There are two possible outcomes of this game. First, your opponent might be smart enough to pare the word list down to one word and then guess what that word is. In this case, you should congratulate them --- that's an impressive feat considering the scheming you were up to! Second, and by far the most common case, your opponent will be completely stumped and will run out of guesses. When this happens, you can pick any word you'd like from your list and say it's the word that you had chosen all along >=). The beauty of this setup is that your opponent will have no way of knowing that you were dodging guesses the whole time --- it looks like you simply picked an unusual word and stuck with it the whole way.

## Specification

Your assignment is to write a computer program which plays a game of Hangman using this "Evil Hangman" algorithm. To do this, we will re-use (almost) all of the code you have written in the previous part of the exercise.

However, for the sake of completeness, your program should do the following (new parts are made bold):

1. Read the file `dictionary.txt`, which contains the full contents of the Official Scrabble Player's Dictionary, Second Edition. This word list holds over 120,000 words, which should be more than enough for our purposes.

2. Prompt the user for a word length, reprompting as necessary until a number is entered such that there's at least one word that's exactly that long. That is, if the user wants to play with words of length -42 or 137, since no English words are that long, you should reprompt.

3. Prompt the user for a number of guesses, which must be an integer greater than zero. Don't worry about unusually large numbers of guesses – after all, having more than 26 wrong guesses is not going to help your opponent!

4. **Prompt the user for whether she wants to have a running total of the number of words remaining in the word list. This completely ruins the illusion of a fair game that you'll be cultivating, but it's quite useful for testing (and grading!)**

5. Play a game of Hangman using the Evil Hangman algorithm, as described below:

	1. **Construct a list of all words in the English language whose length matches the input length.**

	2. Print out how many guesses the user has remaining, along with any letters the player has guessed and the current blanked-out version of the word. If the user chose earlier to see the number of words remaining, print that out too.

	3. Prompt the user for a single letter guess, reprompting until the user enters a letter that she hasn't guessed yet. Make sure that the input is exactly one character long and that it's a letter of the alphabet.

	4. **Partition the words in the dictionary into groups by word family.**

	5. **Find the most common "word family" in the remaining words, remove all words from the word list that aren't in that family, and report the position of the letters (if any) to the user. If the word family doesn't contain any copies of the letter, subtract a remaining guess from the user.**

	6. **If the player has run out of guesses, pick a word from the word list and display it as the word that the computer initially "chose."**

	7. If the player correctly guesses the word, congratulate her.

6. Ask if the user wants to play again and loop or exit accordingly.

## Architecture

As in last exercise, your program will consist of three major parts. Two of the three parts do not really need any adjustment, although you might want your evil hangman to sound more evil. Again, for completeness, your program will consist of the following:

1. The Lexicon class: Lexicon objects are used to retrieve words for the game from a dictionary.

2. **The `EvilHangman` class: an *EvilHangman* object will include all of the logic needed to play the Hangman game. It will keep track of the current status of the game, and it will be able to update the status of the game when a letter is guessed. However, an EvilHangman object will not directly interact with the user (the person playing the game).**

3. The user interface: this is a piece of code that interacts with the user. It displays messages to the user about the game, and prompts her for new guesses. This piece of code will use the Hangman class to keep track of the game itself.

This time, other than taking care that there are words of the requested length, think of how you will implement the grouping of word families. Letter position matters just as much as letter frequency. When computing word families, it's not enough to count the number of times a particular letter appears in a word; you also have to consider their positions. For example, "BEER" and "HERE" are in two different families even though they both have two E's in them. Consequently, representing word families as numbers representing the frequency of the letter in the word will get you into trouble.

## Steps

### 0. Before you get started

Create a new file that will contain your code for this exercise. We will not rewrite the lexicon class, so import it from the other file at the top of your code. Your user interface will function exactly the same as the normal Hangman user interface, so you can import the function you wrote it in as well. Finally, import your `Hangman` class, as we will be extending upon it.

Extention of your `Hangman` class will be done through inheritance. Inheritance is the process by which a so-called child-class derives the data and behaviour of its parent class. In our case, there is only a couple of changes we need to make, as the functionality in general of the game is not too different. In fact, the only changes we need to make are to the `__init__()`, and the `guess()` methods. Depending on how you have implemented `consistent_word()` in the previous part of the exercise, you might need to change its functionality as well. After importing, inheritance of **all** the properties of the `Hangman` class can be done by creating the `EvilHangman` class as follows:

    class EvilHangman(Hangman):
				# Continue your code here

If we do not change anything here, the `EvilHangman` class will function exactly the same as a normal `Hangman` class. However, by *overriding* specific functions, we can change how the class works without having to rewrite everything.

### 1. The `EvilHangman` class

Your code should follow the following structure. It is up to you to fill in the methods. Remember that depending on the way you implement `consistent_word()`, you might or might not need to change it as well.

    class EvilHangman(Hangman):
				def __init__(self, lexicon, length=8, num_guesses=5):
						"""
						Initialize game by choosing a word and creating an empty pattern.
						If no length or number of guesses are given, default to 8 and 5 respectively
						"""
						super().__init__(lexicon, length, num_guesses)

						# TODO

				def guess(self, letter):
						""""
						Update the game for a guess of letter. Return True if the letter
						is added to the pattern, return False if it is not.
						"""
						# TODO

				def __str__(self):
						"""
						Displays the letters that have been guessed, the number of words that
						are remeaining, and the current state of the game
						"""
						# TODO

`super()` here refers to the parent class, which in this case is `Hangman`. It uses the normal `Hangman` class initiator, and then runs the code below. This way, you do not have to repeat code that was already in the original class!

Purely for testing purposes, we would like to implement the `__str__` method, which allows us to call `print(game)` and look at a couple of stats. The resulting print could look something like the following:

	letters guessed are "aemnid", 201 words remaining, game not won

After instantiating a new game, the resulting object should be able to respond to the following actions:

- Guessing a letter
- Producing the current pattern
- Producing the letters that have been guessed so far
- Producing a word that is consistent with the current pattern (to display to the user once the game has been lost)
- Checking if the game is finished
- Checking if the game has been won
- Checking if the game has been lost

To fully implement the game, the object should at least take care of tracking:

- Guessed letters up until now
- The number of guesses remaining
- The set of currently remaining words

It's up to you to think about how you want to partition words into word families. Think about what data structures would be best for tracking word families and the master word list. Would an associative array work? How about a stack or queue? Thinking through the design before you start coding will save you a lot of time and headache.

> Don't explicitly enumerate all potential new patterns. If you are working with a word of length `n`, then there are `2**n` possible patterns, and thus word families, for each letter. However, most of these families don't actually appear in the English language. For example, no English words contain three consecutive U's, and no word matches the pattern `E-EE-EE--E`. Rather than explicitly generating every pattern whenever the user enters a guess, see if you can generate patterns only for words that actually appear in the word list. One way to do this would be to scan over the word list, storing each word in a table mapping patterns to words in the corresponding family.

Of course, we expect you to apply the same assertions as in the `Hangman` class.

### 2. Testing the `Hangman` game

Let's test our game logic. We should be able to start a new game, and repeatedly guess letters. This is a perfect opportunity to use the `__str__` method, which gives us basics stats about the game --- which we use to verify its state.

Again, test your game interactively by running `python` and then `from hangman import *`, and entering the following commands, or a variation thereof:

	lex = Lexicon('dictionary.txt')
	game = Hangman(lex, 8, 6)
	game.guess("e")
	print(game)
	game.guess("a")
	print(game)
	print(game.finished())
	print(game.consistent_word())
	print(game.pattern())
	game.guess("o")
	game.guess("i")
	game.guess("u")
	print(game.pattern())
	print(game)

Further test your code by using your previously made user interface. See if you can beat your own program!

## Extensions

The algorithm outlined in this handout is by no means optimal, and there are several cases in which it will make bad decisions. For example, suppose that a player has exactly one guess remaining and that computer has the following word list:

	DEAL   TEAR   MONK

If the player guesses the letter 'E' here, the computer will notice that the word family for the pattern `-E--` has two elements and the word family for the pattern `----` has just one. Consequently, it will pick the family containing DEAL and TEAR, revealing an E and giving the player another chance to guess. However, since the player has only one guess left, a much better decision would be to pick the family `----` containing MONK, causing the player to lose the game.

There are several other places in which the algorithm does not function ideally. For example, suppose that after the player guesses a letter, you find that there are two word families, the family `--E-` containing 10,000 words and the family `----` containing 9,000 words. Which family should the computer pick? If the computer picks the first family, it will end up with more words, but because it revealed a letter the player will have more chances to guess the words that are left. On the other hand, if the computer picks the family `----`, the computer will have fewer words left but the player will have fewer guesses as well. More generally, picking the largest word family is not necessarily the best way to cause the player to lose. Often, picking a smaller family will be better.

After you implement this assignment, take some time to think over possible improvements to the algorithm. You might weight the word families using some metric other than size. You might consider
having the computer "look ahead" a step or two by considering what actions it might take in the future.

If you implement something interesting, make sure to document your partition method well by describing your changes in detail!
