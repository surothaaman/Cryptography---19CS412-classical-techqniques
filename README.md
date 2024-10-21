# Ex-1 Caesar Cipher

Caeser Cipher using with different key values

## AIM:
To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.

## DESIGN STEPS:

Step 1: Design of Caeser Cipher algorithnm

Step 2: Implementation using C or pyhton code

Step 3:

    1. In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.

    2.For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
    
    3. The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the scheme, A = 0, B = 1, Z = 25.

    4. Encryption of a letter x by a shift n can be described mathematically as, En(x) = (x + n) mod26

    5. Decryption is performed similarly, Dn (x)=(x - n) mod26

## PROGRAM:

#include <iostream>
#include <cstring>

using namespace std;

// Function to perform Caesar Cipher encryption
void caesarEncrypt(char *text, int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        char c = text[i];
        // Check if the character is an uppercase letter
        if (c >= 'A' && c <= 'Z') {
            text[i] = (c - 'A' + key) % 26 + 'A';
        }
        // Check if the character is a lowercase letter
        else if (c >= 'a' && c <= 'z') {
            text[i] = (c - 'a' + key) % 26 + 'a';
        }
        // Ignore non-alphabetic characters
    }
}

// Function to perform Caesar Cipher decryption
void caesarDecrypt(char *text, int key) {
    // Decryption is the same as encryption with a negative key
    caesarEncrypt(text, 26 - key);
}

int main() {
    char message[100]; // Declare a character array to store the message
    int key;

    cout << "Enter the message to encrypt: ";
    cin.getline(message, sizeof(message)); // Read input from the user
    cout << "Enter the Caesar Cipher key (an integer): ";
    cin >> key; // Read the key from the user

    // Encrypt the message using the Caesar Cipher
    caesarEncrypt(message, key);
    cout << "Encrypted Message: " << message << endl; // Display encrypted message

    // Decrypt the message back to the original
    caesarDecrypt(message, key);
    cout << "Decrypted Message: " << message << endl; // Display decrypted message

    return 0;
}

## OUTPUT:

![image](https://github.com/user-attachments/assets/5437676b-c4df-419d-b308-9b0df1ed55d0)

## RESULT:
The program is executed successfully
