# Level 4 Git Instructions <!-- omit in toc -->

## 1. Abstract

This document will serve to provide you with instructions on how to use Git and Github as version control for your projects. Version control allows developers to keep track of their projects and have all files/folders/source code all in one place. It is particularly useful for teams of developers but is also useful for individual work.
For Level 4 students and for future reference for other Levels, this document will explain the basics, including creating an account, repositories, adding files/folders, pushing/pulling and editing and committing changes.

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. Creating an Account](#3-creating-an-account)
- [4. Repositories](#4-repositories)
- [4.1. Creating a Repository](#41-creating-a-repository)
- [5. README File](#5-readme-file)
- [6. Adding Files and Folders](#6-adding-files-and-folders)
- [7. Editing and Committing Changes](#7-editing-and-committing-changes)
- [8. Push and Pull](#8-push-and-pull)
- [9. Downloading and Cloning](#9-downloading-and-cloning)
- [10. Workflow](#10-workflow)
- [11. Tools](#11-tools)
- [Downloading Git Kraken](#downloading-git-kraken)
- [12. References](#12-references)

## 3. Creating an Account

In order to first start using Github, you will first need to create free Github account:

1. Go to <https://github.com>.
2. On the starting page, click ‘Sign up for GitHub’
3. Fill out all fields and complete the puzzle, then press ‘Create account’
4. Use these details when logging in after this point

## 4. Repositories

A repository is often used to organise a single project. Often called a ‘Repo’, repositories can contain anything that your project could need:

- Folders and files including source code
- Images and videos
- Spreadsheets
- Datasets
- Any other documents you need for your project

## 4.1. Creating a Repository

Follow these steps to create your own repository, this is based on reference [1]:

1. In the upper right corner, next to your avatar or identicon, click and then select **New repository**
2. Name your repository
3. Write a short description
4. Select **Initialize this repository with a README**
5. Click **Create repository**

## 5. README File

When you first create a repository a README.md file is created. This is simply a text file where you can write a description of you project or any other information relating to your project. This is often written in Markdown which is similar to HTML with its use of header tags which can be done using the ‘#’ key. It is encouraged to edit your README file to begin with, especially if you are showing the project or repository to others.

## 6. Adding Files and Folders

You are now ready to start your project! Once you have created your project (and perhaps made some progress), you will want to upload all the folders and files required to run your project on other machines. Follow these instructions to add in the files for your project:
1.	Select the repository you would like the files uploaded to
2.	Click **Add file**
3.	Click **Upload file**
4.	Go to the directory of your project in your file structure, and drag in your project folder, or click **Choose your files** and select the files you want to upload
5.	Your files should now be added, scroll down to the bottom to **Commit changes**
6.	Add in a description of your changes where it says **Add files via upload**, this will be the default message if you chose not to change it. 
7.	Leave **Commit directly to master branch** clicked (more on branching at Level 5)
8.	Click **Commit changes**

## 7. Editing and Committing Changes

As well as uploading files, you can also edit the content of existing files inside of a Github repository. You can edit text files such as README’s, as well as source code. The following instructions will guide you on how to edit source code and commit the changes in Github, without the need to use a code editor or IDE. You **MUST** remember to pull the changes to the files you change if you wish to continue editing the code in your code editor (more on this later): 
1.	Open your repository and the file you wish to edit 
2.	Click the **pencil** icon to edit the content
3.	Make the changes you wish to make
4.	Scroll down to the bottom to **Commit changes**
5.	Add in a small description of what you changed
6.	Click **Commit changes**. Your file will now be updated and the time of the commit logged

## 8. Push and Pull

Pushing and Pulling are used to upload and retrieve code from Github, usually directly through the code editor terminal or GitKraken. ‘Push’ is used to push the changes you have made to your code in the editor onto Github without needing to reupload the full file. 

‘Pull’ is the opposite, it is used to retrieve code from Github using the terminal or GitKraken in order to update your code in your editor. This is used to ensure you always have the most up to date version of your code (very useful for collaboration). 

## 9. Downloading and Cloning

If you are not using GitKraken, there are two options available to you to retrieve your files and code from Github. The simplest being to download the project as a ZIP folder:
1.	Navigate to your repository
2.	Click the green **Code** button just above your file structure
3.	Click **Download ZIP**. Your project will then download and you will be free to use it as you please

Cloning is another way to retrieve your files from Github, this is done through your IDE and avoids the need to download the files each time:
1.	Launch your IDE (Visual Studio 2019)
2.	Navigate to the section where you create or open a project (on the right in VS 2019), there should be a section saying Clone or check out code:
3.	Click **Clone or check out code** it should now ask for a Git repository URL
4.	Navigate to your required repository in Github
5.	Click the green **Code** button just above your file structure
6.	You should see a URL under **HTTPS**, copy this
7.	Paste the URL into the box from step 3
8.	Click **Clone**, the project will now appear in the IDE and you can edit it as you please

## 10. Workflow

Building on the sections above, it is important to be able to integrate them all together in one project. To do this, you will need to follow a workflow, essentially a strategy you will adopt to work on your project. There are many different workflows you can use, although the best workflow will often be the one you and your team find the most useful, which you may find you create yourselves.

For Level 4, we recommend you follow a basic flow for your projects, with two branches, **main/master** and **development**. This is shown by the following image:

![Basic flow. By Buddy](/lifecycle/planning/version-control/images/Basic_flow.PNG)

*Fig. 1: Structure for basic flow.*
<span>Photo by <a href="https://buddy.works/blog/5-types-of-git-workflows">Buddy</a> on <a href="https://buddy.works/blog/5-types-of-git-workflows">Buddy Works</a></span>

This structure is based on reference [2]

This figure shows the structure of basic flow that you should follow for Level 4. Everyone should work on the development branch, with the main branch always ready to run with the most up to date version of your code. You should also use **tags** on the main branch to identify the release version; once a change from the development branch is merged with the master branch. This will ensure a simple, clean structure for your project with a clear history of your release versions. This workflow is most suitable for small projects, once you start to work on larger projects, you will need to build on this workflow (more on this at Level 5 and 6).

## 11. Tools

## Downloading Git Kraken

This step is optional. GitKraken is a free Git GUI that should be available on all University machines. It essentially performs the same functions as Github, in fact, they are integrated. Any changes you make in GitKraken get pushed to Github. In order to download GitKraken on your own machines, simply visit gitkraken.com to download for free and follow the instructions on the website.

## 12. References

[1] Hello World. Getting started with github. <https://guides.github.com/activities/hello-world/>.

[2] Basic Flow. 5 types of Git workflows that will help you deliver a better code. <https://buddy.works/blog/5-types-of-git-workflows>.
