# Prada-Mama
# Define some designer fashion items
designer_tops = ["Gucci T-shirt", "Versace Blouse", "Balenciaga Sweater", "Fendi Tank Top", "Prada Blazer"]
designer_bottoms = ["Chanel Jeans", "Dior Skirt", "Hermès Shorts", "Armani Dress Pants", "Louis Vuitton Leggings"]
designer_shoes = ["Yeezy Sneakers", "Louboutin Heels", "Givenchy Sandals", "Alexander McQueen Boots", "Jimmy Choo Flats"]
designer_accessories = ["Ray-Ban Sunglasses", "Tiffany & Co. Necklace", "Burberry Hat", "Rolex Watch", "Cartier Bracelet"]

# Characters
characters = {
    "Jasmine": "Jasmine is a young Black woman with a love for high fashion and streetwear.",
    "Malik": "Malik is a stylish Black man who always stays ahead of the fashion trends.",
    "Nia": "Nia is a Black girl with a passion for blending traditional African prints with modern designs."
}

# Function to print the outfit
def print_outfit(character, top, bottom, shoes, accessory):
    print(f"\n{character} has chosen the following outfit:")
    print(f"Top: {top}")
    print(f"Bottom: {bottom}")
    print(f"Shoes: {shoes}")
    print(f"Accessory: {accessory}")

# Function to evaluate the outfit
def evaluate_outfit(occasion, top, bottom, shoes, accessory):
    # Basic logic to evaluate outfit (this can be expanded)
    if occasion == "casual":
        if "T-shirt" in top or "Sweater" in top and "Sneakers" in shoes:
            return "Perfect choice for a casual day!"
        else:
            return "You might want to rethink your casual look."
    elif occasion == "formal":
        if ("Blouse" in top or "Blazer" in top) and ("Dress Pants" in bottom or "Skirt" in bottom) and "Heels" in shoes:
            return "You look great for the formal event!"
        else:
            return "This outfit is not quite formal enough."
    elif occasion == "party":
        if "Tank Top" in top or "Blouse" in top and ("Heels" in shoes or "Boots" in shoes):
            return "You're ready to party!"
        else:
            return "You might want to change for the party."
    else:
        return "This outfit doesn't seem to fit the occasion."

# Start the game
def fashion_game():
    print("Welcome to Prada MaMa, the ultimate fashion mini-game!")
    
    # Select a character
    print("\nChoose your character:")
    for i, (character, description) in enumerate(characters.items()):
        print(f"{i+1}. {character} - {description}")
    character_choice = int(input("Enter the number of your choice: ")) - 1
    character_name = list(characters.keys())[character_choice]
    
    occasions = ["casual", "formal", "party"]
    occasion = random.choice(occasions)
    print(f"\n{character_name} has been invited to a {occasion} event. Time to choose an outfit!")

    # Let the player choose their outfit
    print("\nChoose your top:")
    for i, top in enumerate(designer_tops):
        print(f"{i+1}. {top}")
    top_choice = int(input("Enter the number of your choice: ")) - 1
    
    print("\nChoose your bottom:")
    for i, bottom in enumerate(designer_bottoms):
        print(f"{i+1}. {bottom}")
    bottom_choice = int(input("Enter the number of your choice: ")) - 1
    
    print("\nChoose your shoes:")
    for i, shoe in enumerate(designer_shoes):
        print(f"{i+1}. {shoe}")
    shoes_choice = int(input("Enter the number of your choice: ")) - 1
    
    print("\nChoose your accessory:")
    for i, accessory in enumerate(designer_accessories):
        print(f"{i+1}. {accessory}")
    accessory_choice = int(input("Enter the number of your choice: ")) - 1
    
    # Print the outfit
    print_outfit(character_name, designer_tops[top_choice], designer_bottoms[bottom_choice], designer_shoes[shoes_choice], designer_accessories[accessory_choice])
    
    # Evaluate the outfit
    evaluation = evaluate_outfit(occasion, designer_tops[top_choice], designer_bottoms[bottom_choice], designer_shoes[shoes_choice], designer_accessories[accessory_choice])
    print(f"\nEvaluation: {evaluation}")
    
    # Ask to play again
    play_again = input("\nWould you like to play again? (yes/no): ").lower()
    if play_again == "yes":
        fashion_game()
    else:
        print("Thanks for playing Prada MaMa! Goodbye!")

# Run the game
fashion_game()
