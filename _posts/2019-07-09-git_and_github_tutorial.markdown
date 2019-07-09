---
layout: post
title:      "Git and GitHub Tutorial"
date:       2019-07-09 04:47:44 -0400
permalink:  git_and_github_tutorial
---


As I started in the data science program, I found using Git and GitHub extremely confusing.  It certainly doesn’t help that the names of both are very similar.  But what the heck were they and why do we need to use them in order to be a proficient data scientist?  Well, using both Git and GitHub is a must for any career in data science because of version control.  Version control allows a data scientist to integrate and record the coding changes (and file changes) from other collaborators.  This is important because employers want employees who understand this concept, and version control skills allow you to contribute to work and projects.  Also,  version control helps you connect with the data science community.  Version control is intertwined with Git and GitHub.

Let’s define what Git and GitHub are exactly.  **Git** is a version control tool that provides all of the basic functionality.  **GitHub** is a platform derived from Git and gives you and your team the necessary organization (i.e. – tracking, code review, etc.) for your projects.  Now that the general definitions are out the way, let's run through a hypothetical issue and how Git and GitHub would be used.

#### *Workflow overview*

In the workflow of a project, it begins with an **issue tracker**.  Think of an issue tracker as a trouble ticket.  An issue can be buggy code, some changes that need to be incorporated, or something along those lines.  A contributor to a project will have to work on any or multiple issues.  When you work on the issues, you create a new branch.

**Branches** compartmentalize your project and make them organized.  You’ll notice on Git that branches can be called the **master**.  The master branch holds the living version of your project.  When you branch from the master, that allows any contributor to make and test their changes independently of the master.  Once they are satisfied with the changes, they can combine or **merge** them into the master.

While working on your project, you’ll constantly make **commits**.  A commit keeps records of changes you make on your branch.  It shows the timeline of workflow changes.  Commits are great because they can be viewed by other collaborators in your team.  **Pull requests** are important to the workflow of the project.  Pull requests is a request to have the branch you’re working on integrated with the master branch.  Once the pull request is integrated or merged, it’s now a part of the project.  Pull requests shows whoever is conducting the pull requests what changes have been made against the master branch.  

#### *Operation*

Once you’re ready to start working on a project, you must **Fork** from the repository’s page on GitHub.  Forking the repo page essentially creates a copy or mirrors it, which will allow you to work on it.  Once the repo is forked, you’ll have to **Clone** it and copy the URL.  Now from Git, you’ll have to do a few steps in order to work on it.  Within Git, you’ll have to navigate to the correct directory where you’ll house your work.  This is done by typing cd along with the filepath name (i.e. – `cd filepath`).  Then type `git clone` along with the URL you copied (i.e. - `git clone URL`).  This will download all the info you forked and cloned from GitHub.  After this step, you can start making your changes within Jupyter Notebook.  Simply type `jupyter notebook` within Git and it will open Jupyter Notebook.  Now you can do whatever work is needed on the project in Jupyter Notebook.

After you’ve finished your work, its time to save them to the master branch.  This work will be done in Git.  Within Git, you’ll type `git status` which shows the changes that have been made to the branch you’ve worked on.  They show up in red font.  After this step, type `git add -A`.  This command is necessary as it commits the changes made the file.  To verify the changes have been made and saved, type git status again.  You should see the changes that have been made and saved now in green font.  The next step is to commit the change and add any messages about the change.  Typing git commit -m and follow in quotes whatever the commit message would be (i.e. – `git commit -m “commit message”`).  The message shouldn’t be very long or overly wordy, just concisely describe the change.  This message will show up on the GitHub repo page, so it’ll be helpful to other contributors.  The final step is to upload these changes to the master branch and GitHub.  Typing `git push` tells git to send the changes to the original repo master branch.  

Now to verify all the changes, this can be done within GitHub.  Click the Compare and pull request.  If you don’t see this notification, just click ‘New pull request’, then select the development branch on the pull request screen. Here we can fill out our pull request description and submit it for review.  It’s likely that you might have to make additional changes to the project.  So, all of these steps will have to be repeated over and over again.  It might seem as clear as mud now, but with practice and repetition, these steps become second nature.  Good luck and happy coding!


