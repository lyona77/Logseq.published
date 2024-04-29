# Beginner's Guide to Efficient Git Workflow Management

**curator**: Lingyan Yu  
**date**: 2023-11-24  
**version**: 1.0
**status**: Complete Draft

Welcome to the beginner's guide on managing your Git workflow. This tutorial is tailored for Git beginners and will cover the essentials of creating a personal branch, updating it with changes from the main project, and committing and pushing your work. This focuses on practical steps to keep your work synchronized and reviewed with ease.  

*Note. Taking small steps in learning tools like Git is completely okay. In time, as you grow more familiar with the basics, you may gradually start exploring more advanced features.*

## 1. Create a Dedicated Branch for Your Work 

These are one-time setup commands on your local terminal:

   ```{r}
   cd [path/to/your/repository] # The "local" folder that hosts all branches of your Git repo
   git pull # Update the local main branch with any changes I've made and pushed to the remote repository
   git checkout -b [your-working-branch-name] # Create a new local branch based on the local main you just updated
   ```

## 2. Pull Updates from Remote Main Branch

Before you start a working session, you should update your branch with the latest changes from the main branch.

   ```{bash}
   cd [path/to/your/repository]
   cd path/to/your/repository
   git checkout main # Switches from your current branch (which was created in Step 1) to the main branch (which you have already cloned to your local desktop)
   git pull 
   git checkout [your-working-branch-name]
   git merge main # Apply any updates or changes I've made to the main branch into your own working branch
   ```

## 3. Work on the Script

## 4. Commit and Push

You don't need to commit every single change you have made. You may save your work per usual.

- A "commit" logs a snapshot of your work on your local desktop. It is typically more official and stable than saves.
- A "Push" uploads all **local** commits since your last push to the **remote** repo.

   ```{bash}
   git add [file-name] # Stage selected changes
   git commit -m "commit message" # A note on the content of this commit, aka the difference between this commit and your last commit
   git push origin [your-working-branch-name]
   ```

---

###### *Supplemental* - Conflict Resolution during Merging at Step 2

If you encounter a conflict between the `main` branch and your working branch during the merge process, here's how you can handle it:

### 1) Understanding the Conflict

A merge conflict occurs when Git is unable to automatically resolve differences in code between two commits. 
For example, if both your mentor (in the `main` branch) and you (in your working branch) have made changes to the same part of the same file, Git will need help to decide which changes to keep.

### 2) Identifying the Conflict

When you run `git merge main`, Git will output a message indicating that there are conflicts that need manual resolution. It will list the files where the conflicts exist.

### 3) Resolving the Conflict

- You'll need to open the conflicting files in a code editor.
- Inside these files, Git marks the conflicting sections clearly, typically with `<<<<<<<`, `=======`, and `>>>>>>>` markers. The part between `<<<<<<<` and `=======` is your changes, and the part between `=======` and `>>>>>>>` is the changes from the `main` branch.
- You should carefully review these sections and decide what the final code should look like. This might involve keeping your changes, accepting the changes from `main`, or a combination of both.
- After editing the code to resolve the conflicts, you should remove the Git conflict markers (`<<<<<<<`, `=======`, and `>>>>>>>`).

### 4) Completing the Merge

- Once you have resolved all conflicts, you should save the files.
- Then, you’ll need to run `git add [file-name]` for each file you resolved conflicts in. This marks the conflicts as resolved.
- After adding all resolved files, you should complete the merge by running `git commit`. This will open an editor to write a merge commit message or you can just save and close to accept the default message.

### 5) Testing

It's crucial you test the code to ensure that your conflict resolution didn’t introduce any errors.

### 6) Seek Assistance As Needed

If you're unsure about how to resolve a particular conflict, it's a good idea to reach out to your mentor or another research/IT support for guidance.
