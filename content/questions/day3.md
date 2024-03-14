+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 3"
+++


---

You can keep asking questions here, we will answer tonight or tomorrow:

- Problem with git bash in Windows. Everything seems to be downloaded, and working in VS code or RStudio, but when I try to open the program Git Bash, nothing happens. Any idea why this terminal won't open?
  - This is a hard one to debug from afar. Maybe my colleagues have some idea on what to try, but sometimes reinstalling helps already



## [Collaborative distributed version control](https://coderefinery.github.io/git-collaborative/)

- Audio from Gregor is not as loud as from the rest of you, struggling a bit to hear him.   Seems better  now thanks!
  - Thanks for the feedback. We will adjust the sound level.
      - Its better

- I find it difficult to navigate through the website (coderefinery.github.io). 
  - I'd recommend starting at the course webpage (https://coderefinery.github.io/2024-03-12-workshop/) and use that to go to each day's place.  Or look at Notes, it always has the links.  coderefinery.github.io doesn't have organization itself
  - We are here now: https://coderefinery.github.io/git-collaborative/concepts/

- Does a fork inherit the commit history and branches of the original?
  - Yes. (There is an option to only copy the master or main branch. For me it's on by default.)
      - Thanks ! :smile:

- What does flattening means ?
  - Here, it means "all past history becomes one commit" to start from
      - is it the same as squash?
      - Roughly yes

> Instructions for  joining the exercise repository as learners without own group: https://coderefinery.github.io/2024-03-12-workshop/communication/#2024-03-12-exercise-preparation-for-learners-without-own-group.
> In short: open an issue at https://github.com/cr-workshop-exercises/access-requests/issues/new/choose (There click "Get started" -> "Submit new issue")

- I'm working by myself. I've been added to "cr-workshop-exercises" and "stream-exercise-participants". Is this enough? Since 
  - yes I think so.
      - Why having a recorded one and a non-recorded one? 
          - the recorded one will be used on stream, so your username might appear there, some people may not want that
          - for the non-recorded, your username will never appear on stream
  
- I am on my own, how to request to collaborate?
    - see line 119 in this document

- Should we use the centralized-workflow-exercice or the forking-workflow-exercice for this exercice?
    - centralized (for exercises 1 and 2), only for exercise 3 we will go to forking

- Could give examples of good github repositories that we can later view and learn from?
    - great question! let's collect some. I would recommend to look at codes or libraries that you or your community might be using in your work. they could be interesting to track.


:::info
### [Exercise: Collaborating within the same repository](https://coderefinery.github.io/git-collaborative/same-repository/#exercise)
In team/on your own: until XX:00, then we will reconvene briefly on stream and then go for a break.
-> Try to do most of this.  Follow solution if you need, it's designed to be followed.  Open a pull request, and then try to constructively review someone else's.

I am:
- done: oooooooooooooo
- not trying: o
- had problems: oo
- everything was good: oooooooo
:::

> We are using : `centralized-workflow-exercise` repository for this exercise

> Remember to accept the invitation to the `stream-exercise-participants ` team first (link in an email to the email address connected to your github account)

- Could you provide a sreenshot where to unwatch repositories. Cannot find it
    - see bottom of the blue box here: https://coderefinery.github.io/git-collaborative/same-repository/#exercise

- When I type 'git graph' into terminal, it said 'graph' is not a git command.
    - It is an alias, you have to configure it first, see: https://coderefinery.github.io/git-intro/aliases/#example-alias-git-graph
      - Thank you!

- I requested access but still cannot add/push commits to the exercise repository
    - In this case the invitation to the repo might be pending. Check your email inbox or look at the blue screen "exercise preparation" for troubleshooting.

- I had a brain freeze and merged my own pull request. Is there an undo button for idiots? :D
    - no problem :-)
    - I don't know of an undo on GitHub/GitLab for merges. On the command line you could undo a merge with `git revert` (see git-intro lesson and episode about undoing)
        - thanks. Cannot use command line, I'm on duty at work and need VPN, command line says no.
    - no undo, the only thing is to revert the changes from the pr. 
        
