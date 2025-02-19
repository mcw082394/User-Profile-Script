# User-Profile-Script
A Python script designed to automate the creation and management of user profiles on a system.
import random
import json

# Simulated user input (workaround for sandbox restrictions)
name = "John Doe"  # Simulated input
age = "25"  # Simulated input
favorite_color = "Blue"  # Simulated input
favorite_hobby = "Reading"  # Simulated input

# Step 2: Validate age input
if not age.isdigit():
    print("Invalid age! Please enter a number.")
    exit()

age = int(age)

# Step 5: Generate a random user ID
user_id = random.randint(1000, 9999)

# Step 6: Create a random username
username = f"{name}_{user_id}"

# Step 7: Store data in a dictionary
user_profile = {
    "User ID": user_id,
    "Username": username,
    "Name": name,
    "Age": age,
    "Favorite Color": favorite_color,
    "Favorite Hobby": favorite_hobby
}

# Step 8: Convert to JSON and save to file
with open("user_profile.json", "w") as file:
    json.dump(user_profile, file, indent=4)

# Step 9: Read from the file and print the stored data
with open("user_profile.json", "r") as file:
    saved_profile = json.load(file)

print("\n✅ User Profile Saved & Loaded Successfully!")
print(json.dumps(saved_profile, indent=4))
