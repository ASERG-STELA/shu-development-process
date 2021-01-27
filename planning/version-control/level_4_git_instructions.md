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
  - [4.2. README File](#42-readme-file)
- [5. Adding Files and Folders](#5-adding-files-and-folders)
- [6. Editing and Committing Changes](#6-editing-and-committing-changes)
- [7. Push and Pull](#7-push-and-pull)
- [8. Downloading and Cloning](#8-downloading-and-cloning)
- [9. Workflow](#9-workflow)
- [10. Tools](#10-tools)
- [11. References](#11-references)

## 3. Creating an Account

In order to first start using Github, you will first need to create free Github account:

1. Go to <https://github.com>.
2. On the starting page, click **Sign up for GitHub**
3. Fill out all fields and complete the puzzle, then press **Create account**
4. Use these details when logging in after this point

## 4. Repositories

A repository is often used to organise a single project. Often called a **Repo**, repositories can contain anything that your project could need:

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

## 4.2. README File

When you first create a repository a README.md file is created. This is simply a text file where you can write a description of you project or any other information relating to your project. This is often written in Markdown which is similar to HTML with its use of header tags which can be done using the ‘#’ key. It is encouraged to edit your README file to begin with, especially if you are showing the project or repository to others.

## 5. Adding Files and Folders

You are now ready to start your project! Once you have created your project (and perhaps made some progress), you will want to upload all the folders and files required to run your project on other machines. Follow these instructions to add in the files for your project:

1. Select the repository you would like the files uploaded to;
2. Click **Add file**;
3. Click **Upload file**;
4. Go to the directory of your project in your file structure, and drag in your project folder, or click **Choose your files** and select the files you want to upload;
5. Your files should now be added, scroll down to the bottom to **Commit changes**;
6. Add in a description of your changes where it says **Add files via upload**, this will be the default message if you chose not to change it;
7. Leave **Commit directly to master branch** clicked (more on branching at Level 5);
8. Click **Commit changes**.

## 6. Editing and Committing Changes

As well as uploading files, you can also edit the content of existing files inside of a Github repository. You can edit text files such as README’s, as well as source code. The following instructions will guide you on how to edit source code and commit the changes in Github, without the need to use a code editor or IDE. You **MUST** remember to pull the changes to the files you change if you wish to continue editing the code in your code editor (more on this later):

1. Open your repository and the file you wish to edit;
2. Click the **pencil** icon to edit the content;
3. Make the changes you wish to make;
4. Scroll down to the bottom to **Commit changes**;
5. Add in a small description of what you changed;
6. Click **Commit changes**. Your file will now be updated and the time of the commit logged.

## 7. Push and Pull

Pushing and Pulling are used to upload and retrieve code from Github, usually directly through the code editor terminal, GitKraken/Github Desktop or your development environment. ‘Push’ is used to push the changes you have made to your code in the editor onto Github without needing to reupload the full file.

‘Pull’ is the opposite, it is used to retrieve code from Github using the terminal, GitKraken/Github Desktop or your development environment, in order to update your code in your editor. This is used to ensure you always have the most up to date version of your code (very useful for collaboration).

## 8. Downloading and Cloning

If you are not using GitKraken, there are two options available to you to retrieve your files and code from Github. The simplest being to download the project as a ZIP folder:

1. Navigate to your repository;
2. Click the green **Code** button just above your file structure;
3. Click **Download ZIP**. Your project will then download and you will be free to use it as you please;

Cloning is another way to retrieve your files from Github, this is done through your IDE and avoids the need to download the files each time. In the [tools](/planning/version-control/tools/level_4_git_tools.md) guidance, we have showed an example with screenshots of how to do this:

1. Launch your IDE (Visual Studio 2019);
2. Navigate to the section where you create or open a project (on the right in VS 2019), there should be a section saying Clone or check out code;
3. Click **Clone or check out code** it should now ask for a Git repository URL;
4. Navigate to your required repository in Github;
5. Click the green **Code** button just above your file structure;
6. You should see a URL under **HTTPS**, copy this;
7. Paste the URL into the box from step 3;
8. Click **Clone**, the project will now appear in the IDE and you can edit it as you please;

## 9. Workflow

Building on the sections above, it is important to be able to integrate them all together in one project. To do this, you will need to follow a workflow, essentially a strategy you will adopt to work on your project. There are many different workflows you can use, although the best workflow will often be the one you and your team find the most useful, which you may find you create yourselves.

For Level 4, we recommend you follow a basic flow for your projects, using just the one branch, **Main/Master**, as you are likely to be working as an individual on most of your projects at L4. You will be introduced to branching and merging at L5 but for L4, this will suffice. You should try to use Github for all of your projects, even if it is just you working on them as they can be used to build a portfolio of work to bring to interviews after graduation or for placements.

The main branch should always ready to run with the most up to date version of your code, using **tags** to identify the release version. This workflow is very basic but will ensure a simple, structure for your project with a clear history of your release versions at Level 4. This workflow is most suitable for small projects, once you start to work on larger projects, you will need to build on this workflow (more on this at Level 5 and 6).

## 10. Tools

Git is integrated in many development environments, including the ones that you will be using at Level 4. These include:

* Visual Studio 2019
* IntelliJ IDEA
* Visual Studio Code

There is also a few Git GUI tools that are available to you, that may make it easier for you to use Git with your projects. Two of these we can recommend to you are:

* Github Desktop
* Git Kraken

We have prepared some walkthrough examples of how to integrate Git with the development environments above, as well as provided links to resources that can help you with VS Code, and the Git GUI tools in the tools guidance [here](/planning/version-control/tools/level_4_git_tools.md). 
We encourage you to look at this guidance to help you integrate Git with all of your projects. This will help you build a portfolio of work, that you can show interviewers when applying for placements and graduate jobs after University.

## 11. References

[1] Hello World. Getting started with github. <https://guides.github.com/activities/hello-world/>.