- Do I first have to merge my new recipe branch to main in my local clone (working in vs code)? Or somehow push this new recipe branch directly to the exercise repository?
    - push the branch to the exercise repo, open a pull request there and then somebody else will merge. you will not merge locally. after it is merged in exercise repo, you can then "pull" the merge to your local repo. is that clearer?
        - Yes it is, I was confused about terminology and the order of steps again -- I now understand that "(3) Make a change adding the recipe" still happens locally and then "(4) Push to GitHub as a new branch" (clicking the cloud icon) takes care of pushing the branch to the exercise repo.

- Would it be better to change 'git commit' to 'git commit -a -m 'message''? because every time I use 'git commit', it always aborts.
    - what you suggest is a good workaround. but there is a solution to this problem. what editor have you configured to be opened for commit messages?
       - vscode
         - OK wait a sec, we have a fix:
           - `git config --global core.editor "code --wait"` this should configure git to wait for the editor to open and not give up
    - Also I personally avoid using the -a flag and manually add what I want to commit via git add as -a just adds everything and often there are some files I might not want to currently commit (e.g. when I have a config file that needs to be there, but currently contains some secrets)...
        - Thank you so much, they are very helpful!
            - Adding to this though, the -m flag is very convenient, since you generally should aim to make short messages anyway and then an editor is bit overkill.

- I cloned the repo locally made changes but I don't know how to open an issue 
    - Issues are added from the GitHub web interface, to the repository that you ~~forked~~ (edit, sorry for confusion) **cloned** in the beginning, up top you will find a "Issues" tab
        - Normally i should fork it and not clone it because i don't see it on Github ?
    - in the first exercise you should not fork yet. we work inside the same repo
    - but once we start forking (exercise 3 today), we will see that issue stay in the "upstream"/original one and the forks typically do not carry issue tracking

- I was expecting that after pushing in the VSCODE, there won't be nee, any longer, to pull in the github repository. Whay it is so? We should always request pull in the github after pushing in the VSCODE?
    - The normal procedure is "pull then push". We are currently in the situation where we have a very high amount of concurrent edits (which is actually not very common). So what you normally do is: You develope on your branch (which commonly is not used by others). Then push that branch to the remote. Then open a PR on the main branch to incorporate your changes. Once your changes are incorporated into main, you pull those changes into your local main branch. If you are working on a branch where others work as well, pulling before pushing allows you to fix conflicts before pushing, and any pushing which creates conflicts will be rejected by git(hub), so you will first need to resolve them before you can push your changes.
        - Thanks for the provided information.

- I think you have already mentioned this, but I am not sure. Is it possible to do a pull request in command line?
    - it is possible and we haven't talked about it. if you use github, then there is GitHub CLI where you can do many things directly from the command line: https://cli.github.com/
        - Thank you ! I'll check that.

- When should I close an issue? 
  - If you use the "fixes #NN" it will automatically close when the pull request is merged.
      - But how does a pull request resolve an issue? The modifications have not been merged to the main branch yet.
        - it only closes the issue after the PR is merged.
            - Ok then I manually closed it before that...
               - you can also manually reopen and let the PR close it (if the PR is still open and if it references the issue number)

- Should we try merging pull requests by other users?
  - yes please
      - It worked!
          -  :) 

