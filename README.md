# smartPass
Password manager using Smartphone based Biometrics MFA and Samsung Knox

Tool Design project for Stony Brook Network security course.

Password managers are commonplace, and most browsers provide password managers as inbuilt functionality or as addons. 
Such password managers usually follow certain mechanism/paradigms.
Most password managers save logins locally on the machine in encrypted manner. 
There can also be a master password that needs to be entered for accessing the login data. 

Example – Firefox inbuilt password manager:
Users set a Master password, which is stored into a hash value after adding a random string and then applying SHA-1 algorithm. 
This generated hash value is then used to encrypt the login credentials. 
Firefox uses triple DES for encryption of credentials. 
Firefox’s security flaws in it’s password manager are well-known (Weak SHA-1, easily accessible locations for storing encrypted data). 
With modern GPUs getting really powerful, SHA-1 can be easily broken. 
Breaking a more advanced SHA-256 hash is also possible thanks to GPUs and high speed internet. 
To add to this, entering passwords is often cumbersome, sharing access with others isn’t possible (Without sharing the actual passwords).

The aim of this project is to build a system that eliminates security issues related to storing encrypted credentials locally, makes sharing logins easy, and uses smartphone’s biometric sensors as the basis of security in password management. 
The idea is to use Samsung knox as basis of AES256 encryption using the DRK provided by samsung. The Knox container is secured by user biometrics, thereby making passwords protected by 2 layer security.
The passwords stored on Smartphone are shared with device trying to Login using end to end encrypted TLS MQTT connection.
