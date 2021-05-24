import random
import time

rock = 1
paper = 2
scissors = 3
names = {rock: "rock", paper: "paper", scissors: "scissors"}
rules = {rock: scissors, paper: rock, scissors: paper}

player_score = 0
computer_score = 0

def  start ():
    print("let's play a game of rock,paper,scissors.")
    while game():
        pass
    scores()

def  game():
    player = move()
    computer = random.randint(1, 3)
    result(player, computer)
    return play_again()

def move():
    while True:

        player = input(" rock = 1 \npaper= 2 \nscissors = 3\n make a move:")
        try:
            player = int(player)
            if player in (1, 2, 3):
                return player
        except ValueError:
            pass
        print("oops! i didn't understand that. please enter 1,2 or 3 .")

def result(player,computer):
    print("1...")
    time.sleep(1)
    print("2...")
    time.sleep(2)
    print("3.!")
    time.sleep(3)
    print("computer threw {0}!".format(names[computer]))
    global player_score, computer_score
    if player == computer:
        print("tie game.")
    else:
        if rules[player] == computer:
            print("your victory has been assured.")
            player_score += 1
        else:
            print("the computer laughs as you realise you have been defeated .")
            computer_score += 1
def  play_again():
    answer = input("would you like to play again ? y/n :")
    if answer is ("y", "Y", "yes", "Yes"):
        return answer
    else:
        print("thank you very much for playing our game. see you next time!")

def  scores():
    global player_score, computer_score
    print("HIGH SCORES")
    print("player:", player_score)
    print("computer:", computer_score)

if __name__ == '__main__':
    start()