- This does not work in gitbash, I wonder how to solve it?
 ![](https://notes.coderefinery.org/uploads/b2248037-1d9f-43a1-842a-235309d2678b.png)
  - This looks like you are currently not in a directory that is a git repository. Have you cloned the repo, or are you currently in one of the subdirectories?
  - I have cloned the repository in my local but still it does not work
    - What directory are you in currently, what does "pwd" (prints the working directory) say?

- Ok, so I have done (4) Create the pull request and now reached (5) merge pull request. But how can I merge since I am collaborator? I am confused. Perhaps I did something wrong. Should I just click "merge pull request"?
    - You should have been added as a developer on these repositories.  If you go to yours, or another, is the button available?
    - I got "Pull request successfully merged and closed"
    - did you merge or someone else? try to merge someone elses if someone else merged yours.I merged, but perhaps I misunderstood. I thought I was not allowed to merge my own.

- I don't really understand the merging. I merged a pull request with mine, and that one now disappeared, while it remained only mine. 
  - Did you merge someone else's request?
  - yes!
  - 
- If I want to pull from the "centralized-workflow-exercise" repository using VSCODE, which command should I use? Should I use "git pull origin"?
    - If you are currently in the repository and want to pull the main branch, just "git pull" should suffice, if that doesn't work try "git pull origin main".
    



- I cannot push. It says: 
```
"remote: Permission to coderefinery/template-centralized-workflow-exercise.git denied to (username).
fatal: unable to access 'https://github.com/coderefinery/template-centralized-workflow-exercise.git/': The requested URL returned error: 403". 
```
- I am using command line.
    - Did you accept the invitation to be a collaborator sent to your email?
    - I think I did. I will retry.
        - I can see you did :+1:
    - Did you create your own branch?
        - Yes, I cloned and then created my own branch locally.
            - Hmm, do you have multiple usernames? You can check your current username `git config -l | grep user.name` 
                - I get my full name. But I have a nickname on Github, which is not my full name. 
                    - Ah, yes sorry this should be full name, so this is fine
            
            - Or what was the command you used to push?
                -$ git push origin boiled-eggs-recipe
                - this is the command I used to clone: "$ git clone https://github.com/coderefinery/template-centralized-workflow-exercise.git
"
            - does this command work for you ` git config --get credential.helper ` ? -> does it show something when you execute it?
                - It shows "manager"
            - more help coming :) 
     - Did pushing work yesterday?
     - You might be on the wrong repository.  It should be this: https://github.com/cr-workshop-exercises/centralized-workflow-exercise.git (the other URL I see above is for the template that is for preparing.)
         - `git remote set-url origin https://github.com/cr-workshop-exercises/centralized-workflow-exercise.git`
             -Now it works. Thanks a lot
            
- I forgot to make a branch and git added to main, how to I fix this?
    - in this case create a new branch from main and push/publish that. you might also later need to "move back" main but that is more advanced. we have an episode on that in git-intro

- I did commit to the main but when I try to "git push" I get the error `Changes must be made through a pull request.`. How do I fix this?
    - main branch is write-protected and you cannot git push to it directly. in this case make the change on a branch that has a different name than main and git push that branch

- I have my branch open locally still, but it has been merged at origin / upstream. What should I do if I want to edit the recipe I submitted (that is now merged)? Should I close my current local branch?
    - Create a new issue, commit changes to the repo, then create a new pull request with your repo. Be sure to reference the issue in your commit message! Alternatively, you can create a new local branch, and follow the same workflow you did earlier.
    - Should I have a new branch locally?
      - Not much need for it, but you can do that if you want to.

- When trying to push my new branch into the remote repository it asks for a github account, but with other pushes I usually use a key generated and I don't understand why is not working in here?
    - It's important that you clone the repository using the SSH address, not the http

- Why can't we have additional commit message in VS code as it is in the GitHub interface
    - You mean the extended multi-line message after the first line?
    - if you push enter it seems to let you do a multi-line message.
    - The "Pull Request message" is a different thing and just a concept of GitHub

- I have pulled from the github using "git pull", but the problem is that it is not fetching all of the new changes. For example, the moment, there are lots of recipes in the desserts folder of github, but mine after pulling does not fetch all of them.
    - Oh yes!  This is the "update the fork".  Checking for link...
    - This is from another lesson but is what to do: https://coderefinery.github.io/git-collaborative/forking-workflow/
    - **Instructors:** should people do this now?

- Isn't it possbile to push somethin in the github without performing issueing?
  - good question, answering on stream ...
  - Yes!  Issuing first is mainly useful when you need to coordinate with others.


- So even if I work alone I can (or should) create an issue as a suggestion for myself? I mean to keep track of changes I want to implement.
  - Yes, of course. If you find it helpful then it's a good idea, and it can help you later to see what your though process was more than a simple commit message.
  - Thank you, this was useful. I will use this in the future. I have always thought about it as keeping track of problems/bugs.

