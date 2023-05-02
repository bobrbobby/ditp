import random

def game():
    print("Welcome to Rock, Paper, Scissors!")
    rounds = int(input("How many rounds do you want to play? "))
    print("Choose your weapon: ")
    print("1) Rock")
    print("2) Paper")
    print("3) Scissors")

    player_score = 0
    computer_score = 0

    for round in range(rounds):
        print("\nRound", round+1)

        player_choice = int(input("Enter your choice (1-3): "))

        while player_choice < 1 or player_choice > 3:
            player_choice = int(input("Invalid choice. Please enter a number between 1 and 3: "))

        if player_choice == 1:
            player_weapon = "rock"
        elif player_choice == 2:
            player_weapon = "paper"
        else:
            player_weapon = "scissors"

        computer_choice = random.randint(1, 3)

        if computer_choice == 1:
            computer_weapon = "rock"
        elif computer_choice == 2:
            computer_weapon = "paper"
        else:
            computer_weapon = "scissors"

        print("You chose", player_weapon)
        print("The computer chose", computer_weapon)

        if player_weapon == computer_weapon:
            print("It's a tie!")
        elif player_weapon == "rock" and computer_weapon == "scissors":
            print("You win!")
            player_score += 1
        elif player_weapon == "paper" and computer_weapon == "rock":
            print("You win!")
            player_score += 1
        elif player_weapon == "scissors" and computer_weapon == "paper":
            print("You win!")
            player_score += 1
        else:
            print("You lose!")
            computer_score += 1

    print("\nFinal Scores:")
    print("You:", player_score)
    print("Computer:", computer_score)

    if player_score > computer_score:
        print("Congratulations, you win!")
    elif player_score == computer_score:
        print("It's a tie!")
    else:
        print("Sorry, you lose.")

    play_again = input("Do you want to play again? (y/n): ")
    if play_again == "y":
        game()
    else:
        print("Thanks for playing!")

game()
