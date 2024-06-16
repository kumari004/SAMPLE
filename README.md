# PRODIGY_CS_01
alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

def encryption(plain, shiftkey):
    cipher = ""
    for char in plain:
        if char in alphabet:
            position = alphabet.index(char)
            new_position = (position + shiftkey) % 26
            cipher += alphabet[new_position]
        else:
            cipher += char
    print(f"Here is the text after encryption: {cipher}")

def decryption(cipher, shiftkey):
    plain = ""
    for char in cipher:
        if char in alphabet:
            position = alphabet.index(char)
            new_position = (position - shiftkey) % 26
            plain += alphabet[new_position]
        else:
            plain += char
    print(f"Here is the text after decryption: {plain}")

wanna_end = False
while not wanna_end:
    todo = input("Type 'encrypt' for encryption, 'decrypt' for decryption:\n").lower()
    text = input("Leave your message here: ").lower()
    shift = int(input("Enter shift key of your choice: \n"))
    
    if todo == "encrypt":
        encryption(plain=text, shiftkey=shift)
    elif todo == "decrypt":
        decryption(cipher=text, shiftkey=shift)
    else:
        print("Invalid input. Please type 'encrypt' or 'decrypt'.")

    confirmation = input("Type 'yes' to continue, 'no' to exit: \n").lower()
    if confirmation == "no":
        wanna_end = True
        print("Have a nice day! Bye!")
