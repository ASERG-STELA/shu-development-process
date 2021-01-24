# Level 4 Git Tools

## 1. Abstract

This document will walk through some examples of how to integrate Git into your development environment. At Level 4, you will be using Visual Studio 2019 and IntelliJ IDEA for your projects. Therefore the following examples will be specific for these two IDE's.
Integrating Git into your IDE's is much more convenient than going directly through Github everytime you want to push or pull any changes from your repository.

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. Visual Studio 2019](#3-visual-studio-2019)
  - [3.1. How To Clone A Project](#31-how-to-clone-a-project)
  - [3.2. How To Push Your Project To Github](#32-how-to-push-your-project-to-github)
- [4. IntelliJ IDEA](#4-intellij-idea)
  
## 3. Visual Studio 2019

As you will be predominantly coding in C# at Level 4, Visual Studio 2019 will be the best IDE to use for creating and editing your code. It will be of great benefit to you to integrate Git with this IDE, and it is very easy to do so.
I will now walk through how to integrate Git within Visual Studio 2019.

## 3.1. How To Clone A Project

1. Get the Github URL of the project that you wish to clone. From Github you can click the green **Code** button:

![Get the Github URL of project](/planning/version-control/images/clone1.png)

2. Open Visual Studio 2019. Select **Clone a repository**:

![Select clone repository](/planning/version-control/images/clone2.png)

3. Paste the URL in **Repository Location**
4. Locate the path of the project to be saved on your computer
5. Click the **Clone** button:

![Click clone](/planning/version-control/images/clone3.png)

## 3.2. How To Push Your Project To Github

1. From Visual Studio 2019, go to the right bottom of the screen. You can see **Add to Source Control**. Select Git:

![Add to source control](/planning/version-control/images/push1.png)

2. This panel will be prompted. If there is no Team Explorer panel, go to **View** -> **Team Explorer**. Then select **Publish to Github**:

![Panel will be prompted](/planning/version-control/images/push2.png)

3. You might get a login window for Github if using Github on visual studio for the first time (or Github not connected), login if so.

4. If there are changes made to the project, you need to update your project repository.  Select **Changes**:

![Making changes to repository](/planning/version-control/images/push3.png)

5. Input the message/hint of the changes and hit **Commit All** button, a dialog box will be prompted, select **Yes**.

6. Now, you need to push the changes to Github. Select **master** from the right bottom of the screen, then **Push**:

![Push changes to Github](/planning/version-control/images/push4.png)

7. Login to you Github account, and check whether the changes have been updated to your repository.

## 4. IntelliJ IDEA

IntelliJ IDEA is the IDE we recommend for use with Java development, this IDE can also be integrated with Git. I will now walk you through how to set up Git with IntelliJ for use with your Java projects.

