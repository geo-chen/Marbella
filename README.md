# Marbella Dashcam

## Finding 1: Same default credentials and limited password combinations
All dashcams were shipped with the same default credentials of 12345678 which creates a "insecure-by-default" setup. For users who change their passwords, it's limited to 8 characters. According to https://www.protiviti.com/sg-en/blogs/6259-8-character-password-still-dead, a 8-char password takes a maximum of 8 hours to be cracked on an AWS box.

## Finding 2: Video recordings open to being downloaded via ports 7777, 7778, 7779
Once access is gained either by default, common, or cracked passwords, the video recordings containing sensitive routes, conversations, footage, are open for downloading by creating a socket:
![image](https://github.com/user-attachments/assets/1f5b3387-7c7e-430f-af30-7bbc2014ee7e)


## Finding 3: Settings can be changed without any other forms of authentication
Via port 7777 without any need to pair or press a physical button, a remote attacker can disable recording, delete recordings, or even disable battery protection to cause a flat battery to essentially disable the car from being used. While all these settings are changed, there are no indications or sounds on the dashcam to alert the dashcam owner that someone else is making those changes. 
![image](https://github.com/user-attachments/assets/fa22d747-31ce-416a-b3e2-f868b3e63e54)


## Finding 4: Passwords are stored in plaintext and can be retrieved with physical contact
When a new SD card is popped into the dashcam, the existing password is written onto the SD card in plaintext automatically. An attacker with temporary access to the dashcam can switch SD card to steal password.
![image](https://github.com/user-attachments/assets/eeb6ce65-040e-4ddf-b818-bcee894ddeba)

![image](https://github.com/user-attachments/assets/65924e4a-9656-49e7-91f4-b598aeccc3bf)


