# CODSOFT_TASKNOimport random

choices = ["rock", "paper", "scissors"]

user_score = 0
computer_score = 0

print("=" * 40)
print("      ROCK - PAPER - SCISSORS")
print("=" * 40)
print("Choose: rock, paper, or scissors")
print("Type 'quit' to exit the game.\n")

while True:
    user_choice = input("Enter your choice: ").lower().strip()

    if user_choice == "quit":
        print("\nThanks for playing!")
        print(f"Final Score - You: {user_score} | Computer: {computer_score}")
        break

    if user_choice not in choices:
        print("Invalid choice! Please choose rock, paper, or scissors.\n")
        continue

    # Computer makes a random choice
    computer_choice = random.choice(choices)

    print(f"\nYour choice      : {user_choice}")
    print(f"Computer's choice: {computer_choice}")

    # Determine the winner
    if user_choice == computer_choice:
        print("Result: It's a tie!")

    elif (
        (user_choice == "rock" and computer_choice == "scissors")
        or
        (user_choice == "scissors" and computer_choice == "paper")
        or
        (user_choice == "paper" and computer_choice == "rock")
    ):
        print("Result: You win!")
        user_score += 1

    else:
        print("Result: Computer wins!")
        computer_score += 1

    # Display score
    print(f"Score: You {user_score} - {computer_score} Computer")

    # Ask whether to play again
    play_again = input("\nPlay another round? (yes/no): ").lower().strip()

    if play_again not in ["yes", "y"]:
        print("\nThanks for playing!")
        print(f"Final Score - You: {user_score} | Computer: {computer_score}")
        break

    print("\n" + "-" * 40 + "\n")
