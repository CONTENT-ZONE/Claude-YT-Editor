# Updating the Repository

Since this repository is a fork of another author's project, you have your own copy (`origin`) on your GitHub, but you may occasionally want to pull in the latest changes that the original author (`hassancs91`) makes.

## The Setup (Already Done)
To make this possible, the original author's repository has been added as a secondary connection called **`upstream`**. 
You do not need to do this step again.

## How to Pull Updates
Whenever the original author updates their code and you want those changes, run the following command in your terminal while inside this project folder:

```bash
git pull upstream main
```

*(This command fetches the new code from the original author and merges it into your local files.)*

## How to Save the Updates
After you successfully pull the updates, your local files will be updated, but your personal GitHub backup will not be. To send those updates up to your own GitHub fork, simply run:

```bash
git push
```
