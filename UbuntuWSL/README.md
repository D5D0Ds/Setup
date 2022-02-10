# Follow the steps to setup Ubuntu in WSL.

*The steps to be followed are:*

1. Install Ubuntu from the Microsoft Store.

2. Open the Ubuntu in Windows Terminal.

3. Setup username and password.

4. Update the Ubuntu using:
```
sudo apt update && sudo apt upgrade -y
sudo apt-get install build-essential -y
```

## ***(Optional)*** To silent the password for Ubuntu, follow these steps:

1. Open sudoers file.
```
sudo visudo
```

2. Edit, and add the line mentioned below, save the file and exit.
```
d5d0ds ALL=(ALL) NOPASSWD:ALL
```

3. In the terminal, provide sudo priviledge the your username.
```
sudo passwd -d `whoami`
sudo chown -R ${LOGNAME}:staff $HOME
```

4. The format for next line is 
- sudo usermod -aG sudo username
    - If your username is ***"d5d0ds"***, then write 
        ```
        sudo usermod -aG sudo d5d0ds
        ```