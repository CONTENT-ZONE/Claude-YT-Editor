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

## What if I make drastic changes to the code?
If you make massive, structural changes to the codebase (like rewriting core logic or moving files around) and *then* run `git pull upstream main`, Git will try to combine your changes with the original author's updates.

Depending on what you changed, one of two things will happen:
1. **Auto-Merge (The Happy Path):** If you and the original author edited completely different files or different lines of code, Git will merge them together automatically.
2. **Merge Conflicts (The Messy Path):** If you both edited the *exact same lines of code* differently, Git will pause and throw a "Merge Conflict." You will have to open VS Code, look at the conflicting files (which will be highlighted), and manually choose which code to keep (yours, theirs, or a mix of both).

**Pro-Tip:** If you plan to heavily customize this editor to the point that it's practically a different software, it is often best to just stop pulling from `upstream`. At that point, you have created a true "hard fork," and you can maintain it independently!
