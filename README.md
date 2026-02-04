# Hacking Lab: Assignment 1
**Student:** Suprim Karki
##  Summary
**Karvinen 2021: Install Debian on Virtualbox**
* **Guest Additions:** The most important step is installing Guest Additions. It fixes the small screen resolution and lets you copy-paste between Windows and Linux.
* **Live CD:** It is better to download the "Live" version of Debian. This lets you test the desktop environment before you actually install it to the hard disk.
* **Sudo:** On a fresh install, your user might not be in the sudo group. You have to add yourself manually or use su - to become root.
* *My thought:* It is annoying that VirtualBox doesn't just work perfectly out of the box, but it's cool that it's free.

**Karvinen 2020: Command Line Basics**
* **Navigation:** You only really need three commands to move around: pwd (print working directory), ls (list files), and cd (change directory).
* **No Undo:** The rm command is dangerous. There is no trash bin in the command line. Once you delete a file, it is gone forever.
* **Tab Key:** The tab key is the best tool. It auto-completes filenames so you don't make typing mistakes.
* *My question:* Why do some commands require -r (recursive) to delete folders, but rmdir only works on empty ones?

## a) Can't Fish
I proved network isolation works.

**1. Internet Connected**

<img width="1440" height="900" alt="Screenshot 2026-02-04 at 16 24 08" src="https://github.com/user-attachments/assets/dc3e1c7c-d89c-4fb6-8849-d1f3db36131c" />


**2. Internet Disconnected**
I disabled the adapter and ping failed.
<img width="1440" height="900" alt="Screenshot 2026-02-04 at 16 23 00" src="https://github.com/user-attachments/assets/9b1cc8b3-12fe-4d9a-ac6f-48501fa87f1f" />


## b) Port Scan (Localhost)
I scanned my computer with no internet.

**Command:** sudo nmap -A localhost

<img width="1440" height="900" alt="Screenshot 2026-02-04 at 16 37 53" src="https://github.com/user-attachments/assets/ca517ad1-8f99-48a6-aaf4-c4d7ea01a323" />






## c) Daemon Scan
I installed Apache (sudo apt-get install apache2a) and scanned again.

**Command:** sudo nmap -A localhost
<img width="1440" height="900" alt="Screenshot 2026-02-04 at 16 41 04" src="https://github.com/user-attachments/assets/57dab508-c38b-4dc4-ac82-8158965d4f5d" />


**Analysis:**
Now Port 80 is OPEN because the web server is running.


## d) Bandit Levels
**Level 0->1:** cat readme
<img width="1440" height="900" alt="Screenshot 2026-02-04 at 16 54 53" src="https://github.com/user-attachments/assets/e3b85809-09e7-465d-bb24-c1682fbcc025" />

**Level 1->2:** cat ./-

<img width="1440" height="900" alt="Screenshot 2026-02-04 at 17 09 55" src="https://github.com/user-attachments/assets/9ab24749-9b1d-4ba2-bbba-18661d31816a" />

**Level 2->3:** cat "spaces in this filename"
<img width="1440" height="900" alt="Screenshot 2026-02-04 at 17 23 58" src="https://github.com/user-attachments/assets/d5f7ac48-24a2-478f-a802-cc2fe0b2fe88" />


**Level 3->4:** cat .hidden

<img width="1440" height="900" alt="Screenshot 2026-02-04 at 17 38 42" src="https://github.com/user-attachments/assets/28a7a50c-b38f-4853-b36d-4e6c72089813" />

**Level 4->5:** file ./* then cat ./file07
<img width="1440" height="900" alt="Screenshot 2026-02-04 at 17 44 54" src="https://github.com/user-attachments/assets/489499c3-6b3a-44f7-9f9a-11bdea91ab5a" />

## References
1. Karvinen, Tero (2021): *Install Debian on Virtualbox - Updated 2024*. Retrieved from [https://terokarvinen.com/2021/install-debian-on-virtualbox/]
2. Karvinen, Tero (2020): *Command Line Basics Revisited*. Retrieved from [https://terokarvinen.com/2020/command-line-basics-revisited/](https://terokarvinen.com/2020/command-line-basics-revisited/)
3. OverTheWire Community (2024): *Bandit Wargame*. Retrieved from [https://overthewire.org/wargames/bandit/]
