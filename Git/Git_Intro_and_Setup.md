---
header-includes:
  - \usepackage{hyperref}
  - \hypersetup{colorlinks=true, linkcolor=blue, filecolor=magenta, urlcolor=cyan}
---

# Git for Version Control: Intro

## Main functions

- clone
- pull
- commit, push
  
## Git vocabs

- Branch: main branch
- Repo: repository, remote, local
  
## Github: Git platform

Github enterprise: <http://github.umn.edu/>
  
## Git Setup Workflow

*Notes*: All codes are run on Terminal.

1. Installation

   1. **Download Git**: Visit the [Git website](https://git-scm.com/) and download the installer for your operating system.
   2. **Install Git**: Run the installer and follow the on-screen instructions.

2. Configuration

   1. **Open Terminal**: Open your terminal or command prompt.
   2. **Set User Info**: Configure your Git username and email.

      ```bash
      git config --global user.name "Your Name"
      git config --global user.email "youremail@example.com"
      ```

3. Create/select a local folder for project-related items

4. Clone a remote repository to this folder using ssh

   1. **Generate SSH Key**: If you haven't already, generate an SSH key on your local machine.  

      ```bash
      ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
      ```

   2. **Add SSH Key to GitHub**
      1. Copy the SSH key to your clipboard.

         ```bash
         cat ~/.ssh/id_rsa.pub
         ```

      2. Then, add it to your GitHub account under SSH keys in settings.

   3. **Test the SSH connection**

      ```bash
      ssh -T git@github.com
      ```

   4. **Clone Remote Repository**: Navigate to the folder where you want to clone the repository and run.  

      ```bash
      git clone git@github.com:username/repository.git
      ```

## Workflow

- Only the local "clone" copies will be modified when you save your changes. If you stage and commit a "batch" of your changes to Git, it will updated your local git file history with the new commit as the most recent "official" version. These two steps will not affect any remote copies.
- To merge your changes into the remote master branch, you will need to "git push" the local git history either on Terminal or via a Git desktop GUI.

## Git Resources

- [Git Intro curated by Software Carpentry](https://swcarpentry.github.io/git-novice/)
- LATIS offered a synchronous Git workshop earlier this month, so we just missed it. There may be internal resources for students working at LATIS. They most likely will offer it again next semester as well.
- [Minnesota Supercomputing Institute (MSI) Youtube channel](https://www.youtube.com/@UofMMSI/featured): recordings of previous tutorials
  - [Introduction to Version Control and Git](https://www.youtube.com/watch?v=cbb_MWE2QPI)
  - [Github and Collaboration using Git](https://www.youtube.com/watch?v=mfyBKEpwnoM)
- External resources for exploration
  - [Learn Git Branching](https://learngitbranching.js.org/?locale=en_US): a visual and interactive way to learn Git on the web
  - Tutorials offered by Git Desktop GUI, e.g. [Git Tutorials - GitKraken](https://www.gitkraken.com/learn/git/tutorials)
    Be aware that GitKraken is not free. It does offer free Git tutorials though. There are several free GUI options out there as well - should you prefer the traditional application view over Terminal.
  - And ChatGPT!  
