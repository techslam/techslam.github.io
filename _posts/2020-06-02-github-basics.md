---
title: "Basics of Git and Github"
date: 2020-06-02 19:00:00 +0100
categories: [Git, Github]
tags: [git]
---
Git and GitHub are the tools that are used by most developers and software companies for the purpose of version controling the software codes in a repository and collaborate with other developers

This post is all about the basics of Git and Github which will help you understand what Git is all about.

## What is Git ?

Git is a free and open source version control system. A version control means to manage the changes to a software code. So it basically mean we can save an initial version of the code into the Git and if there are changes to the code, we can save it again into the Git. We can change and update the code 'n' number of times and save it in the Git, and Git helps us to look back and see all of the code changes made through out the time. This helps to track down a bug or if required revert back to a previous version of the code.

***

## Common Terminology

**Directory** : This is a folder on the computer.<br/>
**Terminal/Command Line** : Application that runs on the computer which is an interface for the text commands.<br/>
**CLI** : Command Line Interface - Most computer programs provides CLI to interact with the program using text command lines.<br/>
**cd** : Change Directory in the command Line.<br/>
**Repository** : A project, or the folder where all your codes and softeare files are placed.<br/>
**Github** : A website to host the respositiories online.<br/>

***

## Common Git Commands

**Clone** : Bring a repository that is hosted somewhere like Github into a folder on your local machine.<br/>
**Add** : Track your files and changes in Git<br/>
**Commit** : Save the changed or newly created files into Git<br/>
**Push** : Upload Git commits to a remote respositiory , like Github<br/>
**Pull** : This is the opposite of Push , where we can download the changes in remote repository to your local machine.

***

## Signup for Github

Go to <https://github.com/join/> and enter the details requested and create a Github account. You will receive an email to verify your email address. After you login to the Github, you will be directed to your dashboard where you can see a button to create a 'New Repository. Repository will be the root folder for your project where you will be saving all the code files, and any other related files for your project.

![Desktop View]({{ "/assets/img/git-basics/github-home-page-new-repo.png" | relative_url }})

***

## Create a New Repository

Click on the 'NEW' button and fill in the Repository Name & Description and leave the rest as is.

![Desktop View]({{ "/assets/img/git-basics/new repo create page.png" | relative_url }})

We can create the required files for this Repo/Project locally on the machine or we can also do that from the editor of the Github. As an example , We will create a README.md file for this newly created git-basics repo.

![Desktop View]({{ "/assets/img/git-basics/create-new-file link highlight.png" | relative_url }})

We will enter the new file name as README.md and add some details into the file :

And scroll down to the bottom to save(or commit) this file.

We can see that there is a placeholder text called 'Create README.md' which is the default commit message. If required we can change this to meet our requirements. For now we will leave the default message as is and click on 'Commit new file'

![Desktop View]({{ "/assets/img/git-basics/commit new readme file.png" | relative_url }})

Once commited, Github will take us back to the Repo and show the newly created file with appropriate commit message.

![Desktop View]({{ "/assets/img/git-basics/after create file screen.png" | relative_url }})

And then we can click on the README.md file and right hand side there is an option to edit this file. We can now edit this file and make some changes and scroll down to now update the README.md file.

![Desktop View]({{ "/assets/img/git-basics/updated line for readme.png" | relative_url }})

In the commit file option , we can see that the default commit message is now 'Update README.md'

![Desktop View]({{ "/assets/img/git-basics/commit the updates for readme.png" | relative_url }})

When we go back to the repo home page , we can see that the README.md file is now having the last commit message shown as 'Update README.md'
We can also see that there are '**2 commits**' done to this Repo. When we click on the '2 commits' , it will shopw us the entire history of the changes done to this README.md file.

![Desktop View]({{ "/assets/img/git-basics/update commit and 2 commit.png" | relative_url }})

Each of the commits will have a unique identifiers and the commit message titles. We can click on them and can see the changes that has been made to the file through these commits. A '**+**' green line indicates new changes that was added. A '**-**' red line indicates the line was removed. When an existing line is updated , it will show as deleted line in red(removed) and updated line in green(being added).

Next , we will clone this project into our local machine. For this we need to ensure we have 
git installed in our machine. If you are using a MAC or Linux , you will already have git pre installed. You can check this by opening a Terminal and run below command -

`git --version`

If you need to install Git , please check <https://www.atlassian.com/git/tutorials/install-git/>

Lastly , I am using Microsoft Visual Studio Code as my preferred code editor. This is free code editor and is widely used by developers. You can download this from <https://code.visualstudio.com/> and is available in every major operating system.

***

## Git Clone

We are going to download the repository that we created in my Github account into my local machine and to do this we would use the `git clone` command.

