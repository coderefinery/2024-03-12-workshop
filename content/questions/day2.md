+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day X"
+++

## Icebreaker questions

### What is your spirit animal?
- Dolphin
- Honeybadger
- Unicorn
- Cow
- Slimy hagfish
- Simurgh
- Seagull?
- Rabbit
- Beagles
- Hedgehog
- Mountain hare
- Cat +3
- Blackbird
- Snow leopard
- Penguin
- Squirrel
- Reindeer (with a red nose)
- Remy from Ratatouille
- Panda
- Dung beetle

### Which types of projects can you use Git, etc? Which will you use it for? (add an o to what you agree with)
- I used it for making backend for my project, currently just to keep my code organised
- Plan to use it for organising code for research papers: oooooo
- Worked as a fullstack software engineer in webdev, now I am doing a Ph.D. in physics where I code a lot so I use Git to organize this code.
- To put the article manuscripts in a BitBucket repository for my supervisor to revise :)
  - Your supervisor uses Git? Nice!
  - Yes.
- Websites
- Writing a book
- We do our blog with Git + static site generators
- Bioinformatics projects
- Bash and Python scripts oo
- All CodeRefinery materials o
- Hobby programming projects + work related projects oo
- Research on image processing / machine vision. Mostly work alone in development of approaches. When version is ready colleagues do testing, GUI, work on other modules for same software. o
- Android app
- Chemometrics projects

## Introduction to version control with Git

