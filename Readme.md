# Cryptography


## Resources

  - [Browserling](https://www.browserling.com/)
  - [Rapid Tables](https://www.rapidtables.com/)
  - [Binary to Text Converter](https://www.browserling.com/tools/binary-to-text)
  - [Browserling Hex-to-Text converter](https://www.browserling.com/tools/hex-to-text)
  - [Browserling Binary-to-Text converter](https://www.browserling.com/tools/binary-to-text)
  - [American Cryptogram Association's list of cipher types](https://www.cryptogram.org/resource-area/cipher-types/)
  - [American Cryptogram Association's list of cipher types](https://www.cryptogram.org/resource-area/cipher-types/)
  - [RSA (cryptosystem) (Wikipedia)](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
  - [GlobalSign: SSL vs TLS - What's the Difference?](https://www.globalsign.com/en/blog/ssl-vs-tls-difference/)
  - [The GNU Privacy Handbook entry on making and verifying signatures](https://www.gnupg.org/gph/en/manual/x135.html)
  - [Birthday problem (Wikipedia)](https://en.wikipedia.org/wiki/Birthday_problem).
       - [Diffie–Hellman Key Exchange (Wikipedia)](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange)
     - [Secret Key Exchange (Diffie-Hellman) Video
 (YouTube)](https://www.youtube.com/watch?v=NmM9HA2MQGI)
  



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

## Goals of Encryption - This is called the P.A.I.N Model

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

1. **Stream or ubstitution Ciphers**: Each letter is replaced with another one at a time to create ciphertext e-g cesar and enigma ciphers

2. **Transposition** The sequence of the the text is re-arranged. E-g
- First, break **Hello!** into two blocks: **Hel**  and  **lo!**
- Next, use the transposition rule to rearrange the letters. 
- **Hel** to **lHe**
- **lo!** to **!lo**
- Lastly, combine the rearranged text to create the ciphertext: **lHe!lo**

3. **Block**: The algorithms are applied to chunks or blocks of characters

4.**Combination** Most modern cryptography utilizes a comnination of these strategies

## Encryption Strength and Mechanics

- "How much more secure is _x_ more bits of encryption?"

- One bit is only either 1 or 0 

- Each algorithm has a specific **key space**: a range of numbers that can be used for that specific algorithm

- A key space is a total possible permutations of a key

- Why don't we just have one million-bit key to ensure it's never cracked?

- For each bit that is added to the key, the key space **doubles** in size. Thus if we increase the total length (or **bit size**) or pw/encryption text to 2 or 3 then the possibilities are increased and it will take longer time. This total number of possibilities is called **key space**

    - Two to the power of the bit size, or  2 ^ [bit size].

- Depends on the length of the text, type of characters and the possible values. For example if the password is only 1 character and can only be composed numbers 0-9 then the key space is 10. If we make it complex then it will become time consuming 

- This is what is meant by 64bit or 256bit encryption

- **Security Tradeoff** The more complex the computation, the more time consuming- holy grail finding an algorythm with the balacne between quality of encryption and the time taken


## Symetric key algorithms (the alternative is Asymetric Key Algorithms)

- Symmetric key algorithms use a single, shared key to encrypt and decrypt a message.

- The shared key is also referred to as a **private key**. 

- **Data encryption standard (DES)**

- FBI initially developed 56k bit key, but it was not very robust

- **Advanced Encryption Standard (AES)**

- Rijndael cipher was the strongest in the FBI contest of encryption and was named AES

- AES offers multiple encryption strengths: 128-bits, 192-bits, and 256-bits. 

- The AES algorithm cannot be used without advanced technologies


## Steps of the Encryption process using OpenSSL

1. Step 1: Generating the private key and IV - This step basically dictats the features to be included in the encryption method

- `openssl` is a free encryption software that can be installed

`openssl enc -pbkdf2 -nosalt -aes-256-cbc -k mypassword -P > key_and_IV`
     
  
- `openssl` initializes the OpenSSL program.
- `enc` stands for _encryption_.
- `-pbkdf2` specifies the encryption key type. 
- `-nosalt` specifies that salting will not be applied. Salting adds a random value
- `-aes-256-cbc` is the name of the cipher used. 
- `-k mypassword` creates a key, with the password `mypassword`.
- `-P > key_and_IV` prints out the key and IV to a file called `key_and_IV`.

- Very important: Note that the key here is generated based on the length of the supplied password. If I give the password to another person then they can use the same process to generate the key with the password provided and then then use the key and IV to decrypt. The process is consistent. 

  - For example:

  ```
    key=89E01536AC207279409D4DE1E5253E01F4A1769E696DB0D6062CA9B8F56767C8
    iv =EE99333010B23C01E6364E035E97275C
  ```
- **key space or private key** It is a range of characters that can be used for a specific algorithm- It is used for encryption and decryption
- **Initialization Vector** It is an additional value that adds randomness to the value

2. Step 2: Using the generated key space and IV on an existing file to create a new encrypted file

  `openssl enc -pbkdf2 -nosalt -aes-256-cbc -in plainmessage.txt -out plainmessage.txt.enc -base64 -K 89E01536AC207279409D4DE1E5253E01F4A1769E696DB0D6062CA9B8F56767C8 -iv EE99333010B23C01E6364E035E97275C`
   
    
- `openssl` initializes the OpenSSL program.
- `enc` stands for _encryption_.
- `-pbkdf2` specifies the encryption key type. 
- `-nosalt` specifies that salting will not be applied.
- `-aes-256-cbc` the type of cipher used.
- `-in plainmessage.txt` is the input file that we will be encrypting.
- `-out plainmessage.txt.enc` is the output file that is encrypted.
- `-base64` specifies completing the encryption in a text format.
- `-K 89E01536AC207279409D4DE1E5253E01F4A1769E696DB0D6062CA9B8F56767C8` specifies the key and the key value.
- `-iv EE99333010B23C01E6364E035E97275C` specifies the IV and the IV value.

3. Step 3: Decrypting the file

`openssl enc -pbkdf2 -nosalt -aes-256-cbc -in plainmessage.txt.enc -d -base64 -K 89E01536AC207279409D4DE1E5253E01F4A1769E696DB0D6062CA9B8F56767C8 -iv EE99333010B23C01E6364E035E97275C`
   
- The syntax is the same as the encryption, except for two small changes:
  
    - `-d` specifies decryption.

    - `-in plainmessage.txt.enc` specifies that the input message is now the encrypted 

## Asymetric or Public-Key Encryption 

- **RSA**
- **GPG**

## Checking for Data Integrity- (whether the data is altered or not) with Hashing

- **Message Digest**
- **MD5**, **SHA256**, **one-way** algorithms
- Creating hashtags `md5sum`, `sha256sum`

## Digital Signatures

## Steganography

Hiding data inside the image files. You typically need a cover file and file or text file that needs data. The hidden file can then be extracted

- **Insertion**

- `steghide embed -cf family.jpg -ef hidden_message.txt`
    

- `steghide` is the command to run `steghide`.

- `embed` is the additional command to specify that we are hiding the message.

- `-cf family.jpg` uses `-cf`, which stands for _cover file_, to specify the file that the data is being hidden in. In this example, we are using the file `family.jpg`.

- `-ef hidden_message.txt` uses `-ef`, which stands for _embed file_, to specify the file that is being hidden. In this example, we are hiding `hidden_message.txt`.

 - **Extraction**

- `steghide extract -sf family.jpg`

- `extract` is the additional command to indicate we are extracting the message.

- `-sf family.jpg` uses `sf`, which stands for _stegofile_, to specify which file to run the steganography tool against.
  

## Using SSL certificates

- Uses public key cryptography for secure exchange of data from a browser to the webserserver hosting the website

- SSL certificates use HTTPS protocol

- Certificate issuing authorities for the companies
- Globalsign
- DigiCert
- Comodo
- Symantec

- **Process**

1. The company requests an SSL certificate **X.509 certificate** for securing online communications.

2. Company documents are submitted to the **certification authority** company by a designated official. Also supplying a unique ip address(domain name)

3. This step is called **Certificate signing request (CSR)** which consists of generating a public and private encryption key. Only the public key is sent to the certificate authority. CSR also contains information about the company

4. After verification of the documents, the company is issued a certificate which is then installed on the webserver by the company

5. No one has the private encryption key. Its hidden and installed on the webserver.

6. You can look at the trusted companies for issuing the certificates which the common browsers recognize- e-g- in chrome you can select security and privacy, manage certificates and then look at the Trusted Root Certification Authorities to see a list of all the approved certification authorities. 

7. **Chain of Trust** These are the top certificate issuing companies (called **root certificate authorities**) that further approve another set of **certification authority** companies that intern issue the SSL certificatee. This can be looked at by clicking view on the certificates window and then selecting certification pathway to reveal the chain of trust. The purpose of this chain of trust is ensure that in the case the issing company is hacked, only the certificates that were issures by that comapnay were compromised. 

8. Note that the public and the private key system is separate from the session key. Below are the setps that occur when you viit a secure website

    a. Browser asks webserver for certificate <br>
    b. Server responds with certificate <br>
    c. Browser verifies the certificate expiration date and root CA (the top most on the chain of trust) <br>
    d. Public key is next used by the browser to create a new session key which is then sent to the server. <br>
    e. The session key establishes a secure session between the browser and the webserver<br>
    f. This is now an encryptd session- only after this is extablished between the browser and server, will any data exchange can occur between the server and the computer that is vising the website<br>
    g. The encryption and decryption of the session data exchange is the symetric encryption. Prior steps are asymetric in the HTTPS protocol<br>

9. Even if a certificate has been issued, a website can be considered invalid if the certificate is:
     - Expired.
     - Assigned to the wrong host.
     - Issued by a CA that is not in the browser's root store.


## Crack a password with cryptography

 - Cryptographic attack types include statistical, birthday, brute force, frequency, replay, known-plaintext, and chosen-plaintext attacks.

 - **Hashtag- Command program for cracking a Hash**

 It uses:
 - `Rainbow tables`  These are tables that display the corresponding cyphertext for a given plain text
 - `dictionary wordlists` These are commonly used passwords
 - `broot force attacks` like `John the Rippper`

 - Hackers can use this to determine the password of the root user after they obtained access into the network

 Steps:

1. ` echo ea847988ba59727dbf4e34ee75726dc3 > hash.txt` Copy the hash into a file

2.  `hashcat -m 0 -a 0 -o solved.txt hash.txt rockyou.txt --force`

- `hashcat`: The command to execute Hashcat.

- `-m 0`: The `0` indicates the script will use the MD5 hash, as this was the hash the security professional determined to be in use.

- If a different hashing algorithm is in use, we would change the value of `0`.

 - For example: We would use `-m 100` for SHA-1, and `-m 1400` for SHA-256.
        
    
 - `-a 0`: The `0` tells the script to apply the attack method of "dictionary."
        - The above link provides additional attack types.

- `-o solved.txt`: Creates an output file called `solved.txt`.

- `hash.txt`: The input file of the hash.

 - `rockyou.txt`: The file containing the wordlist we will check against.

 - `--force`: Overrides any small errors that may occur.








## Hard disk data encryption

## Email and Web Security
**S/MIME** and **PGP**
- Uses public key and the signature 
- 



## Mitigation Strategies after cryptogenic attacks