![Desktop View]({{ "/assets/img/git-basics/git clone terminal image.png" | relative_url }})

Now in the VisualStudio Code, We can add this folder and see the only file that we had created from the github website, which is the README.md

![Desktop View]({{ "/assets/img/git-basics/visual studio code readme.png" | relative_url }})

Now there is another file which is a hidden file called '**.git**' which is an indication that this repositiory is version controlled by the git and we should be able to use all sorts of git command on this repo. We can see this hidden folder by just running the `la` command on the terminal. This '.git' is a folder which stores all of the files that saves all of your commits/code changes over the time. It has all of the changes recorded in the history of this repo which includes the one that we made in github.com

***

## Git Status

Next , We are going to make some changes to the only file that we have in this repo.

And then we run the below command to see the current status of our repo -

![Desktop View]({{ "/assets/img/git-basics/git status 1.png" | relative_url }})

We can see that the README.md is in red colour and the message says 'Changes not staged for commit'

*** 

## Git Add

Next, We are going to create a new file from the editor and call it as 'home.html' and add some contents to it. And then again we will check the status by running `git status`

![Desktop View]({{ "/assets/img/git-basics/vscode home page.png" | relative_url }})

![Desktop View]({{ "/assets/img/git-basics/git status 2.png" | relative_url }})

Here , We can see that the 'home.html' is showing up, however with a different message that is 'Untracked files.' This means Git doesn't know about this new file yet. So before we can save this file into the Git , we need to tell the Git to track this file first. And this can be done using the `git add` command. There are two options that we could use along with `git add` command as below :<br/>
`git add .` => This will stage both the updated and the new file.<br/>
`git add home.html` => This will only stage the new file.

![Desktop View]({{ "/assets/img/git-basics/git add .png" | relative_url }})

Now both the files are staged and can be seen in green colour and they are ready to be comitted.

***

## Git Commit

We can use `git commit` command to now save these changes into the Git. 

![Desktop View]({{ "/assets/img/git-basics/git commit 1.png" | relative_url }})

This commit is done only on the local machine and is not live yet in the github web respositiory. 

***

## Git Push

Inorder to make the changes/commits made in the local machine live on the github web repo, we need to use another command called `git push` which means we are pushing this live to a remote repository where the project is actually hosted.

Inorder to push this to github remote repo, we would need to tell the github that we are the owner of the account. To this we need to connect the local machone to github account somehow. This can be achieved using the **SSH KEYS**.

Follow below article to generate a new ssh key and then how to add it to the github account.
<https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent>

Once the ssh-keys is all in place, we can continue on to `git push` command.

`git push origin master`

Origin is an option set for us and basically indicates the location of the remote git repositiory. Master indicates the branch that we want to push to.

![Desktop View]({{ "/assets/img/git-basics/git push 1.png" | relative_url }})

Now when we refresh the github website repository , we can see the changes that we made locally are live and also can see total commit count is now 3. 

So far what we did was created a repository using github and then cloned it locally and then made changes locally and finally pushed those changes back to remote github repo.

***

## Local Repo

Next , we can see how to create a repository locally and then push them onto github website.

To do this , Let's create a new folder in visual studio code and name it as **git-basics2**. Then navigate into this new folder and run `la` command and we would not see the '.git' folder. This is because this is not yet initialised to be version controlled using git. Next, Let's create a new README.md file and add some texts into it.

![Desktop View]({{ "/assets/img/git-basics/gitbasics2 folder.png" | relative_url }})

Next , inorder to intialize git version controlling into this new project, we need to use `git init` command.

![Desktop View]({{ "/assets/img/git-basics/git init.png" | relative_url }})

Next , we can run the `git status` , `git add`, `git commit` commands as seen earlier. And finally we can try to push this to github and see what happens -

![Desktop View]({{ "/assets/img/git-basics/git push new repo.png" | relative_url }})

This will be giving us an error **fatal: 'origin' does not appear to be a git repository**.
Because we did not clone this new repository from github and created the repo locally, git is complaining as it does not know to which remote repository the code needs pushed to. So we need to manually create an empty repository in github and create the connection. Once the empty repository is created in the Github , we can use the link to create the remote origin in the git.
And then we can also check what remote repository this project is connected to aswell.

![Desktop View]({{ "/assets/img/git-basics/git remote check.png" | relative_url }})

Now that we have established the connection with a remote repositiory, we can go ahead and perform the `git push`

![Desktop View]({{ "/assets/img/git-basics/git push new repo success.png" | relative_url }})

Now when we refresh the github website, we can see the push has been succesfull and is now live.

So this is how we initialise a project locally and then push it to the remote repository like Github.

***

Next we will discuss about - 

## Git Branching
TBC
## Git Merging
TBC