Materials: Continuing with [Git intro](https://coderefinery.github.io/git-intro/)

- What do we need to follow this lesson?
    - Minimum: GitHub account, optional Git installed for terminal, Visual Studio Code (VS Code)
    - More info: https://coderefinery.github.io/installation/

- Does the stream on Twitch work for anyone?
  - Works here, try reload the page?
  - Works now, thanks!

- where i can see this document which shown now on twitch
  - It's this one :smile: You can see the formatted version by clicking the eye symbol on the top bar or side bar
  - I want one with agenda for today
     - Workshop page with agenda: https://coderefinery.github.io/2024-03-12-workshop/
     - Day 2 intro: https://github.com/coderefinery/workshop-intro/blob/master/daily_intro.md (webpage will be updated)

- Do we learn staging in the coming days? I still do not figure out exactly when it is best used. Is it better than many small commits?
    - We have an optional episode about staging: https://coderefinery.github.io/git-intro/staging-area/

- It is really helpful to go through the notes after the sessions, will these notes be available indefinitely?
    - Not here, but they will be curated and then all be available from the workshop page: https://coderefinery.github.io/2024-03-12-workshop/questions/

- In the workflow I have with my colleagues I develop code in MATLAB that is then automatically translated to CPP code using MATLAB coder and tested. The code needs some manual changes before it can go through MATLAB Coder. Usually my colleagues create two copies of the files in the repository with and without these changes. The rational for using copies (rather than branches) is that they need to test that behaviour is still same, which is easier having copies of files than branches. Usually to continue working on further developments I should take the changed files. It fells somewhat wrong to have under source several versions of same file. Could you comment on how we could do this better?!
    - Very good question. Sometimes I've had this case of semi-generated or files that need to be accessible at the same time.
    - In this case, yes, I'd basically keep them separate in the same branch. There are tools that help to view the diffs easily and keep them in sync - at least sort of try to: diff, patch, meld (and other graphical diff tools).

### [Cloning a Git repository and working locally](https://coderefinery.github.io/git-intro/local-workflow/#cloning-a-git-repository-and-working-locally)

- In VS Code, do you have a list of recommended extensions? Any that is a must?
  - Good question! I broadcasted the question to our extended network. It would be great to gather together a useful list of extensions.
    - Linters (depends on language)
    - Jupyter
    - Live server (for webdev)
    - Git Graph

- Let's say I create a release/tag of a version of my code, and my colleagues take that version to another repository, where they have also other modules. What are the tools for merging the code that is common between the repositories later?
  - One solution could be Git submodules: https://git-scm.com/book/en/v2/Git-Tools-Submodules Submodules allow you to keep a Git repository as a subdirectory of another Git repository.
  - There should really be two different repositories in my usecase (I believe) due to different institutions and intellectual property rights (IPR).
  - Git submodules often break. Better to keep separate repositories.

- Can I easily have and edit two branches at same time in different folders in my computer?
  - Yes
      - You can even have them linked to the same actual repository (see Git worktree).

- How to add a new release when an existing one is already there, there is no button to create new release!
  - For all I know you can't have two tags/releases for one commit id. Thus, if you have a release at a specific commit you won't be able to create another one for this commit.

- How to add v1.0? The button did not show up in my GitHub?
     - Either click on branch button and from there you can navigate to the tag. In my case I went on the right side of my repo website and clicked on "Releases" and from there on "Draft a new release"
     - alternatively: your-repo-web-url/releases/new

> Just an observation: Creating a DOI does not guarantee that an asset will "never disappear" - digital archiving is a huge challenge: https://www.nature.com/articles/d41586-024-00616-5
      - Good point. It is not a guarantee but better than having only a repo (which is better than having no repo). But thank you for the clarification.

- Isn't it difficult to work on e.g. Python scripts on GitHub? Since I have to test them while modifying them. Then GitHub would just be a place to upload my files, right? With more functionalities of course. Is there anything I'm missing? +1
    - Yes, we will look into that today: How to work on your code locally before "pushing" it to "the remote" on GitHub.
        - Please ask more if this does not become clear after today.

- When creating new branches locally you can either use the Git switch command or the Git checkout command. What is the difference?
  - In most situation they are doing the same. Checkout actually can accept commits as well, which would "check out the repository at the given commit" and if the commit is a branch name or tag it will check it out at that commit and switch the branch. `git switch` is explicitly for branch switching.

- Should we clone the origin repository or our forked version?
  - Forked version if you have it; but both will work.

- Is there a way to turn on autofill suggestions in Git Bash (Windows)?
  - Do you mean like tab completing?
      - yes!
        - Have a look [here](https://stackoverflow.com/questions/33495152/enabling-auto-completion-in-git-bash-on-windows), this stackoverflow explains it (and hopefully works, can't test it locally unfortunately since I'm on Linux).
        - Thanks, will try this out!

- In source control I see "initialize repository" and "publish on GitHub". I do not see clone repository.
  - You have a project open. Try opening a new window from the file menu.
  - In mine, as soon as I do "new window" it presents "Clone Git repository" as a option in the new blank window (tab called "Welcome"). Hm...
     - When you have opened a folder and it's not a Git repository, it shows the two options in the question. It often opens the previous folder you had open when you run it.

- what is the difference between HTTPS and SSH?
    - SSH is a protocol to connect to a remote system (secure shell). HTTPS is a protocol for (mostly) web-traffic.
        - Sorry, missed the point, you were talking about the different addresses for the Git repo. See the answer below for a better explanation.
    - I didn't understand it well.
    - Two ways of linking to GitHub and authenticating to the repos. This page explains options available to you and what we recommend (part of setup instructions): https://coderefinery.github.io/installation/ssh/.

### [Exercise: Cloning a Git repository and working locally](https://coderefinery.github.io/git-intro/local-workflow/#exercise)
In team/on your own: until XX:00, then we reconvene briefly on Stream
Try to do most of this. Follow solution if you need, it's designed to be followed
I am:
- done: ooooooooo
- not trying: o
- had problems: oo
- everything was good: ooo
- tested RStudio path : o

- There is only 'Publish Branch' button, when I click Git button on VS Code
  - And you wanted to create a branch at this point?
    - Aha. I see. After you created it. Yes, I see it too. I expect that "Publish Branch" would make it visible also on GitHub. Not needed for this exercise but you can try it out. Under the hood, it will "git push" it to GitHub.

- What is the difference between committing and staging?
  - When staging, you prepare and collect your work to be commited later.
  - You can imagine it like in the supermarket, you walk through the supermarket collecting items (your edits to the code), then you go to the cashier where you put your items on the belt (staging), at this point you might still change your mind, and put away the chocolate bar you found next to the belt and take the chewing gum instead, once you are done making up your mind about things, the cashier scans your items and you pay for the things you decided to take home (commit)
      - Thanks! Great explanation

- I do not see the branches in VS Code explorer after cloning, I do not even know the branch I am in at the moment.
  - For me they are shown on bottom left. +1
  - The bottom left also has a "recycle" symbol, or arrows for pushing and pulling. Do you see anything like that?

- I created a new branch in VS Code and I am trying to merge it to main but in the version contol view "... -> Branch" there is no option Merge branch available for me. I am within the main branch.
  - Anyone has ideas? Could it be different versions? There is always command line from the VS Code terminal.
  - When you navigate to "Merge Branch", then none is listed? Or are there some listed but not the one you were looking for?
  - I am only seeing options "Create branch." and "Create branch from..". I am using Windows.
  - Do you have multiple branches?
  - Yes I can see all the branches of "recipe-book" from the menu (bottom bar) and the new branch I created.
  - Can you press ctrl+shift+p and type "Git: Merge branch"? Does it find the command? (It seems in an older version of VS Code it might not be there.)
  - I cannot find a command by this
      - Did it open a command prompt? If so, the command does not exist in your version of VS Code. You can update VS Code or add an extention for merging branches.
     - Another workaround is to open a terminal window (top menu with File Edit ..., choose Terminal -> New Terminal). In the terminal run the command Git merge BRANCH_TO_MERGE_FROM.
     - I checked my VS Code version and it is 1.87.1. We were able to do the merging correctly in the classroom with VS Code 1.81.1 on another computer, without additional extensions.
         - I see the merge also with 1.87, so we are unsure what is the reason.
    - The terminal command gives an error "fatal: not a Git repository (or any of the parent directories): .git"

- The commit (new file) I created locally in a new branch is also visible when I switch to the main branch. It was not the case while working on GitHub. Where is this difference from?
  - I tried this in my VS Code and this didn't happen. This is before the merge, right?
    - Yes
       - Interesting. This "should not happen" :-) You can try with a new change. Or you can open a terminal inside VS Code and check with:
         - `git log --oneline main`
         - `git log --oneline THEOTHERBRANCH`

- I got the following error (screenshot removed)
    - the error means you are trying to run this outside a Git repository. Maybe you cloned and got a new directory but are not yet inside that new directory.

- How to go inside the repository from Git?
   - You are in VS Code or where are you?
   - In the Git bash
        - In this case, try "ls" (list current directory) or "pwd" (print working directory) and depending where you are, you can navigate to it with "cd"
        - Should I navigate to the cloned repository locally?

- Is there a reason that I do not see any remote branches when I do ``git branch --all`` ? I only see my own remote branches which are:
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
  Should I only see the remote branches of the forked repo, or also the one in the upstream?
  - Only of the forked repo (since that's all that Git can know about at the time).

- I want to try to use VS Code and Git. When I want to commit one of my changes, I get an error message asking me to make sure I configured my set-up. I already configured my Git with Git config user.name "my user name" and Git config user.mail "my email adress". Besides, I am connected with my GitHub account on VS Code. Do you have any idea what I should do?
  - Hm.  Good question.  It can't hurt to do it again, though
  - Random idea: could it be you did `git config` without `--global` so that it set user.name and user.email only for a certain repo?
  - Or could VS Code be using a different Git from what you used before.  (I'm not sure how or why this might be though)
      - I double-checked the identification with command lines in VS Code. Everything is ok. But I still get this problem. I also reloaded the window.

- If I am working alone, can my remote repository then be considered a backup? But if we collaborate then it is a must to have a remote, to share, but can also be considered a backup?
  - In a way yes, it can also be really helpful to use eg GitHub when working alone but on multiple computers, to keep your own work synced.
  - So a backup with extra functionalities

- DO we use the powershell terminal in VS Code or the Git bash?
  - I'm not quite sure... does the propmpt end in `$`?  If so, likely git-bash.

- When we created a file Git didnt track the file, and therefore VS Code didnt show anything in the status. It only worked after the file had some content. Why?
  - Hm, not sure. Git should be able to track empty files, but maybe VS Code has some filter on what it shows. Or hasn't updated the view yet?
    - Git cannot track empty files so it needs to have some content to be trackable. For instance you cannot add empty directories under git. +1
    - Empty files are trackable it seems (empty dirs not).

- I made suggestion on explanation on a webpage about VS Code part. Otherwise its nicely explained.
  - Thank you for the suggestion! We will try to add something about the tabs. +1

- How do I see the commits history in VS Code? And is there any way to visualise also the network?
    - I have an extension for that, Git Graph (same for VS Code)
    - After installing the Git graph, how to use it?
        - Go to the version control panel. There should be a new graph icon at the top of the panel

- Is the last commit of a branch also called HEAD, or it only applies to main?
    - Whatever you currently have checked out is HEAD - whatever branch it may be.

- As I understand we should not use Git for files that can be regenerated, e.g. plots? Is there a way to setup so that some files/folders are never under Git under a project?
  - There is the .gitignore file where you can define which files and folders should be ignored by git: https://coderefinery.github.io/git-intro/basics/#ignoring-files-and-paths-with-gitignore
  - When creating a new repository in the GitHub web interface, it provides you the possibility to use a template gitignore file for different programming languages: ![](https://notes.coderefinery.org/uploads/9a1e4f8c-ccea-4564-ae8d-b66674b42f46.png)

- What is origin/HEAD and origin/main?
  - HEAD: the position where you are right now ("position of the recorder head")
  - origin/HEAD is the current position / active branch on the remote
  - origin/main is the main branch on the remote

- We didn't hear the jingle :(
  - CATS will have a solo on the next jingle :-)
  - the UI has a few quicks still.

- Doesn't it give a problem in the path when the instructor names his branch username/whatever *slash*?
  - some people prefer "myname-topic" to name their branches. Slash in the branch works for me but maybe it creates problems on some operating systems?
     - one problem it can create is confusion since it can be confused with origin/somebranch where origin refers to an address. Confusion for humans, not for Git. for Git these are different things.

### [Inspecting history](https://coderefinery.github.io/git-intro/archaeology/#inspecting-history)

- How to step outside? How to move up in folder hierarchy? In Git bash
    - Git bash: `cd ..` to move one level up; you can use `pwd` to check "where you are"
    - Great, thanks a lot!

- I got an error (screenshot removed)
    - Are you running the clone from a place you have permissions to make new files? Does a "networkx" directory already exist?
    - No I am running the command line on gitbash. What shouldI do in this case?
    - What does `pwd` show in git-bash?  It would show where you currently are (I hope)
    - Yes it is `/`.
        - that would indicate the root directory. Most likely your user is not allowed to write in there. Best do this in your home folder
        - Okay it works thanks!

- What exactly is the fixme?
  - "fixme" is a keyword often used to say "I need to come back here and do something". Using the keyword makes it easy to search for it like we are doing here.
  - sometimes I leave a "todo" or "fixme" in the code to fix it later. Of course I will forget to do that... or not have time.

### [Exercise: Explore basic archaeology commands](https://coderefinery.github.io/git-intro/archaeology/#exercise)
In team/on your own: until XX:50
Try to do most of this, steps 1-5. Follow solution if you need, it's designed to be followed. Bisect part is optional.
I am:
- done: ooooooo
- not trying: o
- had problems: ooooo
- everything was good: oooo

- I can't find the string...
  - Make sure you are not searching on `main` but that you first "downgrade" your clone to the particular older version. The text might have disappeared in the past. But maybe you are on GitHub where it might be more difficult to search through a past version?
    - Ignore my comment, you should be able to find it also on main.
    - But let me try on my side ...
      - Yes, I'm on GitHub
         - I am now testing on GitHub ...
         - Ok I got it! Thank you.
             - Good!

- Could you make an example how to write command line for this: "Use /sometext `<ENTER>` to find “sometext” and you can cycle through the results with n (next) and N (last)."
  - Good question. We will show this after exercise here on stream on how to search through file.

- what is the command for these; "Find out when this line was last modified or added. Find the actual commit which modified that line".
   - See solution. But once you know which file it is (which you found out with "git grep"), try "git annotate FILE".

- Is it possible to do the exercise merely using the VS Code than command-line?
  - I will comment on that. some steps probably need an extension but we did not want to recommend installing extensions to make it more complicated. some steps (like "annotate" might not work without extension). We are collecting a list of extensions that we plan to recommend to learners.

- Do we need to find the commit that simply modify that line (they just added a space) or the one that created it? I assume the former, but the code hadn't change really
  - the former. in this exercise just looking at the last change (which added some spaces). But in real life, sometimes we have to dig deeper and then look from there further into the past. Good observation!

- My terminal doesn't go to less?
  - It works if you pipe into less -> `your command | less`
  - What operating system, etc are you using? git-bash?
      - It is git-bash in VS Code terminal on windows
      - I think it might be this, if you did this configuration: https://coderefinery.github.io/installation/git-in-terminal/#step-4-two-more-settings-for-windows-only
      - It helped with some thing else (git in the Conda terminal) but these commands disable `less`
      - `git config --unset core.pager` would un-do it.
  - we will show how to search without less.

- Could you clarify where the branches are saved (like in which folder) in my local computer when I create branches locally? I cannot find them
   - all Git info is saved in a folder called .git that is on the top of your repository. All the branches and metadata is in there (`.git/refs/heads/` in particular).
   - We have an advanced lesson that tells more (but it is advanced and not needed for real work): https://coderefinery.github.io/git-intro/under-the-hood/

- Still do not find the actual commit that modified the line, with "git annotate networkx/algorithms/threshold.py".
  - Does searching for "/Logic error" work?
      - It exits after it prints all the commit so I cannot type /Logic error.

- Could you please briefly explain how to do the last question of the exercice on GitHub?
  - Hopefully we have time to show, otherwise we will describe here ...
    - You can navigate to that point: https://github.com/networkx/networkx/tree/51611a038
    - But to create a branch, you would have to fork first.

- How am I supposed to create a branch pointing to the past when I have not cloned, according to the instructions in GitHub? I do have it in VS Code however, but not sure how to point to that commit. I think it is a bit confusing when we can use both GitHub, terminal and VS Code.
  - Thank you for the feedback. The different tracks are new to us too and were a response to earlier workshops feedback.
  - You are using the "GitHub" path?
  - Answer to the question: you cannot create a branch directly on their repo. you would have to fork first and then create it. But you can probably browse their project at that commit: https://github.com/networkx/networkx/tree/51611a038

- Hi! For some reason when i tried to "git switch --create HASH-1", it returned an error "fatal: invalid reference". Any ideas as to why?
    - I made the same mistake, it is ~ and not -
        - AHA. Okay thank you!

- I think this exercise was too fast and not properly explained
  - Thank you for the feedback, hopefully the walkthrough now helps you to get back on track.
  - But also don't worry if not, you will still be able to join in the afternoon.
      - I agree that there wasn't enough time. For me cloning and creating branches took a long time (a lot of files and changes). Also, I feel that there was a lot jumping back and forth on the page that contains the exercise. It would be useful to have the commands demonstrated at the time when they are needed.
        - Thank you also for that feedback and the suggestion!

- Heard the jingle!
  - :)

- Still do not find the actual commit that modeified the line, with “git annotate networkx/algorithms/threshold.py”
    - Does searching for “/Logic error” work?
        - It exits after it prints all the commit so I cannot type /Logic error

- git annotate exits the file after printing its content, so I cannot type the "/Logic error"
  - It might be that it is not using the pager "less" (a bash command to view text output and navigate while viewing it). "git annotate filename.py |less" should work (replace filename.py with the path+file you want to git annotate).

- If I create a local branch from a remote branch, where the new information is saved? Since the branch is not from the local repository
    - This creates local copy of the remote branch. The new branch starts from there.
    - All branch information is stored in a folder called .git .

- Does remote branch always start with origin
    - When you clone, the place you clone from is automatically called "origin". The remote branch name starts with the name of the remote repository, which in this case is "origin". Usually you only have one remote, called "origin", but you can have more.

- Could you explain more with example what command should be written for this? How to write less and n and N? (screenshot removed)
    - Is the problem that in your case it does not let you navigate up and down in the annotation and immediately quits after printing it all?
    - No I don't know what I should write. /sometext | less -n 1 -N 2? I am not sure if it is correct and what they really means
          - We will explain... in writing ...
          - At the end of session or?
    - I'd recommend not worrying about this - this is command line details. But here is what it means:
        - `git log` starts another program that can scroll up and down. This program is called `less`. It's controlled by the keyboard (once it starts). Keyboard shortcuts (inside the program): "n", "N", "/".
        - But it's possible that your Git doesn't use `less`. In which case, we can't help much - I would suggest going on and asking someone locally.

> Exercise list for those who need a credit has been updated: https://coderefinery.github.io/2024-03-12-workshop/certificates/ Remember that credit/certificate is available only for those affiliated with a higher education institution.

- We can't see the whole url
  - Sorry, here it is: https://github.com/networkx/networkx/tree/90544b4
  - The bottom line: add `/tree/HASH` (replace HASH) behind any github repo and you can see how it looked back then

### [How to turn your project to a Git repo and share it](https://coderefinery.github.io/git-intro/sharing/#how-to-turn-your-project-to-a-git-repo-and-share-it)

### [Exercise: Turn your project to a Git repo and share it](https://coderefinery.github.io/git-intro/sharing/#exercise)
In team/on your own: until XX:35
-> Try to do most of this. Experiment a bit. Follow solution if you need, it's designed to be followed. Add questions and thoughts below (also from earlier sections), these will be discussed on stream after.

I am:
- done: ooooooo
- not trying: oo
- had problems: oo
- everything was good: oooo

- After publishing it ask on VS Code if I want VS Code to periodically run "git fetch", what do I do?
  - Git fetch checks if there are new changes in GitHub. I usually have it on.
      - But how does it work, would it interfere with the local repository?
         - `git fetch` fetches commits that you don't have locally and updates remote branches but does not modify any local branches. I think this can be useful so that you always have also remote commits available on your computer if you need them, without having to actively fetch them. In short: it should not interfere with local branches.

- Hi! I was trying to push an existing repository by command line, but I got the error "src refspec main does not match any". Any ideas on what went wrong?
  - Maybe you need to tell it what to push: `git push -u origin main` (`main` is branch to push, `origin` is remote name, `-u` says "remember this for later")
  - and a main branch exists? +1
      - Good call! I'll check it out. Thanks!
        - Check with `git status` or `git branch`
            - Solved! Thanks so much

- Why using VS Code instead of GitHub? I did it so much faster on GitHub, I think.
  - To have a local copy. This is in case you need it for other reasons, and would depend on what the project is. If it's software, you would run tests and use it locally.
  - Day 1 was GitHub (easy but not very realistic), now we go to harder but more realistic. Different people may focus on different parts.
  - For archiving the work the GitHub path is good enough. But if I want to continue on it, then you probably either want to clone it or start from local.

- Is it really necessary to create an empty repository on GitHub? In VS Code I can just “publish to GitHub private (or public) repository with username/myproject.
  - With VS Code it is not needed to do (it creates it for you). But on command line you need to do it first.

- Ok, so I can publish to GitHub without first creating a repository, but that does not seem to work with GitLab?
    - With VS Code: yes

- In making changes to a file in a local repository, after committing is asked "would you like to stage all your change and commit them directly?". What should be done here?
  - Here say yes. Later you can try to use the staging area to more selectively decide what to commit. We will discuss it. It can be useful to create well-defined commits. But at the beginning there is no problem with committing directly.

- If we're doing this on GitHub, we don't really do step 3, right? Just trying to understand this fully.
  - Right. Then it's already there. Now just for fun you could try the reverse and to clone it to your computer into a different folder.

- Created a readme file on the Git remote repository, how to make it reflect in the local?
  - try to "pull" the change to your local clone.

- When I want to push to origin, I receive an authentication error:
  remote: Support for password authentication was removed on August 13, 2021.
  remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
  fatal: Authentication failed
  how can I avoid this?
  - This is from command line? Or from where?
      - Yes, from command line.
         - In this case you probably want to set up SSH keys or the Git credential manager. See the "configuration" in the Git lesson: https://coderefinery.github.io/git-intro/configuration/ the part about "Authenticating to GitHub"
             - Thank you
                - It can take some time to set this up but if you plan to work on the command line with git, I recommend to set this up. I personally use SSH keys.

- How to delete a repository, then, on GitHub and also by using VS Code (if possible)?
  - On GitHub: top right is settings, then in there scroll all the way down and you can delete the repo.
  - On VS Code: if you remove the directory or the .git inside the directory, the Git repo is gone locally (this doesn't delete the GitHub copy).

- I got this error: "error: failed to push some refs to github.com:[my user/repo]"".
    - Any more in the error message? Hopefully it wolud tell the reason somewhere else.
      - No further info in the line. Maybe the question I have is whether I need to have edited some file here to then push? E.g. most simply how to save a new script into the main branch?

- How to disconnect with git? Once I establish a folder connecting with git, the VS Code Git also notifies me 'commit'.
  - In VS Code look for remotes. With CTRL+SHIFT+P and then search for "remote" or: three dots, then "Remote". there you can remove it and then it's disconnected.
  - What do you mean by disconnect?
    - I mean after I publish my project, each time I modify the files, VS Code asks me to commit. What if I do not want to commit, just modify the files locally. I don't want VS Code to notify me.
    - I guess delete .git folder might be helpful.

- Is there anyway to change the Git repository from private to public? Because I am unable to view network with the private on GitHub.
  - Settings → General → Danger zone (at bottom) → change visibility.

- We call these projects but on GitHub they are called repositories. On GitHub they also have "Projects"?
  - Yes with a GitHub project you can do more, like having a task board, milestones, and many things "around" a Git repository (same on GitLab).

- What is the file extension for the file LICENSE? Is there a set way for creating a license file?
  - In essence it's just free-form. No extension, but you could put it in some format. GitHub does some magic detection.
  - If you start creating a file named LICENSE on the GitHub interface, it will give you a picker to choose one. We will talk more about licenses on day 4.

- In the timeline tab of VS Code, why does my timeline show a lot of "File Saved"?
  - Not sure. I wonder if it could be a mode that is automatically committing on every save?

### [Practical advice: how much Git is necessary?](https://coderefinery.github.io/git-intro/level/)

- When should we initialize the .gitignore file? If there are files from a format that I want to exclude but that are in the history of git, creating a .gitignore file does not allow us to get rid of these. What should I do then to remove these. Ex: I clone a repo with NN weights. These files are very heavy. So I create a .gitignore file. But these files are still on the history.
  - Good question! Changing history is another topic. It has its risk. Try searching "git remove big files from history" or some such...
  - In this situation you can start over from scratch with a new repository in which those large files are not added in the first place.

- Can I have different .gitignore files for two local repositories of the same repo?
  - Yes you can. The .gitignore itself can be version controlled within each repository. Aha, ok, with two clones of the same repo it is a bit more complicated.
      - For instance, I have a local repo on my laptop and another one on some clusters with a limited memory. So I would like to compute the results on the clusters, transfer these to my laptop and then erase them from the clusters while keeping them on my laptop.
        - Unsure whether this could be done working with a single repo. One setup could be to work with two repositories. One containing the contents that need be available all clones, and another repo with the larger files.
        - In that workflow, wouldn't a synced .gitignore still work? If it's tracked on one place then it'll end up in all histories. If it's ignored in one place but doesn't exist in other places, it doesn't matter.
  - `.git/info/exclude` (the `.git` dir of each repo) is a non-tracked ignore file - per local computer.

- I can understand using Git for code, but what about more complex files, e.g Word documents?
  - It works! I use it for similar, for example our group's image archive.
  - But you don't get nice things like the differences between files and so on. It's not *best* but in some cases it's better than other options.
    - For Word documents (or common documents) there are better solutions. The main issue with "proprietary" formats, or binary formats is that if you have conflicts, it's difficult to solve them. I'd personally rather use a shared editor (overleaf, googledocs or MS cloud) with a history than Git for version control of documents, where I expect a lot of edits. But if it's "just" to keep them in one place and not for collaborative work on the document, storing them in Git works fine (e.g. you work on a document for a webpage, and put the final doc into a repository, and potentially later replace it by more recent versions).

- How to turn a project into a GitLab repository instead of a GitHub repository?
  - You would start the repo on one's own computer like normal "git init".
  - Then you would make a new repo in the GitLab web interface.
  - Then set the remote to the GitLab path (which the GitLab empty project will tell you how to do).
  - (same for any other web repository services).
      - this is not so clear especially with the VS Code path.
  - Below someone mentions a VS Code extension for GitLab.

- Is Git the best way to handle projects with a lot of non-code assets, like videogames with binary 3D files? How do you handle the changes to those files?
    - If things get really large git-annex or git-lfs can be an idea (integrated into git). Overall, there is no drawback of using Git for these kinds of projects, but as mentioned above, for non textual files, conflict resolution is not (easily) possible and repos can become quite big.
    - Git LFS (large file storage) is designed for this kind of case but uses only a central repo. git-annex also does but is much larger and more distribtuted.

- When would you clone vs fork a repository? If I want to play with someone's code, maybe make some own changes but don't want necessarily to share it back, perhaps cloning is OK?
    - Yes. I would fork, if I intend to track my changes or see a potential of submitting a feature via a PR and use a clone mostly if I just want to "use" the code without a lot of modification.
    - But I can also track the changes in a clone right? It can be it's own repository?
      - Yes, in the clone you can make edits and commits. But you cannot push to the parent repository unless the owner of that repo has given you write access.

- Could you explain what .gitignore file does?
  - The .gitignore file contains a listing of files that should not be version controlled. The listing can be in form of file name patterns, e.g. `*.out` if you want to exclude output files with that suffix.
      - It's extremely useful to e.g. avoid tracking editor specific files (like the .vscode folder that VS Code tends to create for any project it opens) or temporary files like compiled Python (pyc) files. Also if you e.g. run a database in your project, you likely don't want to have that database on GitHub, but only have the code there.

- Any preparations we should do for tomorrow's sessions today already? Creating local files, folders, repos?
  - the only preparation step for tomorrow is for learners without a team or who are not in a local exercise group. Since tomorrow we will do collaboration, if you are on your own, open an issue following https://coderefinery.github.io/2024-03-12-workshop/communication/#2024-03-12-exercise-preparation-for-learners-without-own-group
  - exercise preview: https://coderefinery.github.io/2024-03-12-workshop/exercises/ (this afternoon we will create solutions/screenshots)

- Are there things that you often do only on GitHub/GitLab vs. command line and vice versa.
  - Reviewing pull requests and issues (obviously, can only be done there), but more importantly the "Suggesting" feature for pull requests to make small changes to the pull requests (could be done locally, but I don't often)

- I noticed that RStudio as an option for commit signing in the commit dialog. Is there benefit of cryptographically signing commits in the context of (academic) research?
  - You can probably figure out cases where it's useful. I don't hear of it being often used in the academic context.
    - thanks!

- When I use the command: ssh -T git@github.com, I will get ``You've successfully authenticated, but GitHub does not provide shell access.``. I have set the ssh keys in GitHub to the best I know.
  - This is a successful response. It probably showed your username. Git will work.
      - But then I recieve the same error as before when I want to push the origin.
      - The exact same message?  Hm...
      - Yes, is not it related to the second part that says shell access is not provided?
      - Which error do you get?
          - remote: Support for password authentication was removed on August 13, 2021.
            remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
            fatal: Authentication failed

    - Is you remote using Git protocol? git@github.com:USER/repository.git? (vs https://github.com/USER/repository.git). You can see this with `git remote -v`
    - ``git remote -v`` gives me https://github.com/USER/repository.git which is what I added as origin via ``git remote add origin https://github.com/USER/repository.git
    - That's it then, change it to git@github.com... : `git remote remove origin` and `git remote add origin git@github.com...`. Using https protocol tries to use password authentication which as it says was removed.
        - Thanks! It is working now.
        - Glad to hear this, you're welcome!

- From the VS Code code pathway, how to publish project to a GitLab repository instead of GitHub, given that from start the only option is GitHub.
  - GitLab has an extension called "GitLab Workflow" for VS Code. It allows a lot of interaction wit GitLab, checking if it enables publishing.
      - It adds a command for cloning from GitLab and adding a remote. But not publishing directly. You would need to create an empty repository on GitLab and add it as a remote.

- When working locally, Git will keep track of each previous version to be accessible even years after. All this information must be stored I understand. Can this become a problem with the time? Does Git uses some compress format?
  - It does compress all the stored data. For the types of things Git is designed for (text files), it works pretty well. For bigger things like .docx, .pdf, images: it's not perfect but is OK.

- How come that I can publish directly from VS Code to GitHub, without first creating an empty repository on GitHub, compared to GitLab where I have to first create an empty repository? Or am I wrong?
  - VS Code is owned by Microsoft and so is GitHub, so they make sure it works well. Above someone mentions GitLab extensions that would make it easier there, too.
  - But in general you are correct in your observation.

- Bring cat back
  - sorry, as you probably know CATs do what they want. Hopefully it comes back...

- Is there a way to do automatic Git commit to avoid losing work? Perhaps a bad way to use git? Because I also use Time Machine which use versions and automatic backup. Perhaps something like a commit with backup in the commit text.
  - Could it be an automatic script with random commit message and then squashing the commits when you do a "real one"?

- Is there a practice to join commits? Sometimes I go fixing really small things like typos and several times a day. Could I join my commits of the day and write a sensible description for that one big commit (like fixed several typos, wrote documentation, etc.)
  - This "undoing and recovering" episode: https://coderefinery.github.io/git-intro/recovering/
  - I use "rebase" often. Search "git interactive rebase" and "git interactive rebase squash" and "git commit fixup" for ideas. I use this somewhat often.

- Is not most code developed under certain employment proprietary? How do you build your GitHub portefolio? Mostly from project done on free time?
  - Depends on your employer, many (?) universities/funders have some guidelines along the lines of "as open as possible, as closed as necessary".
  - Research code is often closed until one or multiple papers have been published using it, after that it is often up to developer.

## Feedback

Today was:
- too fast:
- too slow: oooo
- right speed: ooooooooooooo
- too advanced:oooo
- too basic: o
- right level: oooooooooooo
- needed more exercise time: oo
- needed less exercise time: oo
- I will use what I learned today: ooooooooooooo
- I would recommend today to others: oooooooooooo
- I would not recommend today to others: o
- too slow sometimes, too fast other times: oooo

Rstudio track was:
- helpful: ooo
- not refined enough to be useful:
- I didn't use: ooooooooooooo

One good thing about today:
- Found that exercise where we searched for the string to find the commit and so forth was very good.
- The speed was really nice, I never got "lost" and genuinely learned a lot, already used this in my own project to know where
- It was a nice experience
- I feel like I have a better understanding of the relationship between local and remote branches. o
- Tips and examples for commit messages very useful. Otherwise generally very easy to follow, very useful. o
- I'm long time RStudio user but this was the first time I used the integrated Git feature. o
- I understand better what I can do with Git in my work.
- Learned how to work between VS Code and terminal and GitHub and how to use commands flexibly within these.
- Enough time to discuss questions from the document on stream.

One thing to improve for next time:
- Perhaps balance the exercise times for different difficulty levels.
- For me that I just wanted to use GitHub and partly VS Code, it was a bit slow and I would have liked more information given.
    - Thanks for this feedback! Could you specify what "more information" you would have liked?
- I would have liked to do a few more exercises to practice command line in different ways (i.e., similar instructions with other examples or try different ways to do obtain same results).
- There could be a simple exercise at the end of day 1 for those who want to make sure their command line Git can do everything required for day 2 exercises.
  - Thank you for this feedback! Would there be need for more than this: https://coderefinery.github.io/installation/git-in-terminal/#verification ?
  - Or what things did you have trouble with? (this is important for us to know so that we can update the install instructions and verification)
    - It seems like I didn't follow that page all the way to the end, plenty of useful steps there. I was confused with basic things like changing directories/folders ('cd'). For example, I cloned the folder successfully but did not realize that I have to go into the folder. Also took me a while to figure out how to exit the 'graph'.
    - One more thing to check in the installation page could be whether connection between command line Git and GitHub works. Are you allowed to connect from your local computer to GitHub? See https://coderefinery.github.io/installation/git-in-terminal/#verification.

Any other feedback?
- Thanks for adding RStudio, really helpful. I think I need some more help with the SSH stuff there, though.
- Perhaps focus on terminal first in the course, then GitHub and finally VS Code. It is a bit confusing when we mix them. o
- There is a bit of information overload
- a lot of information
- advanced stuff
- I enjoyed the starting with GitHub, it makes life easier (I have earlier used mainly command line). o
- I am more confident using branches now, didn't have a good understanding of it before. Now I know, thanks so much!
- As a beginner, while I liked the archaeology exercise and its practicality, finding specific commits seemed a bit advanced. I think I was expecting the focus for today be more on cloning repos and pushing changes to them. Maybe an exercise where we push a change from our locally cloned recipe-book repo to GitHub and check changes in the insights panel. (Hmm, seems like we might actually being doing some of this on day 3).
- Thank you to the team and CATS!

News for day 2:
- We did the things that are now listed on the schedule
- Tomorrow is "git collaborative".
  - It builds on things today - it would be good to review if you haven't attended days 1-2.
  - We assume that you can link to and push/pull from GitHub.  You need to make sure the authentication works with whatever program you are using: https://coderefinery.github.io/installation/ssh/ .
  - It is possible to do everything in GitHub though.
