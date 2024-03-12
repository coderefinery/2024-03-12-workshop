+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 1"
+++

## Icebreakers

### Where are you connecting from? How is the weather there?
- Finnland, Aalto, sunny, some clouds, icy
- Norway, Tromsø, cloudy, some snow
- Helsinki, Finland, sunny with light clouds
- Oulu, Finland, -4 degree Celsius and cloudy
- Helsinki, Finland, sunny from Aalto university
- Kiruna, Sweden, -4 degree Celsius and cloudy
- Turku, Finland, Finally it's sunny (BLUE SKY!)
- Trondheim, Norway, gray -2  degree Celsius
- Otaniemi, Finland, sunny
- Bergen, Norway, cloudy
- Helsinki, Finland, sunny
- Malmö, Sweden, cloudy
- Amsterdam, Netherlands, misty
- Nijmegen, Netherlands, gray
- Finland, Espoo, Apparently Sunny.
- Finland, Pöytyä, sunny and warm. Definitely better than Helsinki.
- Otaniemi in person room, weather is "sunny", coffee is instant coffee :( Illegal
    - That's the best I can do... :D
- Lyngby, Denmark, bit grey
- Lyngby, Denmark, I can confirm
- Kongens Lyngby, Denmark - pretty sad weather :(
- Espoo, Finland, sunny
- Helsinki, Finland, sunny
- Helsinki, Finland, sunny
- Helsinki, Finland, sunny
- Stockholm, sunny
- Espoo, Finland, sunny
- Donostia, Spain, cloudy
- Donostia, Basque Country, cloudy
- Delft, Netherlands, cloudy
- Ede, Netherlands, cloudy
- Aarhus, Denmark, cloudy
- Aarhus, Denmark, grey and cloudy
- Helsinki, Finland
- Norrköping, Sweden, sunny
- Uppsala, Sweden, foggy
- Lund, Sweden, chilly
- Stockholm, Sweden, sunny and nice
- Rovaniemi, Finland, -4 degree Celsius and cloudy ☁️
- Turku, Finland, sunny
- Lohja, Finland, sunny with some clouds
- Tampere, Finland, frigid but sunny!
- Delft, Netherlands, cloudy, sad, not sunny :( 7 degree Celsius +1
- Barendrecht, Netherlands, cloudy
- Delft, Netherlands, cloudy
- Denmark, Lyngby, cloudy
- Oslo, Norway, -1, cloudy
- Honselersdijk, Netherlands, light gray
- Oslo, Norway, chilly
- Örebro, Sweden, cloudy, -2 degree Celsius
- Helsinki, Finland, nice and sunny for once
- Göteborg, Sweden - cloudy as always
  - always :-) west coast is the best coast
- Delft, Netherlands, cloudy
- Bergen, Norway, cloudy
- Hämeenlinna, Finland, sunny
- Port Harcourt, Nigeria, cloudy, which is nice because there is no scorching heat.
- Donostia, Pais Vasco, cloudy
- Trondheim, Norway, almost sunny
- Cullercoats, UK, rain imminent
- Paris, France, almost sunny

### Have you used git before, if yes, how?
> Poll: Add an 'o' to the answer that applies to you

- Don't know what git is: oooooo
- Yes: oooooooooooooo
- No: ooooooooo
- Yes, GitHub web interface: oooooooooooooooooooooooo
- Yes, GitLab web interface: oooooo
- Yes, other web interface: oo
- Yes, VSCode: oooooooooooooooooooo
- Yes, command line: oooooooooooooooooooooooo
- Yes, RStudio: ooooooooo
- Yes, other: o
- Yes, command line, web interface oooo
- Yes, using GitHub (VSCode) and Bitbucket o
- Very little oooooo
- Yes, GitHub desktop app
- Yes, from the web
- Yes, but I always mess something up: o
- No, I am new to Git
- used Bitbucket which is similar
- built-in Xcode version control

## Welcome and practicalities

Materials: [Welcome and practicalities](https://github.com/coderefinery/workshop-intro/blob/master/livestream.md)

- Is this the right place to ask questions?
    - Yes it is! :)

- How can I edit this document?
    - Find the pen symbol on top of the page to switch to edit mode, then type your question.

- What's the difference between BitBucket and Git?
    - Git is a system for version control and storing of files. BitBucket and Github are web platforms that understand the git format, and make git repositories available by the web.

- Is it ok to configure GIT LFS (Large File Storage) by default and advantages and disvantages of it.
    - I haven't used Git LFS much, but from what I understand there shouldn't be much disadvantage: if you don't add the large files it probably won't do much

- What is GIT LFS :)
    - "Git Large File Storage", an add-on that makes Git better for large files that shouldn't have full history tracked.

- Why is it a play sympol on the video screen and how do I get rid of it? If I press pause I see a pause symbol. But it is annoying and in the middle of the screen.
    - Hm.  It stays if you move the cursor out of the screen?  This is new for me
    - Yes, it is there all the time. Very difficult to focus when seeing this. I am using Safari on MacOS.
    - Fixed. Switched to Firefox.

- The jingle!
    - It was made by someone in CodeRefinery last week!

- One wish, to please adjust the pace for the beginners who are new to Git. Thanks.
    - The first two days have been completely restructured so that day 1 is a better introduction for beginners who don't have much command line experience. Day 2 adds VS Code as a follow-along option.

- Would you also have a overview of Docker/container best practises or a updated course pointing to the same. Thanks
    - We want to make such a course but don't have yet. I don't have the best course off the top of my head.
    - Containers basic will be a small part of the reproducibility lesson on Day 4 (Tue next week)
    - For containers in a supercomputing context, see e.g. https://raw.githubusercontent.com/PDC-support/pdc-intro/master/episodes/pdf-files/singularity.pdf

- Why do you teach GitHub but yourself use GitLab. Are there concerns around the same that one should take care of when choosing between the two? Thanks
  - GitHub is proprietary and owned by Microsoft.  Which is always a risk once they need to make more profit. At least moving code is easy - that will not get lost.  Issues is harder.  GitLab has an open-core component that universities and so on can run themselves, which is a good backup.
  - See also "Why GitHub?" at https://coderefinery.github.io/git-intro/ (blue box)

- In what way we should deliver homework in order to get 1 credit
  - You'll hear more about this later, roughly by email.
  - https://coderefinery.github.io/2024-03-12-workshop/certificates/
  - scip@aalto.fi is the email (it will open a ticket so you can track your request). If you submit your homework by 22 March, you get the credit asap (highly recommended!). Otherwise expect the credit in mid-May - June.

- If i will miss one day can i find a recording of workshop
    - Yes, they will be on Twitch for 1 week immediately and will also be placed on Youtube later on (usually same night, but potentially could take a bit of time).

- CAT
  -  Miao miao

- I will be disappointed now if we don't get to see a cat.
  - It comes and goes as it wants (it is a CAT after all), but we'll start video if one comes. Later in the day is usually more active.

## Introduction to version control with git

Materials: [Git intro](https://coderefinery.github.io/git-intro/)

- What do we need to follow this lesson?
    - Minimum: GitHub account, optional git installed for terminal, Visual Studio Code (VSCode)
    - [More info, see Installation](https://coderefinery.github.io/installation/)

### [Motivation](https://coderefinery.github.io/git-intro/motivation/)

- Does usage of Git really benefit, all of this (version control, etc) can be done manually by storing them somewhere, backing up, etc.
    - You mean, git compared to making copies yourself? If so, yes!  you can easily cp to make backups, but you can't search through and use that history as well.  You'll see powerful things in day 2 and 3 (and even the basics are easier)
    - Some operating systems (Win and Mac) can allow for automatic version control of a folder so that you can travel back in time for the last 30 days. The advantage of git is that you can travel back in time on your code with more fine grained detail, for more than 30 days (without mentioning the advantages of collaborating or sharing the code with others). If you work alone, will never share your code with anyone, and don't care about going back to a previous working version of the code, then git might be an overkill for your case. However, if you work with others, if you need to show what you did with your code for a publication, if you need to be able to rerun your code in X months in the future, then git is definitely the tool to use. (Code availability statements are becoming commong practice in peer review / journal submissions).

- The page that the instructor is showing now, would it be helpful to review this prior to the lessons?
    - Not necessary but of course any reviews are good
    - For this workshop we decided it is not necessary because the instructors have the time to go through it with you.
    - We are however always further developing the workshop format and materials and would like to hear your feedback:
        - Was the introduction too fast, do you feel it would have been beneficial to read through the materials beforehand?

- What's the difference between GitHub and GitLab ?
  - Both are web platforms that use the same basic format.  Different companies making similar things - biggest different is GitLab has an open core so it can easily be self-hosted at universities, etc.

- Should we add version control to all our works and preliminary scripts or this is just for final steps when we know where we are going?
  - We would say, always start early - since you might make mistakes and need to go back even at starting phase.  Most of us `git init` as soon as we start something.
  - If you really don't want that history later, you *can* remove it.

[Copy and browse an existing project](https://coderefinery.github.io/git-intro/browsing/)

- Is it easy to transition from GitHub to GitLab or vise versa if you know one?
  - if you have a good understanding of the concepts, yes, however, one has to be aware of some differences in terminology, different words for the same thing, see for example [GitLab info on terminology differences](https://about.gitlab.com/blog/2016/01/27/comparing-terms-gitlab-github-bitbucket/)


### [Exercise: Browsing an existing project](https://coderefinery.github.io/git-intro/browsing/#exercise)
In team/on your own: until XX:06 , then break (until xx:16)
-> Try to do most of this.  Follow solution if you need, it's designed to be followed

I am:
- done: ooooooooooooooooooooooo
- not trying: oo
- had problems: oooo
- everything was good: oooooo

- Where do we record the answers to the exercise? Just a local e.g. word file?
  - Do you mean for credits? Yes, keep some notes in some other file (for days with local work, the work itself will be the copy)

- Where can we find the history of a repository ?
  - Check the solution, it has screenshots and so on.

- Is it possible to find use GitLab instead of Gihub for the fork?
  - Not for "fork" in the sense of this lesson.  You *could* clone this and make your own copy on a GitLab, but that's too much for right now.

- Where to find the history in GitHub?
  - Check the solution, it has screenshots. The solution is also a guide.

- I forked the recipe-book git and when I tried searching for "salt" at the top bar it returns an error saying "This repository's code is being indexed right now". What went wrong?
  - Ah. Interesting - I think it just takes some time to prepare. Wait a few seconds/minutes and try again.
  - There is a note on that. It takes afew minutes to create the index the very first time. Go ahead with the other steps and then retry searching later

- I have signed in but the url is still https://github.com/coderefinery/recipe-book does this mean I am on the streaming repository? I did, it redirected me to sign in. I am not sure how to get the url to include my username - sorted, Thanks.
  - Did you do the "fork", as in this section: https://coderefinery.github.io/git-intro/browsing/#creating-a-copy-of-the-repository-by-forking
  - (and no, this shouldn't be streamed even like this)

- When trying to search for recipes who has "salt" I got 'This repository's code is being indexed right now. Try again in a few minutes.'
  - We have a note on that. It takes few minutes. Start it, continue to other steps, then return to it and index will be ready. This is needed only the very first time.

- Why is the timeline on GitHub different from the one found using "git log -graph". Specifically, I am not able to see the two branches not merged into main.
  - So, those non-merged branches are in the coderefinery/recipe-book
  - Locally when you cloned, Git created only one local branch, main, and this is the one you see with "git log". More about local and remote branches later.

- In the VS CODE, after typing "git annotate sides/guacamole.md" in the terminal, it showed the history but it is now stuck and I can no longer type anything there, how to fix that, should I use a short-key to exit from that mode? (It showing (END) after the history)
    - You can press the "q" key to exit

- What does "Blame prior to change..." mean? I feel a bit confused :( I understand "blame" will show when and by which commit each line was last changed.
    - "Blame prior to change" will show changes before the last change – if you decide that the shown commit is not the interesting one (e.g. it only fixed something trivial in the line) you can use it to go further back in the history


- How do you update your forked repository with the latest changes of the original?
  - We will practice this on Thursday but if you want to try it already today: it is the "Sync fork" button that appears if your fork is behind


- How one may decide the type of license to use?
  - Next week we actually have a lesson on called "Social coding" that talks just about this!  Roughly, I'd say start with what you want: reuse or not?  And do you want reusers to need to re-share changes?

- Why is my network graph different from the coderefinery one?
    - What is the difference (roughly)? or what is missing in yours?
        - Small differences in owner?

- The issues tab is not visible on my repository copy. How do I enable it?
    - You can enable in settings but it may make sense to only track issues in one central place.

- My fork is public, possible to make it private?
  - Under Settings → General → Danger Zone → Change visiblility you can do it.
    - "For security reasons, you cannot change the visibility of a fork."
    - Hm, interesting.  It just worked for me.  I wonder if it's because I'm an owner of the repository...
    - "A fork is a new repository that shares code and visibility settings with the upstream repository. All forks of public repositories are public. You cannot change the visibility of a fork." (https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-permissions-and-visibility-of-forks#about-visibility-of-forks) didn't know this either
    - Interesting
    - Might be (at least to some extend) an attempt to make copyright violations more difficult.  Essentially an owner can have a look at what was done with their code.
    - According to this [StackOverflow answer](https://stackoverflow.com/questions/71446341/what-security-issue-is-caused-by-changing-the-visibility-of-a-fork-on-github) it seems the reason is mostly that you cannot really keep the content of a fork of a public repo private, i.e. its content could be accessible via internal GitHub stuff
        - If I get the comment in there right, it's essentially that, since GitHub links all content of repository forks into the "upstream" repository, this would mean, that anything in your "private" fork (on GitHub) will be part of the "upstream" repository, so someone could start digging around in the upstream to find your supposedly private changes and GitHub esentially decided, that it's easier to disallow making it private than try to "decouple" forks.

- I am using VS CODE, but "git graph" did not work for me when used in the Command Line.
  - Did you define the alias: No, how to do that.
  - Run this command: `git config --global alias.graph "log --all --graph --decorate --oneline"`
      - Reference https://coderefinery.github.io/git-intro/configuration/#useful-alias-for-the-command-line
  - So, it is not possible to have a graphical history in the VS CODE?
      - There is a plugin https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph but I have never used it (I prefer using git from the terminal)
  - I think you can with extensions but we don't want to make a recommendation (yet).

 - One of the ways in which I have misused git is that I commit very little. I always feel that I want to have things in slight  better share before the state is recorded. Can you comment on how to develop a more commity mentality?
    - My personal philosophy is something along the lines: "There is so much bad code around, it doesn't hurt if my 'bad' code is available.", so I try to just add whatever I was working on, hopefully split into logical units and put it into my repo. Also: even small seemingly innocent changes can alter functionality, and might be difficult to track down if you don't have the "steps in between" stored somewhere.
    - One (advanced) technique when you commit code to another project is to first do a branch with many small commits that allows you trying out things, going back, etc. Then, before proposing a pull request, you do a new branch and use interactive rebase to merge your commits into fewer, "clean", commits. But a bit too advanced for day 1 of git :)
    - comment from fellow student: I managed to get myself to more commity mentality by thinking that the repository is my worklog. Early in the (research) process my thinking is not clear, so my commits are junk and commit messages reflect that. Going on, my thinking gets clarity and my commits too :) Good commit messages are the key for explaining what was done and why.

- Why does one need to create a fork, and not just clone the main repository?
  - For the first exercise this would have worked well. we just wanted to prepare you better for the next two exercises where we will create commits and branches and in this case you would not have write permissions to the central repository unless we add you as collaborator.
> Note: git blame for annotations: which commit changed which line of code

### [Solution and walk-through](https://coderefinery.github.io/git-intro/browsing/#solution-and-walk-through)

### [Committing changes](https://coderefinery.github.io/git-intro/merging/)

- I can see only the day the changes were made but not the exact time. Normal?
   - you can get exact time with "git log" locally. I am wondering whether on GitHub one can change from time-delta to time to see the time stamp instead of difference?

- It's difficult to hear the speaker on Twitch right now
  - Thank you for the feedback, we have adjusted the sound level.

- When trying to create mixed-nuts.md on CMD I get error: 'fatal: pathspec 'sides/mixed-nuts.md' did not match any files'. Why?
    - what path are you in? I.e. are the pathes you specify correct (sides needs to be a directory in your current path and it needs to contain mixed-nuts.md)
    - I see, I have to cd to sides first.
        - no, if you are in you base directory of your repository, and use `git add sides/mixed-nuts.md` git will look in the `sides` directory for the `mixed-nuts.md` file.
        - Alright. So I first need to create mixed-nuts.md
            - yes, you can only add files that exist (or have existed in the repository, i.e. when you manually delete a file and then add it it's the same as if you would do `git rm`)

> Note: The instructor mentioned LaTex. [LaTex](https://www.latex-project.org/) is a typesetting system, super helpful for writing publications, e.g. via online editors like [Overleaf](https://www.overleaf.com). For making LaTeX easy to use, https://typst.app/ is very neat.

- You mention that we should work on our own fork, but is it really possible to cause any damage to the original? I tried and got an error message that changes will only occur in my own fork.
    - Could you copy/paste the error message? And was that error message on the GitHub web page or after a terminal command?
        - When I tried to edit I get "You’re making changes in a project you don’t have write access to. Submitting a change will write it to a new branch in your fork "
            - So this was on the web-page. Yes, if you don't have write permissions to a repository, you can't change things in there.
    - No damage is possible. If you start by creating changes to a repo where you don't have write access to, it will create a fork for you.
        - But if you would have write access there are ways to modify a repositories history, which could delete data from the repository.

-  Maybe a bit unrelated, but how to create an .md file in the folder and not in GitHub?
    - depending on your operating system. On Linux: `touch newFile.md`, On Windows: `copy NUL newFile.md` or, on any OS go to a browser, say New -> File and rename it.
    - So after renaming it still is name.md.txt. I just copied one of the previous and renamed it, seemed to work.
        - This is likely Windows "hiding" the file extension. Do you show file extensions in your explorer? If you go to "View" you can Check the "File name extensions" box. This will show the extensions and will allow you to also change the extension. The explorer will ask you to confirm that you want to change the extension.

- When one is working on VS CODE or the terminal - how does one then link the changes made to their GitHub account?
    - By pushing the changes. I think this will be discussed later on.

### [Exercise: Practice creating commits and branches](https://coderefinery.github.io/git-intro/commits/#exercise)
In team/on your own: until XX:55, then we reconvene on stream
-> Try to do most of this.  Follow solution if you need, it's designed to be followed
I am:
- done: oooooooooooo
- not trying: oo
- had problems: o
- everything was good: ooooo

- When committing, there is an option to make a branch. How is that different than that we now started with creating a new branch?
  - It's essentially the same. Creating a branch first is just closer to what you would normally do if you don't edit on the web-interface but on your local machine.

- The network graph does not want to load, should I just be patient or can I do something else?
  - Yes, try reload after a minute or so
  - The "problem" here is that there are now many new forks of this repository and this graph shows all related forks/branches in those forks.

- In step (6) Compare the brances, where do I access the compare changes view through the UI (and not through the URL)?
  - On GitHub you can add a "/compare" behind the URL and from there it is easier to compare branches and commits. We need to add this to the solution
    - I opened an issue in the lesson repository: https://github.com/coderefinery/git-intro/issues/457

- I have an error ![](https://notes.coderefinery.org/uploads/fe943003-b0c9-473b-a84d-f76d2a1bed14.png)
    - This could be due to the tag name already being in use.
    - You need to click on "Choose a tag" above, chose a tag name and then ask to create that tag. It is a bit confusing, the place where you entered "data" is the *title of the release*, not the tag (even though both can be then same, e.g. for something like "v1.0.0"). Where you entered "tagtagtag" is a description field for the release.

- I don't really understand how tags work. And what's their connection with releases and branches
  - This is important and it should be covered in the stream.
     - We will discuss this on stream. In short: a tag is a label to a commit, very much like a branch. But a tag does not move. GitHub introduced "releases" which are tags with some metadata. Under the hood a "release" is a tag. If you create a tag locally on your computer and push it to GitHub, it will show up as release. We will practice pushing changes tomorrow and on Thu.

- Using VS Code. When committing, I was later prompted to push before committing again. I did. Should I have done that? Is there a strategy to when to just commit and not push/ when to push?
  - If you don't push, the commits only exist locally. This is perfectly fine for until you want to make your commits visible on GitHub.

- I created a new branch on GitHub. How can I change its name using the terminal?
  - It will be easier to change on GitHub
  - But on terminal:
    - `git branch -m old-name new-name`
  - This seems to not work: I think it might have something to do with the branch not existing locally. It's calle remotes/origin/new-recipe and when I switch to it using `git checkout` it appears as (`HEAD detached at origin/new-recipe`)
      - Did you do `git switch new-recipe` or `git switch origin/new-recipe` ?
  - Nice! No I used `git checkout`. This works. Still very confused about the detached HEAD terminology but I guess there will be more on that later?
     - detached HEAD: you have switched to a commit that no branch points to. you can then still look around and even make new commits but you will have difficulties later finding the new commits. So first create a branch, then new commits. If there exists a remote branch origin/new-recipe and you type `git switch new-recipe` it creates a local branch tracking origin/new-recipe. The remote vs. local branches we will explain a bit more tomorrow. If you type `git switch origin/new-recipe` or `git checkout origin/new-recipe`, git brings you to the commit but not the branch. This is because the origin/... branches are read only.

- Do you usually only add tags to the main branch?
  - Tags are added to commits which are typically on the main branch. When GitHub asks you where to create tag from and offers "main", your tag will be assigned to the commit that is referenced by "main". But the shorter answer is: yes.

- Is GitHub like Jenkins?
  - Jenkins is similar but not exactly like GitHub, but it uses the git technology like GitHub. The git technology on its own does not require web-interfaces like GitHub, one can use git even without an internet connection (e.g. for a sensitive project that should not be on the internet). GitHub adds a series of services on top of the core git functionality like browsing the code and comparing differences as we saw. Jenkins is more comparable to GitHub actions: pipelines of processes that can be triggered by changes on the code (e.g. an action can be "Rebuild the coderefinery HTML pages when a new change is committed in the coderefinery webpages repository"). For an in-depth comparison, see https://k21academy.com/devops-foundation/github-actions-vs-jenkins

- I am confused. In step 5 I should see my commits and you write in the solutions go to: Insights tab → Network view. But then I only see the other users, no commits.
  - In the network view you see what each user has done (i.e. what they have committed.) Once the graph opens, you can move around the graph by clicking and holding. Any dot on the graph is a commit, and if you hoover over one you will see the commit id.
  - You created commits on GitHub but cannot see them in your network overview?
  - Solved. Now I see it, thanks!

- A problem. I am unable to change name of branch. I don't see the three dots on the right of "view all branches"
  - on GitHub, next to the branch name button, there are "N branches" or a symbol. If you click on it, you land at github.com/youruser/yourrepo/branches where you see an overview and there on the right side are the three dots?
  - Solved, thanks!

- I got an error when trying to sync my local changes from VS Code to GitHub, because it says I have divergent branches. Is this because I first did the exercice on the GitHub webpage and then in VS Code? It it says I have to choose if I want to 1) merge, 2) rebase, or 3) fast-forward only. What is the difference between these options? I managed to solve it by choosing "merge", but I'd like to know what the options mean. Thank you.
  - It means that the same remote branch on github received different commits than the local branch.
    - merge: Nerge the remote branch into the local, creates a merge commit
    - rebase: Same effect as "merge" but without creating a merge commit, by moving local commits behind the remote ones, creating a more linear history
    - fast-forward only: Only merge if it can be done without a merge commit

- I am working in Python. As an example, should I create a new branch when I add new functions and then merge to main when they have been tested? Or how would a typical workflow be? Thanks.
    - It depends on how your workflow usually is, but git is independent of any languages you are programming in.
    - So in a Python workflow you could do so that you have your functioning codebase on the main branch. Then it depends if you are working by yourself or with others. And if the main branch is "in production", i.e. if someone else is using the code on main.
        - A general workflow would be, when you have an idea for a new feature, working alone:
            - Keeping main branch for ready, functioning code
            - Create branch from main
            - work on your new feature on your new branch until it is "ready" to be on main
            - Merge
        - And working collaboratively (this will be discussed on Day 3):
            - 1. Create an issue on the repository to get some feedback, discuss the idea
            - 2. Once you made the decision to start working on the feature, you assign the issue to yourself and create a branch to work on
            - 3. On that branch you do as many commits as you want to (depends on your own preferences) while you are working on the implementation of the feature
            - 4. Once done with the implementation you test the implementation, or let others test it from your branch, or do it automatically (we have a lesson on this next week)
            - 5. Either you do the pull request as part of step 4 or you do it after. In the "PR" describe your changes and why you did them, discuss with others if needed in comments
            - 6. Merge to main
    - If you are just by yourself then creating commits on main is fine. Tomorrow we might discuss this a bit more: https://coderefinery.github.io/git-intro/level/#what-level-of-branching-complexity-is-necessary-for-each-project

- I don't still see how the compare works, when I compare in my fork it takes me to the code refinery repository
    - You should be able to choose between different forked repositories and different branches, base:main for example refers to your main branch, username/lasagna refers to the lasagna branch in username's fork
      - "username/lasagna" was a branch name, not by itself referring to a fork. I like to name by branches with my name so that I can find them again and so that others know who they belong to.

- Can I use Git also in RStudio?
  - Yes :)
  - https://jennybc.github.io/2014-05-12-ubc/ubc-r/session03_git.html --> Configure RStudio to use git

- Do I always connect my project to a repository in GitHub when I use Git?
  - No, this is optional. You can create and work with a git repository that resides only on your local file system. It is a good habit though to have additional instances of the repository, on e.g. another server or on a web-based service such as GitHub.

- I am a bit confused with fork and clone. I have forked (on GitHub) and now cloned to VS Code. Is this correct? So do I then need to sync between GitHub and VS code so that both local and remote is identical? But I only see the remote commits, is this correct? Or why don't I see the commits in timeline in VS code? But I can see both branches in VS Code.
    - I don't quite understand the question, but in principle yes, you can sync both ways.  VS Code (by default without extensions) doesn't

- If I collaborate with someone on GitHub I use fork I suppose? But if I just want to use someone elses code I clone?
    - Roughly.  If you don't want to contribute back, you can clone without a GitHub fork.  (you can add a fork to contribute back later if needed).  We'll see more about this contributing back on day 3.

- Is it possible to access the archive later? We might need to go back to these answers later
  - Yes, please see the link to the archive at the top of the current document i.e. https://hackmd.io/@coderefinery/archive-2024-march
  - At the end of the day we will edit the archive notes for clarity and then post on the workshop webpages

- My latest commit appears accompanied by HEAD -> main when I do "git log". What does the HEAD terminology refer to?
  - It refers to the current checked-out branch's latest commit.
  - Hmm ok. Then if I checkout to a different version, to test the code as it was in a previous state, the HEAD will appear on that different commit?
  - Yes, git will refer to this as a detached HEAD.

- Are there any general guidelines and / or could you share any your personal practices and examples in commit messages and branch names. If I am working on my own or setting up practices for a team, what would be a good what to start at it?
  - We'll get a lot more experience and hear more in future days
  - Personal recomendation: start on main branch.  Once there are more lines of work, you can use branches named after what they mean.
  - For commit messages, think "what would I want to know about this change?" - it's a message to yourself later or others now.  (don't be so long you dont' want to commit, though).
  - Anything imperfect is better than perfect that never happens.
  - I'd recommend short single commit messages

- Would you generally recommend working locally (in VS Code or the terminal) and sync to GitHub, or do you use the GitHub webpage for some parts of your workflow?
  - For most real work: work locally, Github is another copy. The GitHub web interface allows some useful stuff, but it's not for intensive work.

> Note: Think of pull requests as change proposals


### [Merging changes and contributing to the project](https://coderefinery.github.io/git-intro/merging/#merging-changes-and-contributing-to-the-project)

- I already have a pull request at my main branch from the new one I created in the previous exercise. Am I supposed to have that or did I do something wrong? It says "new-branch had recent pushes 6 minutes ago"
  - Is this the note that you might want to make a pull request, or an actual open pull request?
  - Ah, I guess it was just a note. Sorry!
  - GitHub recognized that you made a change to a branch and suggests that maybe you want to initiate a pull request. Often this is useful, but if you don't want to create a pull request quite yet, ignore it and continue on the branch.

- What is the difference between a pull and push request
  - There isn't something called "push request". "Push" is "send code to others", you can do this if you have permission. If you don't have permission, you'd say "hey, I propose this change, do you want to pull it?"
  - Note: GitLab calls it a merge request
  - So a 'pull request' is saying do you want to merge, and 'push request' is say do you want to pull?
    - See answer above.

### [Exercise: Merging branches with pull requests](https://coderefinery.github.io/git-intro/merging/#exercise)
In team/on your own: until XX:45
-> Try to do most of this.  Follow solution if you need, it's designed to be followed
I am:
- done: ooooooooooooooooooooo
- not trying: o
- had problems: o
- everything was good: oooooooooo

- Why am I able to see the forks done by other people (to the original repo) from the Network of my own fork? I would expect to only be able to see my own commits and so.
  - Because the repos are related by fork relation and it might be interesting for you to see what other people are up to in their copies. Tomorrow we will create our own isolated repo and then you only see your own commits.

- Any ideas on why it takes so long to load the network graph?
  - Very active workshop :-) First time I see it take so long for such a small repository.
  - For own repos it is typically very fast but now it has to crawl over all the copies and assemble data. Probably a GitHub engineer has a busy day thanks to us.

- (Temporal not related to this) Are we going to learn something about "Actions"? When? Thanks!
  - Yes, we will use them on Thursday, and learn to create them next week.

- Can I move my recipe from one directory to another? I originally created it to the main and want to move it to salads
  - I don't know how to do that on GitHub purely. I would do that in the command line/ terminal (inside VS Code for instance). You can move or rename with "git mv oldname newname" or "git mv oldplace newplace"
  - Anybody knows whether it can be done in GitHub only?
  - When you edit the file on GitHub, you can press backspace in the text entry for the file name, and change the directory


- Now our forked repository is public. Is there a way to make a forked repository not public? Or would you just work locally and update the public forked repository when you are happy with the changes? When we create our own repository, I assume it is possible to keep private, if there is no need to collaborate on it.
  - In theory it could be made private, but it seems that some people can't do that (maybe people who don't have access to the main project?)  We aren't sure.

- If I like the Spanish omelette recipe pull request in the coderefinery/recipe-book-recorded can I get that for my own fork?
  - Oh yes!  Normally, assuming you are following the project, you would click this "Sync fork" button on the main view. That updates you. (locally, this is "pulling from the central repo")
  - The previous answer is ok *only if* the pull request was *already merged* into the central repo. If not, you could follow the link to iamc repo, spanish-omelette brach, and then fork *that* repo and incorporate from there. But as far as I know you can't so to say do a pull request directly from iamc repo/branch to your forked repo.

- How do I undo a merge? Do I just open the main branch before I merged it?
  - Two options: undo the changes but leave the history, or undo the history.  We'll learn more of each of these in (day 2 I hope).
     - Undoing a merge we will not do as part of this workshop but we have an episode. in short: "git revert" more here: https://coderefinery.github.io/git-intro/recovering/

- If I get the workflow so far correct: First we create a fork from the repository we want to add to, then we make commitments to that fork as much as we need to add the element we want, and finally we make a pull request to merge the fork to the original repository. Correct?
    - That is correct. Whoever is the owner of the repo will then decide to accept the pull request or not.
    - (for clarity, for small projects: if you are working alone or own the repository, you can "push" directly if you want)

- A question from previous section: I added something to a recipe from main branch, I added a new recipe from new recipe branch. When I compare the two branches, only the second change (a new file added) is shown, is that normal?
  - A view could show changes on both sides, or only changes that are on one side but not the other.  I guess this view is the second.  (from the command line there are ways to show both)
  - In summary: yes, probably this is normal.

- Is there any reason you would choose to not delete a branch after it has been merged?
  - Yes. Some projects have the workflow that the feature branches stay alive over longer time, months or even years. New stuff is contributed from that branch via pull requests. Importantly new stuff from other branches are pulled in from the main/master branch so that the feature branch stays in reasonable sync with other development.
  - Sometimes new stuff is not pulled in from main to the feature branch for many years. Then you have a problem :-)

- I have no write access to merge pull request to the main CodeRefinery repository
  - Yes this is by design. On Thursday we will create exercise repositories where will give everybody also merge permissions.
  - We wanted to show you that you can make changes even to repos that you don't have write permissions, by creating your own copy

- About creating tags, I can not seem to create a new tag after the previous one I created
  - Hm. Can you make with a different name?

- A question related to previous section. Let's say I am working but have to leave work and my code is incomplete. Should I commit anyway, although the code is not complete or is there another way?
  - It's up to you and your preferences. If I'm leaving and might work on another computer, I might commit to a branch. If I would resume on this same computer, I might now.  If I want to checkpoint my work in case I mess up later, I would commit.
  - You *can* adjust existing commits, which we might cover later.  But there are some risks
  - https://raw.githubusercontent.com/louim/in-case-of-fire/master/in_case_of_fire.png ;)

- What if I am working on several files. Should I commit for each file separately or all together? Any rules of thumb?
  - If the changes are related, then all at once (if the changes depend on each other to work/make sense).

- I understand that "Sync Fork" will work for adding any changes from the original repository to the 'current' branch in the fork. What if a new branch is created in the original repository? Is there way of including this branch into the fork?
   - Good question

### [Solution and walk-through](https://coderefinery.github.io/git-intro/merging/#solution-and-walk-through)


### [Resolving a conflict (demonstration)](https://coderefinery.github.io/git-intro/merging/#resolving-a-conflict-demonstration)

- Ah, the Great Cilantro War of 2024
  - :D

- Is it possible to merge only a part of the pull request (PR)?
  - No, but... If you have conflicts, you need to resolve them and in practice you could remove the changes from the PR, thus only "accepting parts". But from the git perspective what you would be doing is adding a new commit to the pull request that contains your changes and thus you would merge "all of the pull request", since the conflict resolution becomes part of the PR
      - Would it be technically possible for me (manager of main repo) to tell the person who submitted the pull request to revert/remove some changes so that only a subset is merged? (e.g. during the review discussion in the opened pull request)
        - You can comment on the commit and say that this and that should not be in, and depending on how they committed they could revert certain commits (if they are independent), and only leave those commits that you want. What you could also do, is building a branch and only take those commits that you want t that branch. This is called "cherry-picking" and maybe will be discussed later (not sure). But this only works, if the commits really are independent (i.e. have only changes in lines that no other commits have altered)

- How are exactly the conflicts happening? For example, in the case of the cilantro, what if the changed lines are moved? Could be considered different lines and therefore different entries even if they are changing the same thing?
  - With text files (code, markdown, etc) there are tools that can identify which subparts of the text changed even though line numbers are not exactly the same. However they are not that clever, so that at some point the automatic difference stops working.

- CAT! Best possible finish to today's workshop.
  - It even sang us the song of its people
  - <3
  - I was under attack here
      - Did you again forget to feed the cat at the time it decided to be fed?
      - I am very strict, next meal at 16:00.

- What is cat name
  - online name is CATS - anyone get the reference?
      - All Your Base Are Belong to Us?
      - correct

- And is there any good practice guidelines for when to do commits?
  - Logic units, and better more often than too seldom (smaller incremental steps).

- Are we going to run everything that we have done today also in VS Code? In a real-world setting you would not use Git in GitHub like we did today right?
  - Yes!  Tomorrow we go to there.  Make sure you are set up for it (see installation instructions but VS Code mostly works)

- I'm not sure how works on GitHub work can be put in the assignement document. We should sent the git log --all output. But how can I do it on GitHub? And what should be presented for today's session?
  - We'll figure out how to do exercises for this day 1, we hadn't thought about this before we started.

- In a research project, can all files be under git? Or are there some files that should not be included, e.g. Jupyter notebooks?
  - Normally you would have original files, but generated files (figure .png, manuscript .pdf) are *not* tracked: they can be re-generated later from the original files. This is the basic principle at least.
  - For the combination of Jupyter notebooks & Git, there are some techniques and tools available. We will come to that during next week

- What is the most common situation when things get messed up?
  - A surprisingly common and at the same time rather serius situation is when different feature branches over time get more and more disconnected, making upstreaming and downstreaming most complex. When this happens, developers/users of feature A, and developers/users of feature B can loose out of on the fruits of many months (years!) of work.

- One thing I don't understand is installing something vs cloning. In GitHub I can clone, but what if I want to install in my virtual environment? Is it clone first and then install?
  - When you clone from GitHub to a local computer, you get the full copy of the repository. For interpreted languages like Python this might suffice. For compiled languages like C/C++/Fortran, you need to compile, link and install after cloning.


### Day 1 summary and outlook
  - We covered the Git intro lesson episodes
    [Browsing](https://coderefinery.github.io/git-intro/browsing/)
    [Committing](https://coderefinery.github.io/git-intro/commits/),
    and [Merging](https://coderefinery.github.io/git-intro/merging/).
    You should review these if you missed day 1 - the exercises and
    solutions are all built-in there.
  - Day 1 was about learning concepts the easy way (web).  Day 2 goes
    to local work and is real examples of working on your own
    projects: you'll see how we really do it.
  - It's OK to come to day 2 if you haven't come today.
  - For day 2, we'll move to local work.  It's important that you have
    your local VS Code or command line terminal set up to follow
    (though many parts can also be done through the GitHub web
    interface still).  See the install instructions.


## Feedback

Today was:
- too fast: o
- too slow:
- right speed: oooooooooooooooooooooo
- too advanced: o
- too basic:
- right level: ooooooooooooooooo
- needed more exercise time: ooooooooooo
- needed less exercise time: oo
- I will use what I learned today: oooooooooooooooooo
- I would recommend today to others: oooooooooooooooo
- I would not recommend today to others:
- too slow sometimes, too fast other times: o
- It was great. If things went fast, you could focus on the stream, if things went slow, you could do exercices at the same time. oo

One good thing about today:
- It is really nice done,
- Nice organization, timing, easy to follow. I have been using git (badly) for some time and there were still some new things. Nice cat!!
- Quick and thorough answers to questions. Thanks!
- Liked that we had these different "paths" e.g. GitHub, VSCode and terminal +1
- Great flow and well timed swaps between lecture and exercises
- Clear and "for dummies" approach. | oo
- I really like also the tutorial/solutions to the exercises
- great structure, helpful to have both the stream and the written instructions (and different levels of detail on that as needed with just basic instructions vs walkthrough)
- Also I really like the support for both web, VS and command line!
- Nice and understandable overview for beginners! o
- The collaborative document is great and very very useful!!
- The pace was good. Enough time for the exercises.
- Excellent complementarity between live, collaborative document and exercises document.
- liked much the structure and emphasis on learning by doing

One thing to improve for next time:
- i would like to have somewhere recorded  version of how to use bash (on video), because using terminal harder
    - Our prep has a basic video, but tomorrow we will see more examples of command line git.
- Along the workshop I would like to move from web brower to terminal or VS Code
- More cats o
- More cats !!! Dogs are OK too :)
- I did the exercices today on both GitHub homepage and VS Code. It was a great way to learn. I don't know if this is a better way to introduce this in the stream as well?
- I know you said you're preparing it, but I'm excited about RStudio support o
- A demonstration for RStudio will be helpful as well. oo
- JupyterHub would be interesting to go through as well
- I could have used a bit more time for the exercises
- It may be easier for beginners to understand the new vocabulary if you have additional illustrations showing the differences/similarities between e.g. repository, branch, fork, clone etc. oo

Any other feedback?
- Excellent cat content oooo
- Loving the jokes and the general light mood oo
