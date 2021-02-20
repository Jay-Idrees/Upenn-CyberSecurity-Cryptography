# Cryptography


## Resources

  - [Browserling](https://www.browserling.com/)
  - [Rapid Tables](https://www.rapidtables.com/)
  - [Binary to Text Converter](https://www.browserling.com/tools/binary-to-text)
  - [Browserling Hex-to-Text converter](https://www.browserling.com/tools/hex-to-text)
  - [Browserling Binary-to-Text converter](https://www.browserling.com/tools/binary-to-text)
  - [American Cryptogram Association's list of cipher types](https://www.cryptogram.org/resource-area/cipher-types/)
  - [American Cryptogram Association's list of cipher types](https://www.cryptogram.org/resource-area/cipher-types/)
  



## Caesar Cipher

- Modifying text to unreadable format - the changed text is called ciphertext

- Ecryption > Decryption

- Can be any trick, for example, every letter can be substituted in a systematic manner, for example every 2 letters down 

- Engma machine was created by the Germans to make encryption more sophisticated

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
   
   - Quick analysis. If its just numbers then it is probably just ASCII, if its a combination of numbers and letters then it is probably Hex and if only numbers 0-7 then probably octal.
   
   
   ## Modes of data protection 

    - **DATA at rest** - hardrive database- encryption of the laptop or hard drive
    - **Data in Motion** - Data moving between devices- e-g encrypted email  - use encryption

    ## Goals of Encryption

    - **Privacy and Confidentiality** thats why you are encrypting the message

    - **Authentication**
    - E-g confirmig the source that sent the data (e-g confirming the person who sent the email)
    
    - **Integrity**
    - This is separate from encryption and authentication. It checks that despit the data being encrypted and the source authenticated, the data has also not been altered during transport
    
    - **Non-Repudication**
    - The owner of the email cannot refuse that it was not him 

    ## Methods of encryption

    - Mostly based on mathematical algorithms and algorithims use keys to maintain their security

    - **Strategies**:
    
    1. **Stream or ubstitution Ciphers**: Each letter is replaced with another  to create ciphertext e-g cesar and enigma ciphers

    2. **Transposition** The sequence of the the text is re-arranged. E-g
    - First, break **Hello!** into two blocks: **Hel**  and  **lo!**
    - Next, use the transposition rule to rearrange the letters. 
    - **Hel** to **lHe**
    - **lo!** to **!lo**
    - Lastly, combine the rearranged text to create the ciphertext: **lHe!lo**

    3. **Block**: The algorithms are applied to chunks or blocks of characters

    4.**Combination** Most modern cryptography utilizes a comnination of these strategies

    ## Encryption Strength and Mechanics

    - "How much more secure is _x_ more bits of encryption?" As we increase the number 

    - One bit is only either 1 or 0 

    - For each bit that is added to the key, the key space **doubles** in size. Thus if we increase the total length (or **bit size**) or pw/encryption text to 2 or 3 then the possibilities are increased and it will take longer time. This total number of possibilities is called **key space**

     - Two to the power of the bit size, or  2 ^ [bit size].

    - Depends on the length of the text, type of characters and the possible values. For example if the password is only 1 character and can only be composed numbers 0-9 then the key space is 10. If we make it complex then it will become time consuming 

    - This is what is meant by 64bit or 256bit encryption

    - **Security Tradeoff** The more complex the computation, the more time consuming- holy grail finding an algorythm with the balacne between quality of encryption and the time taken


    ## Symetric key algorithms
    Advance encryption standard