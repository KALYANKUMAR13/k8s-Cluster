In normal http protocal, file is sent in a plain format, so hackers can able to see the file 

Symmentric Encryption:
When we are encrypting the file with number+apla and sending through server. The server needs the key to decrypt it. So the client, sends the key along with the file. Here hacker can get the key and decrypt the data too.Same key is used for encrypting and decrypting.

To solve the above one, Aysmmentric Encryption comes into the picture.

Asymmentric Encryption:
Private Key and Public Key 
ssh keygen concept.

Client Requests a Secure Session:
When a user types a URL starting with https:// or clicks on a link to a secure site, the browser (client) requests a secure session with the server.

Server Responds with its Digital Certificate:
The server responds by sending its digital certificate to the client. This certificate contains the server’s public key and is issued by a trusted Certificate Authority (CA).

Client Verifies the Certificate:
The client verifies the server's certificate against a list of trusted CAs. If the certificate is valid and the CA is trusted, the client proceeds. Otherwise, it will show a security warning.

Establishing a Session Key:
Once the certificate is verified, the client generates a random symmetric session key. This key will be used for encrypting the data exchanged during the session.
The client encrypts this session key using the server’s public key and sends it to the server. This ensures that only the server can decrypt the session key, as only the server has the corresponding private key.
```
Normal Data---->Symmentrickey---->Server's Public Key
```
Server Decrypts the Session Key:
The server uses its private key to decrypt the session key. Now both the client and the server share the same symmetric session key.

Secure Communication Using the Session Key:
The client and server use the symmetric session key to encrypt and decrypt the data exchanged during the session. Symmetric encryption is much faster than asymmetric encryption, making it suitable for encrypting the bulk of the data.