- The pull in VS code same as pull request in GitHub interface?
  - Yes
  - so then which one synchronises from the remote repository to the local repository.
  - ah, it seems I may have misunderstood your question slightly. "Pull" is a git command, which syncs the local repo and the remote repository. "Pull request" is a feature by which one can ask to "merge" suggested changes into the main branch.
      - "Pull request" is a GitHub thing, not purely Git.
  - So I can merge a branch to the main in VS Code without necessarily making a pull request?
      - Yes, in your local repo you can do whatever you want, but if  you want to later push the commits to GitHub, you should have permissions to commit to the main branch in GitHub.
      - this is only when I am collaborating, or? -> Collaborator can have permissions to pull directly to the main branch, the repo owner sets this when inviting you. Or... if they protect the main branch in the repo.
      - Yes, today is "git collaborative" and we see how bigger projects might work.  Most projects some combination of day 2 and day 3.
      - Ok Perfect. How then if one is the "manager" of the repo, create that access or permission before anyone can merge to the main branche -> that's it!

- Are there ways to see if there are mistakes in the code/file e.g. spelling mistakes are highlighted in github or if it's a 
  code file that it checks the typical spelling of functions (...)?
  - In the exercise after lunch, we'll have an example of automatically detecting some problems.  And you'll learn how to do it yourself on day 6.  It is really cool. Thanks!

- From the Twitch chat:
  - @CodeRefinery should "base: main" be changed or not? This page suggests we want to change it https://coderefinery.github.io/git-intro/merging/
  - Before, it should have gone to your user since you were modifying your own thing.  Now we are contributing to the central repo so it should say "base:main" since you are in the same repo.
  - (Or in the "compare across forks" view, it would say "base repo: cr-workshop-exercises base:main" <- head repo:cr-workshop-exercises compare: [your branch])



:::info
### Exercise Practicing code review: https://coderefinery.github.io/git-collaborative/code-review/#exercise
In team/on your own: until XX:00, then meet briefly back on stream before longer break
-> Try to do most of this.  Follow solution if you need, it's designed to be followed
I am:
- done: oooooooo
- not trying: o
- had problems: o
- everything was good: oooooo
:::

---

- Why creating a new branch? Can’t we just keep using the same branch, with new commits to it, and then open a pull request to main? 
  - creating a new branch for a new pull request? Yes
     - reason: PRs (pull requests) are from branch to branch. if you add new commits to the source branch, they modify the pull request. you would otherwise accidentally modify older still open pull requests. to avoid this: each PR has its own source branch. then you can move on and no risk of surprise and confusion if somebody reviews it 3 weeks later.
    
- Ok, continue from previous question. So does this mean I must first pull the remote/main and create a new branch from this? Or where do I start the new branch from?
    - yes, you typicall start from main and first update main before creating the branch. unless there is a different convention in the project you contribute to. some projects use different branch strategies. Great, thanks.

