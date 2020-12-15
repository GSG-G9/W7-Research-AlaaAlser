
## HTTPS
  HTTPS is a secure version of HTTP because it uses SSL/TLS as a sub layer. When a website uses HTTPS in its web address, it indicates that any communication taking place between a browser and server is secure. In other words, if your website is using HTTPS, all the information will be encrypted by SSL/TLS certificates ,this is particularly important when users transmit sensitive data, such as by logging into a bank account, email service, or health insurance provider.

----------------


## What are TLS/SSL certificates ?
 SSL refers to Secure Sockets Layer whereas TLS refers to Transport Layer Security.  Basically, they are one and the same, but, entirely different.

SSL and TLS are cryptographic protocols that authenticate data transfer between servers, systems, applications and users. For example, a cryptographic protocol encrypts the data that is exchanged between a web server and a user.

SSL was a first of its kind of cryptographic protocol. TLS on the other hand, was a recent upgraded version of SSL.
  
----------------

## How Do SSL/TLS Certificates Work?

SSL have two-key encryption system:

### Private Key:
This key is responsible for the decryption of data and this key is only present on the site's server / is hidden and is almost impossible to obtain.

### Public Key: 
This key is the one that is used to encrypt information or data, and it is called public because the browser obtains it by entering any website that uses https.

Thus, the data transfer process became greatly secure, as it is true that the https protocol does not mean complete security, but it is much better and provides adequate protection for most sites.
If your site is a banking service, for example, then you need more protection.

You can tell whether a website is using SSL by looking for a padlock icon or a green bar at the top of your browser. You should be able to click on this icon to view the information on who holds the certificate and to manage your SSL settings.

For instance

1-Any message encrypted with Bob's public key can only be decrypted with Bob's private key.

2-Anyone with access to to Alice's public key can verify that a message (signature) could only have been created by someone with access to Alice's private key.

![](https://aprilspokes.files.wordpress.com/2014/10/chrome-secure-site-thumb.gif?w=1200)

   
----------------


## Why is this important to implement in your projects?

Today there isn’t much content that website users or creators want passed over the web that isn’t fairly secure and generally they would rather a website have a secure connection versus not. So, website creators are making sure that their sites are HTTPS versus HTTP, even if they run a fairly innocuous informational site about dog breeds.
  
----------------

## How to generate certificates and use them in a node project ?

**Step 1:Create or download SSL Certificate Files** 
  - create certificate
```
openssl req -nodes -new -x509 -keyout server.key -out server.cert
```
- or you can buy SSL Certificate Files and download it
**Or ask the server owner to give you a certificate without entering data**

**Step 2: Create https_server.js file & upload SSL files to Server directory**
- Generate a private key (key.pem)
- Create the Certificate Signing Request (cert.pem)
- Assign that keys to server using http.createServer()
```
const app = require("express")();
const https = require("https");
const fs = require("fs");

app.get("/", (req, res) => {
  res.send("Hello");
});

https.createServer(
    { key: fs.readFileSync("server.key"),
      cert: fs.readFileSync("server.cert")
      },
    app
  )
  .listen(4000, () => {
    console.log("Listening...");
  });
  
```



**Step 3: Start Node.js**
