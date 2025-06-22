# Password-Generator
I have successfully completed the project titled “Password Generator Using Python”, which focuses on generating strong, secure, and customizable passwords based on user preferences. The primary objective of this project was to create a simple tool that helps users generate random passwords of desired length and complexity, improving password security.
The project was developed using core Python programming concepts such as conditional logic, string manipulation, and the random and string libraries. It allows users to choose the password length and whether to include uppercase letters, lowercase letters, digits, and special characters.

import random
import string

def generate_password(length, use_upper, use_lower, use_digits, use_special):
    characters = ''
    
    if use_upper:
        characters += string.ascii_uppercase
    if use_lower:
        characters += string.ascii_lowercase
    if use_digits:
        characters += string.digits
    if use_special:
        characters += string.punctuation

    if not characters:
        return "Error: No character types selected."

    password = ''.join(random.choice(characters) for _ in range(length))
    return password

# User input
try:
    length = int(input("Enter password length: "))

    print("\nInclude the following in your password:")
    use_upper = input("Uppercase letters? (y/n): ").lower() == 'y'
    use_lower = input("Lowercase letters? (y/n): ").lower() == 'y'
    use_digits = input("Numbers? (y/n): ").lower() == 'y'
    use_special = input("Special characters? (y/n): ").lower() == 'y'

    password = generate_password(length, use_upper, use_lower, use_digits, use_special)
    print("\nGenerated Password:", password)

except ValueError:
    print("Please enter a valid number for password length.")