- I do not have the suggestion symbol. Ho can I add a single comment as suggsested in the exercise?
![](https://notes.coderefinery.org/uploads/3e955d64-842a-4b75-8926-7646a2323b3b.png)
    - hmm interesting. I wonder whether you perhaps have no write permission to the repository? have you been able to create branches on it?
    - you could also try this on a repository that you create just for testing whether it works there.
         - does this mean if I work on other' perople's branch, I need to create a branch on other people's branch? 
           - if you have been added as collaborator, you should be able to add suggestions to other people's branches. no need to create new branch.
           - Yes I could add suggestions but how could I add as the example?![](https://notes.coderefinery.org/uploads/9cc954dd-0530-49cb-b693-07f733b844c9.png)

- I had the same, but you really need to pres the plus in front of the line you want to edit. I hope that works :)
  - I pressed th plus and nothing more shows up

- For some reason my pull requests are not linked to the issue. I am using ";fixes #nn" in both the commit and the pull request title. This is the case with issue #55 and pull request #56. Any idea why? - Update: Hmm, that is strange. I don't see the "linked pull request"-symbol on my issues list. 
    - OK looking ...
    - they are linked. navigate to the issue and you will see that they are cross-referenced. but the issue will only be closed once the PR is merged to the default branch (main). if this was what you meant/expected and did not see yet?
    - I was expecting to see the "linked pull request"-symbol next to the issue on the issue tab. And I still don't see it. 
      - in hindsight it makes sense since otherwise anybody could close any issue just by opening a pull request. we need the review step and the accepting step. 
      - Update: OK, when I open the issue, I can see the commit I have made. But maybe the pull request is not linked, because the commit is linked? I still don't see the "linked pull request"-symbol next to the issue. 
           - yes exactly. I wasn't looking carefully enough.
               - Great, thank you! 
 
- My pull request has been merged and the branch closed remotely. I should probably close my local branch now as well, how to do that in Git Bash?
  - You can remove the branch with `git branch -d <branchname>`. Using "-d" option makes sure you can only delete it if it has been merged. (In contrast to "-D" which deletes the branch no matter what.)
    - Thanks, very useful to know the difference!

- Should I use "git request-pull origin my-recipe" in the command line of VSCODE to request a pull? It is not working, or I am doing a mistake.
    - TLDR: it's not the same thing as pull request. My understanding is that "git request-pull" is an old command that is separate from pull requests. It basically enables a similar workflow in cases where you don't have your repository hosted in github or similar.
    - Is it possible to request pull in the VSCODE, then?
       - we are checking. probably possible with an extension?
       - GitHub: With the GitHub Pull Requests extension
       - GitLab: With the GitLab Workflow extension
    
- How to resolve conflict?
   - if you see it on GitHub, there is a resolve button. once you click on it, you see the conflict and you need to decide which of the two versions to keep. remove the conflict markers, then 'mark as resolved' and commit the merge. in the recording from day 1 we resolved a conflict in the last episode of day 1.
    
---

:::info

# Lunch break until 12:00 CET/ 13:00 EET

CodeRefinery workshop: https://coderefinery.github.io/2024-03-12-workshop/

:::

---

- I would like to start actively using git (and GitHub) to show what I have done for my thesis, how can I get started?
    - The lowest entry barrier is to create your personal website using github pages! The best template that is around these days is https://github.com/alshedivat/al-folio (you can have a look how your website can look like by browsing the demo site: https://alshedivat.github.io/al-folio/). You could try to keep a learning blog (and write about coderefinery!), share the code from your thesis, or just have a place on the internet to showcase your work/publications/cv etc. And since it all happens via git/github you also show that you can master all of the things you've learned in these 3 days.
    - We will also talk a bit about github pages in next weeks documentation lesson ( Day 5: https://coderefinery.github.io/documentation/)
      
- Is it worthy to get the github pro account to get repo synched all the time, or is there other options?
    - I need to verify this but I think that if you have an email address from a higher edu institution, then you can apply for the student or teacher github account and that makes you "pro".
    - RB: yes I got it through my university somehow. I do not pay as individual for the account.
    - I'm not sure what it means to "get repo synced all the time" - normally you can push/pull as needed, I haven't done other syncing.
    
- When I commit my local file to main branch, I don't know which folder my file exists on github. I checked the network, my branch has merged with main branch, but I cannot find my file that I commited.
    - You can get a list of all committs recently done on the repo via github interface. Do you see the commit you did locally?
      - Sorry. I didn't find 'all committs recently done on the repo' via github interface... 
      - I know if I use 'git graph', I can find all commits. Is this the same to the results via github interface?
      - I found it. Thanks.



## How to contribute changes to someone's repository
https://coderefinery.github.io/git-collaborative/forking-workflow/#

- CATS!
- That is one great cat!
- The cat strikes back

- Could you share how do you usually strat a new repository? Typical directory organization or good templates you can recommend? 
    - We will cover this next Tuesday. Here a reference that everyone should read :) https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005510 see "Box 1, section 4".
    - Tuesday lesson: https://coderefinery.github.io/reproducible-research/organizing-projects/ (we are still doing small updates to next Tuesday lesson)
    - I personally don't start project repositories from a template, but I create the "data, results, src, docs" folder... but maybe we should have a template :)
    
- Do you keep all files related to project in same directory and code is in a subdiroctory? Or do you have a directory for "Code" with subdirectories for each project?
    - This is what some do here at Aalto, but there is no single good answer:
        - A shared project folder that will be the container for everything
        - A (source) data folder (things that should be read only)
        - A code subfolder with sub-subfolders src, docs, results, data (<- data that can be shared with the repository e.g. external data to combine with source data)
        - Other subfolders (e.g. manuscript, user specific subfolders, derivative-data folder for things that the code produced from the source-data)
        - If there are many repositories as part of a single project (e.g. one for a new library being developed, another one for the pipeline that uses the library), GitHub offers "github projects" where you can have a [kanban board](https://en.wikipedia.org/wiki/Kanban_board) for all the issues of the linked repositories and other project management features.
        

- Can you comment something on test deriven development and its application in research?
  - Can you ask this again at the end Q&A? (OK :) )  This deserves a longer live Q&A
  - Day 6 has a dedicated testing lesson.

::: info
## Exercise 
### https://coderefinery.github.io/git-collaborative/forking-workflow/

In team/on your own: until XX:55
-> Try to do most of this.  Follow solution if you need, it's designed to be followed. This time exercise participants cannot merge (no write permissions) and we will help reviewing and merging some.
I am:
- done: ooooooooooo
- not trying: oo
- had problems: o
- everything was good: oooooooo

:::

- "in the commit cross-reference the issue you opened" Can I reference an issue that is open in the original repo, not my fork that I have cloned?
    - Oh yes, reference in original repo (the one that you will send the pull request *to*)
        - Ok, so I push local changes to my fork and then create a pull request for the original one?
             - yes

- I commit my changes in main so I need to revert this change and then create a branch to repeat it. How to revert a commit from github web?
    - We don't think so
    - But try this: instead of making the new branch from your own fork.  Go to the main repository, click "edit" (from that main branch), and we *think* that would offer to make a new pull requst branch *from the right place*, and let you use it for your pull request.
    - some more background and this is advanced: there is "git revert" which creates new commits that can do the opposite of previous commits. and then there is "git reset" (cannot be done on github as far as I know, you have to do it locally) which can move branches back. strategy could be: create a new branch from main, then locally move "main" back. but then when you try to push the branch that has moved back, github will complain (it does not want you to accidentally delete commits) but then one can force-push.
      - example of this:  https://coderefinery.github.io/git-intro/recovering/#recovering-from-committing-to-the-wrong-branch

- How do you cross-reference the issue in the commit of a fork of the repo? I created the issue upstream (the issue tab is also not available in my fork)
    - did you make the issue in your own fork, or the upstream?
    - you would cross-reference it the same way as in previous exercise, e.g.: "I did this and that; fixes #123" (assuming you address issue 123). This should cross-ref the two, even across the fork-relation.

- Observation: It seems the "fix #nn" cross-reference to an issue can be used in the title (first line) of a commit, but only in the comments of the pull request. If put in the title of the pull request, it does not in fact cross-reference. 
    - Good point. But I think it will still auto-close it. If you visit the issue. Do you see the PR mentioned there (before merging)?
        - If I only put it in the title of the PR, I don't see the cross reference in in the issue. I haven't tried merging to see if it still closes the issue. 

- I'm sorry, I missed how you can implement automatick checks. Where do you specify the program to run?
    - The action is defined in .github/workflows/, and it calls check_recipe.py.  We'll learn more about this on day 6 and show how to set it up! The goal here was only to show that it is possible.

- What if I want to change something after my pull request has already been improved? Do I need to make a new branch 
    - No need to make a new branch, just create a new pull request from a new commit in the same branch!
    - Do you mean brand new change, or further improving your pull request?
        - I'm sorry, I meant to type "approved" not "improved". I reopened the branch, fixed my recipe, and created a new pull request. I think that's the way to do this? I'll see if my pull request gets approved :D

- I noticed something called labels and milestones. Have you discussed this or will discuss it? .
    - We don't usually discuss, but roughly: labels are ways to label pull requests, helps to manage lots of them. "milestones" is a term from software development, development goals in the future (what needs to be done before X milestone?)

- I also found that there is an inbox in github. Is that the same as getting notified by email? If so is there a way to just get in github without getting email?
    - You can disable email in the settings somewhere and only use the GitHub inbox. Thank you.

- I am still a little bit confused about the difference between a branch, a fork and a clone. I feel like they do all the same. 
    - we will clarify during Q&A - this is a great question

- We are missing the "Issues" tab in the forks GitHub web interface. Is this supposed to be like this? If so, how do you work in a branch, in your fork? Without issues?
    - Yes, this is intended. Issues can be enabled in the repository settings. You are meant to discuss in the issues of the original project.
        - In the settings of the forked repo? We can not find it anywhere. Sorry, found! Thanks
    - but it can be clearer for projects to know that there is only one place where issues are tracked

- Is it that when I fork a repsoitory using the web interface I still need to clone it to work on it locally. So in reality they are not mutually exclusive?
    - correct.


:::info
# Break until XX:05
:::

- why is github important and necessary ?
    - GitHub is one of the standard platforms, it is likely you will encounter it as part of your work (many large software projects are on GitHub)
    - convenience, many tools to use

- We have a self hosted Gitlab instance at the lab. We were wondering if you had some clues on best practices for selecting what to publish to github or the lab's gitlab respectively? We struggle to define a workflow that optimizes "control" and "public access" to the research we do.
    - for public collaborations: use something public 
    - something you want to keep private: keep it on private instance
    - you can also create mirrors later, eg mirror from gitlab to github. Your work on gitlab is still safe
        - can be challenging when one is updated

- check is not so clear to me, what is the check, who creates it and ho does it work.
    - refers to automated tests
    - There will be a dedicated lesson on this topic next week, day 6: https://coderefinery.github.io/testing/
    - You can tell something called "Github Actions" to run code which does whatever you want.  It can report success or failure.  We had it test for titles in recipes.  We'll learn more next week (link above)

- Please remember to include the feedback questions in this document.
    - check, below

- What's the practical difference between branch + pull and fork + pull?
    - For branch + pull you need to be a collaborator on the repository
    - Forks you only need if you are not allowed to create branches on a repository; interesting for very big projects

- How user-friendly is the GitHub interface for beginner developers?
    - what do you all think? was it easy to start using git through the web interface?
    - it was good because i was following steps but does it be hard to continue 
    - I think the GitHub interface is good, especially now that I know what a lot of the buttons are for.

- how important is GitHub for job applications
    - depends on the job you are applying to
    - if it is related to software development and related to FOSS, then a  public GitHub (or other) repo that shows some of your work is probably necessary to get the job
    - I don't think anyone would hold it against anyone if they used GitLab, BitBucket, self-hosted, etc: as long as it's avaliable as a "portfolio" somewhere

- Can you comment something on test driven development and its application in research? (copied from above)
  - Testing is probably very important for research: you need code to be correct, right?
  - test-driven development is one style (write tests first, then write code for tests).  This may or may not be right for any particular case
  - (Please remove if this is consider promotion or otherwise inappropriate) University of Helsinki has a free MOOC course on Test-Driven Development: https://tdd.mooc.fi/

- difference between sync and merge
    - sync is merging both ways "under the hood"

- can we use the learning materials you have published to do workshops on our own at the lab? Do we have to register somewhere? (Amazing work by the way!)
    - Thank you! You can reuse them as you like :) 
    - Just check the license of each lesson you would like to reuse, most of them are CC BY 4.0 , see also https://coderefinery.org/lessons/reusing/ (*thanks!*)
    - If you reuse them, also let us know! When we know where people are reusing our materials, it helps with further funding applications and work on more material
    - We are also working on making the lessons citable and make them findable and persistent on Zenodo

