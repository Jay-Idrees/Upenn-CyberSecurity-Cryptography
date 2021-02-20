# Cryptography


## Resources

  - [Browserling](https://www.browserling.com/)
  - [Rapid Tables](https://www.rapidtables.com/)
  - [Binary to Text Converter](https://www.browserling.com/tools/binary-to-text)
  - [Browserling Hex-to-Text converter](https://www.browserling.com/tools/hex-to-text)
  - [Browserling Binary-to-Text converter](https://www.browserling.com/tools/binary-to-text)
  



## Caesar Cipher

- Modifying text to unreadable format - the changed text is called ciphertext

- Ecryption > Decryption

- Can be any trick, for example, every letter can be substituted in a systematic manner, for example every 2 letters down 

- Engma machine was created by the Germans to make encryption more sophisticated

- 

- Some common terms:

Plaintext: Information in human-readable form.

   - **Plaintext**: Information in human-readable form. 

   - **Ciphertext**: Plaintext message that has been encrypted into an unreadable form.

   - **Encryption**: The process of converting plaintext to ciphertext.

   - **Decryption**: The process of converting ciphertext to plaintext.

   - **Cipher**: A method of performing encryption or decryption.

   - **Key**: A parameter specifying how plaintext is converted to ciphertext and vice versa.

   - **Caesar cipher**: A type of cipher that shifts the letters in the alphabet by a fixed number.

   - **Enigma cipher**: A type of cipher used by Germany in World War II to encrypt messages.
   
   ## Encoding vs Encryption, ASCII as an example of encoding

   - Encoding goal is simply transporting the data into another format so that it is compatible for use by a different type of system

   - There is no key involved, the conversion method is publically available. For example binary encoding. The range of a byte is between `00000000` to `11111111`

   - In contrast the goal of Encryption is to revent unauthorized access to the information

   - Another good example of encoding is `ASCII- American Standard Code for Information Interchange` encoding. Using the hexadecimals to convert the binary to text and vise versa. There is encoding for every upper and lower case english letters, punctuation, graphic and mathematical symbols as a number between 0 to 255

   - `0-127` is standard ASCII and `127-255` is extended ASCII

     - The decimal value **84** represents the character **T**.

    - The decimal value **118** represents the character **v**.

    - This conversion is called **decimal to ASCII encoding** or **decimal to text encoding**.  

    - The hex representation of the word "hello" is **68 65 6c 6c 6f**. Designed for more compact representtion of the binary data

    - Alternatively for **octal** as a system that applies a principle similar to hex, but uses digits `0` to `7`. 

    - For example: The octal value **042** represents the decimal **34**.

    - Quick analysis. If its just numbers then it is probably just ASCII, if its a combination of numbers and letters then it is probably Hex and if only numbers 0-7 then probably octal