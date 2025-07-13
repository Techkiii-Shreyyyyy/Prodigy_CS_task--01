# Prodigy_CS_task- 01
'CEASER CIPHER PROGRAMME'

def caesar_cipher_encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():  
            start = ord('A') if char.isupper() else ord('a')
            encrypted_text += chr((ord(char) - start + shift) % 26 + start)
        else:
            encrypted_text += char  
    return encrypted_text

def caesar_cipher_decrypt(text, shift):
    decrypted_text = ""
    for char in text:
        if char.isalpha(): 
            start = ord('A') if char.isupper() else ord('a')
            decrypted_text += chr((ord(char) - start - shift) % 26 + start)
        else:
            decrypted_text += char  
    return decrypted_text

def main():
   
    choice = input("Would you like to (E)ncrypt or (D)ecrypt? ").lower()
    text = input("Enter the message: ")
    shift = int(input("Enter the shift value (integer): "))
    
    if choice == 'e':
        encrypted_message = caesar_cipher_encrypt(text, shift)
        print(f"Encrypted Message: {encrypted_message}")
    elif choice == 'd':
        decrypted_message = caesar_cipher_decrypt(text, shift)
        print(f"Decrypted Message: {decrypted_message}")
    else:
        print("Invalid choice! Please enter 'E' for encryption or 'D' for decryption.")

if __name__ == "__main__":
    main()
