---
layout: page
title: Walkthrough
order: 1
---
# Intro

This is an information page within the template. The .md file has a header that specifies the page type, title and order that it should appear in the table of contents. You can add as many pages as you like and update the header information in each one. This will create an accurate table of contents on the main page and allow navigation.

The information below will go through all the steps necessary to build a GitHub pages site. These pages also serve as a simple template to construct a workshop site.

## Create a new repository on GitHub

First we create a new repository on GitHub. On the organisation page of the BIO3092 GitHub site click the green 'New' button in the top right corner.

![New repository](/images/new_repository.png)

Enter some information about the name and description of your workshop and set the visibility to public. Finally click 'Create repository'.

![Repo details](/images/repo_details.png)

A more detailed guide to setup a new repository on GitHub can be found [here](https://docs.github.com/en/github/getting-started-with-github/create-a-repo)

## Creating a new gh-pages branch

Next, create a new branch in the repository to store our pages site. On the main page of your repository click the branch selector button and enter the name of your new branch i.e. 'gh-pages'. Then click the 'Create branch gh-pages from main' button.

![New branch](/images/new_branch.png)


A more detailed guide to setup a new branch within your repository can be found [here](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository)

## Clone your repository

Now clone your repository to your local machine so that you can add files and write your workshop. You can find the URL for your repository by clicking the green 'code' button in the top right hand side of your repository.

![Clone](/images/clone_url.png)

On your local machine navigate to the directory where you want to store the repository and enter the command:

```
git clone <url>
```

![Git clone](/images/git_clone.png)

Some information should be printed to the screen and a new directory will be created containing your repository. For more information on this process see [this page](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository). Note that you will have to have an ssh key and this needs to be associated to you Git account. See [here](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) for details.

## Change to the gh-pages branch

Before we can start adding material we need to switch to the 'gh-pages' branch so that all the files we add go to the correct place in our repository. We do this with the command:

```
git checkout gh-pages
```

![Git checkout](/images/git_checkout.png)

## Add files and create the workshop

You can now add files to this directory and write your workshop materials. To create a workshop page in line with the BIO3092 RNA-Seq pages you can download the files from the template repository (they can be downloaded as a zip file directory from GitHub), import them into your repository directory and make any changes necessary.

I work in an IDE ([Atom](https://atom.io/)) that comes with built in functionality for working with projects stored on GitHub. It means all the commands for pushing to the server can be handled from an intuitive GUI. You can see in the following screenshot the files I have added for the template repository (left) and that Atom will keep track of changes in a Git tab (right).

![Atom](/images/atom.png)

In fact many of the operations (cloning, checkout and switching branches) can be handled from the Atom GUI.

## Update the config file

In the template files there is a config file (\_config.yml). There is one small change that will need to be made in this file. Change the line:

```
baseurl: /template
```

to

```
baseurl: /<your-repo>
```

![config](config_update.png)

This just sets the base URL for your GitHub pages to the correct repository.

## Pushing the workshop to the server

Once the workshop has been written, it is time to 'push' our changes to the repository. This process is done in three stages on the command line.

* First, we use `git add` to [add](https://github.com/git-guides/git-add) files to our commit
* Then, we use `git commit -m` with a message to create a [snapshot](https://github.com/git-guides/git-commit) of the repository ready for upload.
* Finally, we use `git push` to update the [remote branch](https://github.com/git-guides/git-push) with our commit.

This can all be handled on the command line from within the repository directory. Or through a GUI interface in an IDE such as Atom.

![Atom push](/images/gui_push.png)

In the above screenshot you can see on the right hand side I have staged files (add) for upload and have entered a message for the commit. The next step is to press commit to 'gh-pages' and use the 'push' button (appears at the bottom after committing) to upload changes to the server.

## Publish the branch as a GitHub pages site

We have now almost finished the setup. Once the workshop files have been uploaded to the server we need to publish the repository as a GitHub pages site. If you now view your repository on GitHub, you should be able to see your added files.

![Updated repo](/images/uploaded_repo.png)

Click the 'settings' button in the top right and scroll down to the GitHub pages section. Update the settings to publish the repo as a GitHub pages site. If you have used this template repository to create your workshop these settings should already be complete.

![Settings](/images/settings.png)

Once the GitHub pages site has been published the URL will appear in this section. Visiting the page should show something similar to:

![Landing page](landing_page.png)

Now when you make further changes to the workshop just 'push' the changes to the server and after a few minutes those changes will be reflected in the pages online.