- What if I want part of a repository private but the rest public? As I understand it is not possible. At the same time I want a backup of everything. 
    - Usually it is either public or private, you cannot have both at same time.  Things are repository-level granular.
    - You could check out submodules (separate repos but linked); have a public "mother" repository and then have another private repository which you include as submodule (for example the secret data) (not tried, but could imagine that this could work)
    - Or, keep two separate repositories and have them refer to each other.



## Feedback, day 3

:::info
### Day 3 news
- We covered the things listed in the schedule: three exercises
- Next week we change track.  We give live examples, with less exercises.
    - This is because the exercises are harder to do in big groups
    - You will have time and we encourage you to try exercises yourself after the course
- Week 2 preparation
    - Anyone can come, installation of software isn't needed, since things are designed as demos.
:::

Today was:
- too fast: 
- too slow: 
- right speed: ooooooooooooo
- too advanced:
- too basic:
- right level: oooooooooo
- needed more exercise time: 
- needed less exercise time: 
- I will use what I learned today: ooooooooooooo
- I would recommend today to others: ooooooooo
- I would not recommend today to others: 
- too slow sometimes, too fast other times: 

One good thing about today:
- Collaborative exercises building on the recipe book repo introduced on day one felt very rewarding and enjoyable.
- Todays work was really eye opening for me. Always felt a bit uneasy about colabs, but even with all there people working in the same repo it felt smooth.
- +1 to the previous. This day was really eye opening
- Today was a good way to pull together day 1 and 2. It demonstrated the whole workflow. 
- Today felt really useful and it was a lot of fun to collaborate. I wasn't as motivated to seriously do the exercises of day 1 and 2, but today I was motivated because I could interact with other people.
- Today was really fun and I got a lot of new ideas on how to use Git to facilitate work in the research group
- It was really nice to experiment with collaboration features, as normally in real-life projects I'm little hesitant to make suggestions or submit issue tickets.
- ..
- ..

