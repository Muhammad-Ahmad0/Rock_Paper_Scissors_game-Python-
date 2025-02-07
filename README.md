import random

# Choices for the game
choices = ["Rock", "Paper", "Scissors"]

# Function to determine the winner
def determine_winner(player, computer):
    if player == computer:
        return "It's a tie!"
    elif (player == "Rock" and computer == "Scissors") or \
         (player == "Paper" and computer == "Rock") or \
         (player == "Scissors" and computer == "Paper"):
        return "You win!"
    else:
        return "Computer wins!"

# Main game loop
def main():
    print("Welcome to the Rock Paper Scissors game!")
    print("Enter 'Rock', 'Paper' or 'Scissors' to play. Type exit to quit.")

    while True:
        # Player's choice
        player_choice = input("Your choice: ").capitalize()

        if player_choice == 'Exit' or player_choice == 'Quit':
            print("Thanks for playing!")
            break
        elif player_choice not in choices:
            print("Invalid choice. Please enter 'Rock', 'Paper' or 'Scissors'.")
            continue

        # Computer's random choice
        computer_choice = random.choice(choices)
        print(f"Computer's choice: {computer_choice}")

        # Determine and display the result
        result = determine_winner(player_choice, computer_choice)
        print(result)

# Run the game
main()
