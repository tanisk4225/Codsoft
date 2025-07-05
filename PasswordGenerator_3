import random
import string

length = int(input("Enter the desired length of the password: "))

print("Choose password level you want to create:")
print("1. Using only letters (a-z, A-Z)")
print("2. Using letters and numbers")
print("3. Using letters, numbers and special characters")

ch = input("Enter your choice out of 1, 2 or 3: ")

if ch == '1':
    characters = string.ascii_letters
elif ch == '2':
    characters = string.ascii_letters + string.digits
elif ch == '3':
    characters = string.ascii_letters + string.digits + string.punctuation
else:
    print("Invalid choice, using only letters by default.")
    characters = string.ascii_letters
password = ''.join(random.choice(characters) for _ in range(length))

print("Generated Password is:", password)