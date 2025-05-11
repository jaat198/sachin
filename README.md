def caesar_encrypt(message, shift):
    """Encrypt the message using Caesar Cipher."""
    encrypted_text = ""
    for char in message:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            encrypted_text += chr((ord(char) - shift_base + shift) % 26 + shift_base)
        else:
            encrypted_text += char
    return encrypted_text

def caesar_decrypt(encrypted_message, shift):
    """Decrypt the message using Caesar Cipher."""
    return caesar_encrypt(encrypted_message, -shift)

def main():
    print("Welcome to the Caesar Cipher Program!")
    while True:
        print("\nWhat would you like to do?")
        print("1. Encrypt a message")
        print("2. Decrypt a message")
        print("3. Exit")
        choice = input("Enter your choice (1/2/3): ")
        
        if choice == '1':
            message = input("Enter the message to encrypt: ")
            shift = int(input("Enter the shift value: "))
            encrypted_message = caesar_encrypt(message, shift)
            print(f"Encrypted Message: {encrypted_message}")
        elif choice == '2':
            encrypted_message = input("Enter the message to decrypt: ")
            shift = int(input("Enter the shift value: "))
            decrypted_message = caesar_decrypt(encrypted_message, shift)
            print(f"Decrypted Message: {decrypted_message}")
        elif choice == '3':
            print("Exiting the program. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
