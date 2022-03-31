# Number-Guessing-Game
Guess the number that computer picks
import random
print("Welcme to the Number Guessing Game!")
print("I am thinking a number between 1 and 100.")
number = random.randint(1,100)
difficulty = (input("Choose a difficulty. Type 'easy' or 'hard': "))

def attempt(difficulty):
  if difficulty == "easy":
    return 10
  elif difficulty == "hard":
    return 5
  else:
    print("Invalid input. Try again.")

def guessing(guess):
  global number
  if guess > number:
    print("Too high.\nGuess again")
  elif guess < number:
    print("Too low.\nGuess again")
  else:
    print(f"You got it! The answer was {number}")
    return -1
  

attempt = attempt(difficulty)
while attempt > 0:
  print(f"You have {attempt} attempts remaining to guess the number.")
  guess = int(input("Make a guess: "))
  if not guessing(guess) == -1:
    attempt -= 1
  else:
    attempt = -1
if attempt == 0:
  print(f"You've run out of guesses, you lose. The number was {number}")
