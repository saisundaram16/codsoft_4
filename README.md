#Rock_Paper_Scissor_game

import random

def get_computer_choice():
    return random.choice(["rock", "paper", "scissors"]) 

def determine_winner(user_choice, computer_choice):
    
    if user_choice == computer_choice:   
        return "tie"
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "user"
    else:
        return "computer"

def play_game():
    user_score = 0
    computer_score = 0
    
    print("Welcome to Rock, Paper, Scissors!")
    
    while True:
       
        user_choice = input("Choose rock, paper, or scissors: ").lower()
        while user_choice not in ["rock", "paper", "scissors"]:
            print("Invalid choice! Please choose rock, paper, or scissors.")
            user_choice = input("Choose rock, paper, or scissors: ").lower()
        
        
        computer_choice = get_computer_choice()
        
       
        print(f"You chose: {user_choice}")
        print(f"Computer chose: {computer_choice}")
        
      
        winner = determine_winner(user_choice, computer_choice)
        
        if winner == "user":
            print("You win this round!")
            user_score += 1
        elif winner == "computer":
            print("Computer wins this round!")
            computer_score += 1
        else:
            print("It's a tie!")
        
        
        print(f"Current score - You: {user_score} | Computer: {computer_score}")
        
        
        play_again = input("Do you want to play another round? (y/n): ").lower()
        if play_again != "y":
            break
    
   
    print("\nFinal Scores:")
    print(f"You: {user_score} | Computer: {computer_score}")
    if user_score > computer_score:
        print("You win the game!")
    elif user_score < computer_score:
        print("Computer wins the game!")
    else:
        print("It's a tie game!")


play_game()
