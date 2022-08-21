# Windows configuration

## git installation

- Option 1: Install from winget (recommended)

  ```
  winget install --id Git.Git -e --source winget
  ```

- Option 2: Install from installer file.
  > 1. Visit [here](https://git-scm.com/download/win)
  > 2. Other Git for Windows downloads > Standalone Installer > 64-bit Git for Windows Setup.

## verify installation

1. Open command promt from windows search.
2. run following command `git --version`
3. you should get optput like `git version 2.33.1.windows.1`

You might need to restart you computer after installation if you use powershell.

# configuere user

```
git config --global user.name "<your full name>"
git config --global user.email “<valid-email>”
```

## Setup SSH connection

1. launch git bash from windows search and run the following commands
   ```
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   Press enter everytime it asks for any input.You don't need to worry about it.
   Now continue.
   ```
   eval $(ssh-agent -s)
   ssh-add ~/.ssh/id_rsa
   cat ~/.ssh/id_rsa.pub
   ```
2. Copy the text got after running the previous command you need it later this config.
3. Login to your github account.
4. now go to [https://github.com/settings/ssh/new](https://github.com/settings/ssh/new)
5. Now Paste the previously copied text in `key` box and give a unique title.
6. if you lost the key you messed up.
   No don't worry I was just kiddin. run command ` notepad ~/.ssh/id_rsa.pub` and get the text.

7. Now open cmd again and run the command

   ```
   ssh -T git@github.com
   ```

   now type ``yes` if it asks for any input. <br>
   result shoud be some thing like this

   > Hi username! You've successfully authenticated, but GitHub does not provide shell access.

8. If everything goes as followed you are good to go otherwise you are fucked up.

<br><hr><br>

# Git config for linux

## installation

- on debian/ubuntu distro based - `sudo apt install git`
- on arch based distro - ` sudo pacman -S git`
- On fedora based distro - ` sudo dnf install git`
  <br>By the way I use manjaro and Linux Mint.

## configuire git

```
# name
git config --global user.name "$name"
# email
git config --global user.email "$email"
```

## set up ssh

1. generate key

   ```
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

   press enter three times

2. copy genereted key after running the following command

   ```
   cat ~/.ssh/id_rsa.pub
   ```

3. copy the content and visit [https://github.com/settings/ssh/new](https://github.com/settings/ssh/new)

4. Now Paste the previously copied text in `key` box and give a unique title.

5. Attempts to ssh to GitHub

   ```
   ssh -T git@github.com
   ```

   Type `yes` and press enter if it asks for input.

   Result should be something like.

   > Hi username! You've successfully authenticated, but GitHub does not
   > provide shell access.

If everything goes as followed you are good to go otherwise you are linus user fix this by yourself.
