# Marbella Dashcam

Product: Dashcam

Models: KR8s, KRX

Product URL: https://makagps.com/

## Finding 1 - CVE-2025-30125: Same default credentials and limited password combinations
**Description**: All dashcams were shipped with the same default credentials of 12345678 which creates a "insecure-by-default" setup. For users who change their passwords, it's limited to 8 characters. According to [research](https://www.protiviti.com/sg-en/blogs/6259-8-character-password-still-dead), a 8-char password takes a maximum of 8 hours to be cracked on an AWS box.

**Vulnerability Type**: Insecure Permissions

**Vendor of Product**: Marbella

**Affected Product Code Base**: KR8s, KRX

**Affected Component**: Weak password strength

**Attack Type**: Remote

**Impact Code execution**: False

**Impact Information Disclosure**: True

**Attack Vectors**: It is not difficult for a remote attacker to crack a weak 8-char wifi password.

**Has vendor confirmed or acknowledged the vulnerability?**: No


## Finding 2 - CVE-2025-30127: Video recordings open to being downloaded via ports 7777, 7778, 7779
Once access is gained either by default, common, or cracked passwords, the video recordings containing sensitive routes, conversations, footage, lack any forms of authentication and are open for downloading by creating a socket:
![image](https://github.com/user-attachments/assets/1f5b3387-7c7e-430f-af30-7bbc2014ee7e)

**Vulnerability Type**: Insecure Permissions

**Vendor of Product**: Marbella

**Affected Product Code Base**: KR8s, KRX

**Affected Component**: Unauthenticated downloading of sensitive media files

**Attack Type**: Remote

**Impact Code execution**: False

**Impact Information Disclosure**: True

**Attack Vectors**: A remote attacker nearby can connect to the dashcam and dump all sensitive media files.

**Has vendor confirmed or acknowledged the vulnerability?**: No

## Finding 3 - CVE-2025-30126: Settings can be changed without any other forms of authentication
Via port 7777 without any need to pair or press a physical button, a remote attacker can disable recording, delete recordings, or even disable battery protection to cause a flat battery to essentially disable the car from being used. While all these settings are changed, there are no indications or sounds on the dashcam to alert the dashcam owner that someone else is making those changes. 
![image](https://github.com/user-attachments/assets/fa22d747-31ce-416a-b3e2-f868b3e63e54)

**Vulnerability Type**: Incorrect Access Control

**Vendor of Product**: Marbella

**Affected Product Code Base**: KR8s, KRX

**Affected Component**: Unauthenticated configuration change

**Attack Type**: Remote

**Impact Code execution**: True

**Impact Information Disclosure**: True

**Attack Vectors**: A remote attacker nearby connect to the dashcam and make unauthorised changes to the dashcam's configurations without alerting the dashcam owner or pressing any physical pairing button on the dashcam.

**Has vendor confirmed or acknowledged the vulnerability?**: No

## Finding 4 - CVE-2025-30124: Passwords are stored in plaintext and can be retrieved with physical contact
When a new SD card is popped into the dashcam, the existing password is written onto the SD card in plaintext automatically. An attacker with temporary access to the dashcam can switch SD card to steal password.
![image](https://github.com/user-attachments/assets/eeb6ce65-040e-4ddf-b818-bcee894ddeba)

credits: Chee Peng

![image](https://github.com/user-attachments/assets/65924e4a-9656-49e7-91f4-b598aeccc3bf)

**Vulnerability Type**: Incorrect Access Control

**Vendor of Product**: Marbella

**Affected Product Code Base**: KR8s, KRX

**Affected Component**: Exposed passwords in plaintext

**Attack Type**: Physical

**Impact Code execution**: False

**Impact Information Disclosure**: True

**Attack Vectors**: An attacker with temporal physical access to the dashcam, with or without the SD card, can obtain the dashcam's wifi password in plaintext.

**Has vendor confirmed or acknowledged the vulnerability?**: No


## Disclosure Timeline
23 Feb 2025 - Disclosed to Marbella

24 Feb 2025 - Forwarded disclosure to Marbella's country office

7 Mar 2025 - Final follow-up email sent