One thing to improve for next time:
- This is a bit of a chicken and egg problem, but I learn best when I first have an overview and then dive into the details and how-to. Now we started with the details and how they are done, and only today pulled it together into a full workflow. One idea could therefore be to draw an overall workflow diagram (like the clouds you showed today), start with that on day one and then dive into the how-to of the different elements (while refering back to the diagram). +1
- I agree that a good diagram of how github works, would do wonders. I have been trying to draw such a diagram myself during the presentations but I don't think I understand enough of it yet.
- ..
- ..
- ..


Any other feedback?
- This Day 3 was my favorite so far: the exercises quite naturally brought together steps done on GitHub and command line.
- Enjoyed the first week of the workshop: Especially things done on days 1 and 3 felt very practical and I can easily see myself doing similar things in the near future. In comparison, parts of day 2 felt a bit advanced (looking up commit information on command line)
- It's nice to play with a practice repository, often in my own code I am too afraid to experiment. Really nice workshop format, light, not tedious at all, very useful info, thanks a lot! Nice to have a safe place to ask silly questions :) Looking forward for next week! +1
- Won't be able to participate next week due to timetables, but I got a lot out of this week - thank you for all the hard work you put into this workshop. And thanks to all fellow contributors. And CATS!
- Your schematics about forking, cloning, branching etc are very well made :)
- I love the chaotic style of the whole course!! Maybe not perfect for everyone but suited me really well. Thanks!
- Thank you all, well done! o
- Really amazing and so much learned. I have already moved from knowing nothing to knowing so much.
- I wonder if there's a way to postpone introduction of forks until after getting familiar with a more basic workflow of just a single repo. Fewer concepts (branch, clone) to take in at once (compared to forking etc which opens all these questions we've seen on what are the differences), then leave the working with someone else's bigger project for later when more ready to take in additional more advanced concepts. It was a bit much to take it all in for some in our team.
- thnak you ! Great job ! Great material!
- thank you for this day, it was awesome
- Thank you so much for all the efforts and making this great course!
- Thanks a lot!
