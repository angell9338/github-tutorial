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


      The key's randomart image is:
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
`mkdir` - Allows you to make a directory.
  - You can remove an directory by using ``rmdir`` or ``rm``, however note that ``rm`` doesn't remove as well as ``rmdir``.

``git init`` - Initializes git in your directory  (now called a repository) for version control - only do this once at the beginning  
- Note: In order to unintialize git you'll need to use ``rm -rf.git``

``git add "file name"`` - Once you've made changes to an file, you can use this command to add it. However it's only one single file.

``git add --all`` - You'll be able to add all the files you've changed, unlike ``git add "file name"``

After you've added your files, then you use ``git commit -m "any message you want"`` in order to commit any file.
You'll be able to go back to those changes whenever you want.

##### How to remote: 
``git remote add origin URL``

``remote``: a connection between our current repository and an external one (that lives on github)

``add``: adds the remote repo (as opposed to editing or removing an existing one)

``origin`` this is our “nickname” for the remote repo.  “origin” is standard.
   - Note:In the future, you might need multiple remotes.
   
``URL``: the location of the remote repo.  Could be HTTPS or SSH

After you've set up your git remote, you're able to push and pull code or files from Github and into your commandline.

``git push -u origin master`` - 

- "push" - sending our commits from our local repo to our remote repo (up to the cloud: Github)

- "-u" - means “upstream.” This tells git to remember which remote repo & branch to push our changes to when we type git push in the future.

- "origin" - this is which remote we are pushing to

- "master" - the “main” branch of our project

---
## Workflow & Commands
Throughout working on your project in your repository, it's best to have a habit of
doing git status or git add etc during intervals so you won't lose anything. 

``git add`` - adds the current/entire directory: all files that have changed


``git status``

- Optional command to see which files have been edited since the last commit (it will be red)

- Optional (and recommended) command to see which files are staged for the commit( they will be green) (remember: press ↑ twice)


``git push`` - Send any changes from local repo “up” to the remote repo

``git pull`` - Brings any changes from the remote repo “down” to the local repo

---
## Rolling Back Changes

``git revert (a commit message)`` - revert back to the commit where you want

``git reset --soft HEAD~1`` - undo commit

``git reset HEAD filename`` - undo any changes made before you added

``git reset HEAD~1`` - reset both the commit and the add, basically going back to the edit.