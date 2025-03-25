# Kaiwen-Tao-Lab-5

## Task 0: Declare your AI Usage

Refer to the PDF in the repo.

## Task 1: Github Skills

![Task 1](https://github.com/user-attachments/assets/25f39786-69c8-4395-b158-2c6a31e62687)

![Task 1 game](https://github.com/user-attachments/assets/2260d154-aac8-4b57-9457-390959287421)

![Task 1 js](https://github.com/user-attachments/assets/c93fa7bb-563d-4bec-88ec-74803508dbf7)

## Task 2: Github Video + Questions

### `git commit -am “this is a test”`

We use git add. and git commit to save a copy of the code when we want to commit a change to a local file. The command git commit -am "this is a test," on the other hand, can combine the two into one. The -am in the command will do the work of git add. Also, the quotation mark will be the commit message for this commit.

### `git commit --amend`

You can change the message of the last commit with git commit --amend.  If there is a typo in the last commit message, it could make the message confusing, which would make it hard to find the change at that point. You can also add new files to the last commit by using the --amend flag after git add. After making changes to the commit, add a quote mark at the end like this: git commit --amend "new commit message."

### `git stash`

git stash will remove the changes from your current working directory and save them for later use without committing them to the repo. After saving it, use git stash pop to add those changes back. If there is a lot of different code that you want to save, then we can use "git stash save" with a name after in the quote marks, like "git stash save "NAME" to reference. Then use "git stash list" to find all the stashes and use git stash apply to add those changes back according to the reference content. If you are using GitHub Codespace, then those stashes you save will be saved in the cloud.

## Task 3: Docker Videos + Questions

### Q1 Why are Docker images made up of layers, and how does the layering structure benefit the process of building images?

The main reason Docker images are layered is to improve the reusability and maintainability of the image. Layering allows for partial updating of the image, as the result of layering is that you only need to update the layer in which the change occurs, while the other layers can remain unchanged. Of course, if there is a problem with one layer, that layer can be easily replaced or repaired without affecting the functionality of the other layers. This can greatly reduce the size of the mirror and improve the transmission speed and storage efficiency of the mirror. 2. Of course, it is also possible to realize a template like a base image, which can be shared by multiple applications, so as to avoid repeated construction of the same image, reducing the waste of resources.

### Q2 What is the purpose of a Dockerfile in creating a Docker image? Using own words, explain in 2-3 sentences.

A Dockerfile is a text file that contains all the instructions for building a Docker image. The text in the Dockerfile contains a list of commands and instructions needed to build the image. By defining a set of commands and parameters, the Dockerfile directs Docker to build a custom image. So Dockerfile is essential for creating Docker images.

### Q3 List and briefly explain the basic instructions used in a Dockerfile for building a `Node.js` Docker image.

The first layer of the image is to add the parent image by first typing FROM followed by the name of the node's parent image, which can be found by searching Node in DockerHub to find the parent image you need.The FROM command specifies the base image, which is the starting point for building the image and is used for subsequent commands to build. Then, on top of the first layer, we can add our own additional layers, the next layer will be all the dependencies that we need to install in the image, and for that we need to use the RUN command, which will execute commands in the image during the build process. The commands we specify will be run after the image is built. However, in some cases, since the command will be run in the root directory of the image, it will not be able to access the other files in the folder and will not be able to run. Therefore, we must specify a working directory for the image using WORKDIR, which sets up the working directory within the container where all subsequent commands will be executed, and CMD, which specifies the default command to be used when the container is created. Finally, we need the EXPOSE command to declare the port on which the container will listen when running.
