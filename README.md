# GitHub Tutorial

_by Angel_

---
## Git vs. GitHub
 - Git is a system that tracks your changes within Software Development.

    -Pros:

        - Easy to use. Warns you of things such as deleting files (such as trash).

    -Cons:

        - Slow

 - GitHub is a version control platform that allows you to transfer code into the website. It keeps track of your respositories.

    -Pros:

        - Visually tracking changes. Able to collaborate with others. Stores codes in the cloud.

    -Cons:

        - Requires Git.


---
## Initial Setup

##### Making your Github Account

1. Go to Github, and make an account.
   - Enter an username, enter your email, and set up an password.
   - Select the Free Plan. Complete your setup, and then verify your email.

##### Setting up your IDE & Generating Your SSH

1. Go to ide.cs50.io
   -Log in VIA your Github Account.
2. In order to configure your account, enter this within the command line.

    `` git config --global user.email "you@example.com"``

     - Note: You'll need to use your email, so don't copy completely.
3. Then type : ``git config --global user.name "Your Name"`` into your command line

     - Note: Make sure you've cd into the right directory
4. Generating the SSH Key
     - Make sure you are in the root directory by doing cd ~
     - ``ssh-keygen -t rsa -b 4096 -C "you@example.com"`` then slowly press ENTER repeatedly until you see something similiar to this:


      -The key's randomart image is:
        +--[ RSA 4096]----+
        |       .o o..    |
        |       o +Eo     |
        |        + .      |
        |         . + o   |
        |        S o = * o|
        |           . o @.|
        |            . = o|
        |           . o   |
        |            o.   |
        +-----------------+

5. ``eval "$(ssh-agent -s)"`` starts the agent in the background

6. ``ls -al ~/.ssh`` you should now see a file named id_rsa.pub

7. ``cat ~/.ssh/id_rsa.pub`` then copy all of the result to your clipboard (it should start with ssh-rsa and end with your email address)

8. Then click [this link](https://github.com/settings/keys) It should bring you to GitHub Keys. Then press New SSH Key
    - Title: ide50
    - Key: paste your ssh key
    - Press the green Add SSH key button

9. Go back in your cs50 IDE. 
    - do ``sudo nano ~/.ssh/config``
10. Then paste the following:

        -Host github.com
        -Hostname ssh.github.com
        -Port 443

11. Exit by doing control+X , then press Y then ENTER
     - ssh -T git@github.com
     - Type yes, press ENTER, and you should see
>Hi "username"! You've successfully authenticated, but GitHub does not provide shell access. 

Why is the SSH Key Important? 
The reason why the SSH Key is important because it allows the computer or other programs to identify you. It is used for managing networks, operating systems, and configurations. 
It is also inside many file transfer tools and configuration management tools. It is important for us to use it because we need to transfer files etc from github to our CS50 IDE.

---
## Repository Setup
``mkdir`` - Allows you to make a directory.

``git init`` - Initializes git in your directory  (now called a repository) for version control - only do this once at the beginning  
- Note: In order to unintialize git you'll need to use ``rm -rf.git``

``git add "file name"`` - Once you've made changes to an file, you can use this command to add it. However it's only one single file.

``git add --all`` - You'll be able to add all the files you've changed, unlike ``git add "file name"``

After you've added your files, then you use ``git commit -m "any message you want"`` in order to commit any file.
You'll be able to go back to those changes whenever you want.




---
## Workflow & Commands



---
## Rolling Back Changes