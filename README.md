# python_hangman_game
import random

# Word list
words = ['apple', 'banana', 'grape', 'orange', 'mango']
word = random.choice(words)
guessed_letters = []
tries = 6

while tries > 0:
    display = ''
    for letter in word:
        if letter in guessed_letters:
            display += letter
        else:
            display += '_'
    print("Word:", display)

    if '_' not in display:
        print("You won!")
        break

    guess = input("Guess a letter: ").lower()
    if guess in guessed_letters:
        print("You already guessed that letter.")
        continue

    guessed_letters.append(guess)
    if guess not in word:
        tries -= 1
        print("Wrong guess. Tries left:", tries)

if tries == 0:
    print("You lost! The word was:", word)
    #this is hangman game.Guess the letter and win the game.
