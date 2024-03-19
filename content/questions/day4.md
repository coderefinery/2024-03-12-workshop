+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 4"
+++


## Icebreaker

Have you heard the sentence "hmm... works on my computer"? What does this mean in practice? How do you solve this problem?
- Restart the computer and hope it helps :)
    - "Have you tried turning it off and on again"
- Searching on internet for some time and then find out that a restart of the computer or the program is enough.
- Stack Overflow
- For research: It has only run on a few computers: not designed to be portable (yet).
    - What to do: (a) ask author to package for reuse, or (b) spend lots of time and frustration to figure it out.
- Go for a coffee.
- I have no idea what I'm doing.
- Eat chocolate
- Erase completely the code, write again the code exactly as before, and hope this time it works ;)
- Clone their operating system

What do you know now about programming/scripting/software which you wish somebody told you when you started?
- How to organise folders and code
    - "physical geography" of the systems
- Care about how you use your tools, the investment is really worth it.  If you don't, work with someone who does.
- Version control and good informative documentation....
- That practice is the best way to learn - have a task and try to do it
- Do not use exotic frameworks and tools as the cool kids do, follow the KISS principle.
- That it's fine to share "crappy" code, others may have valuable ideas how to improve it
- How to not hard-code everything and why this is important


## Motivation
https://coderefinery.github.io/reproducible-research/motivation/

- Once someone gave the advice "don't get involved in a project someone else started.  always do things small enough you make your own small code from scratch" - may be good advice but how does science really advance then?
    - One important comment here I think is: don't try to reinvent the wheel. While  I understand the issue that caused this comment, you can easily end up re-implementing things that have been solved in a better way before.

- I have found that sometimes it is easier to reuse the idea, and not the legacy code. Sad but so it is :(
   - on the positive side: often rewriting the code does not mean throwing away everything that has been done. the old code can serve as reference implementation and can help us creating tests for the new code. but in this case we should make sure to credit the old code.

- What are your experiences re-running or adjusting a script or a figure you created few months ago?
  - For me not fun but possible, for others I have seen very, very bad.
  - It used to be very bad but these days I document everything because I will forget everything and because everything on my computer will change. So it got better but it is more up-front work.
  - I have definitely struggled with this and felt quite bad about it. I have been working for long with a large piece of code I created myself, I have often struggled to reproduce results after putting it down for months - 1 year. It is helpful to know other struggle with this. I would say the biggest waste of my time as a researcher is probably in the big start up cost of picking something up again. Sometimes I feel that as a researcher I lost my original joy in programming due to the frustration with this.
  - I was pleasantly surprised that for one of my previous projects I had written a better code than I remembered - was able to reproduce the results and get additional figures, but this has not been the case always.
  - With smaller scripts it has been fine, but larger ones that depend on specific input files or API versions or other things that can change, it can take a lot of time to get the script to work again.
  - I got given code that was a few months old (with comments at least), but some of the features of python stopped working and it was poorly written. It was easier to just rewrite
  - horrific and time-consuming, when libraries I have used have changed and I have to track what has changed to get the script running.

- Have you continued working from a previous student's
  script/code/plot/notebook? What were the biggest challenges?
  - Adjust it to new use cases. Reduce hard-coding.
  - Accept that the code is in a different style than I prefer, so not rewriting the whole thing but only adjusting it to what I need
  - Get the code working all together - was struggling with mismatched package versions, as there was no documentation on that.
  - ...
  - ...
  - (share your experience, but constructively)

- Was there much reproducibility problems before ~2010?  (you are right I didn't hear before then, but also I wasn't paying attention then)
  - I would say that reproducibility was a problem also earlier but people cared less and did not see it as problem. Reproducibility was possibly easier to achieve since there were fewer frameworks and dependencies and fewer software layers. A Fortran code which is last touched in 1980 might still work fine. Try to run a Python code that hasn't been touched in 15 years.
  - data sharing was not very common until recently, so potential problems stayed hiding

- I don't hear a lot about preregistration of your study/paper, can this also help for the reproducibility? What are your thoughts about that?
   - I think it can help. Preregistration is not directly about reproducibility, it's more a solution to publication bias (only positive results getting published) and p-hacking. But in a preregistration, the researcher has to describe the method and the journal must judge the paper based on that. So they cannot just give a result without a good description of methodology.
   - I would argue it addresses a different issue, i.e. positive result bias. But if that would get solved, it could encourage better practice since you are less forced to produce "something that works"

- i think we should consider the argument that lack of reproducibility is not as terrible as it seems considering that Science is a strong-link problem, not a weak-link problem. At some point too many resources will be spent in data integrity that outweigh the benefits
    - https://www.experimental-history.com/p/science-is-a-strong-link-problem
    - good point. it is a balance to make. perfect reproducibility might be too much effort. but with already some relatively simple steps we can achieve pretty good reproducibility.
    - agreed!  One of my arguments has been "not everything should be perfect, everything should meet the level it needs".  But if something has no chance of being reproduced, what was the use?
        - Also, lack of reproducibility leads to a trust crisis, which leads to a lot of the problems we start seeing at the moment where people simply claim "I don't agree with this experiment" and it becomes difficult to argue that "this one is solid, while that one isn't" since both might be published in "respectable" journals...
        - I think we all agree that lack of reproducibility is *not good*. But I have concerns about some obsessions particularly about depositing horrible amounts of data that no body will ever use, just for the sake of access. Also, I think that getting quick and dirty results at the beginning of a project is underrated.
            - I think there is a difference between publishing "quick and dirty" results and getting some results quickly at the start of a project for internal purposes. If both quick and dirty and carefully done experiments, get the same type of research paper, there is no way to distinguish between what's a "hint" and what's a solid research for anyone not deeply involved in the procedures.
            - Agreed!


## Organizing your projects
https://coderefinery.github.io/reproducible-research/organizing-projects/

- **Are you using version control for academic papers?**
  - Tried to use GitHub once, failed though because collaborators did not embrace it. Overleaf seems to be a good compromise
  - Partly, using Overleaf but want to switch to VS Code using Git.
  - It is very easy with Overleaf which is integrated with Git
  - When I did, yes
  - Yes, but only for working alone and storing implementations + Overleaf for papers
  - yes. Iterations b/w me and my supervisor happens throughout version control.
  - Only Overleaf, but I really need to start using Git more. My version control is a mess.
  - Yes, but it's hard when working with large amounts of data. Working on computational cosmology, there is no way that people will be able to run my scripts from scratch, since they need data that is proprietary, and not only that, is too large to be shared in version-control tools. Given that, sometimes it seems a bit pointless to me sharing the scripts/code.

- **How do you handle collaborative issues e.g. conflicting changes?**
  - Suggest to comment first before changing text
  - One person is in charge as "editor" and in difficult cases consults with others
  - ...
  - Make sure that you don't have multiple people making huge changes to the same sections.
  - Mostly sending confused and angry emails
  - Co-authors comment their suggestions and the main author implements based on them
  - By disputation.
  - I usually only give collaborators the right to suggest changes but not to directly implement them

- Maybe a dumb question, but what is meant to be in the doc folder? I thought readme files are also documentation?
   - it's good question. in there could be code documentation. tomorrow we will show some solutions for when you need more than READMEs. But READMEs are also documentation and often they are good enough.
   - I interperted it to be "manuscript/papers", but also like above: sometimes big enough projects have own big docs (we'll do this tomorrow!)


## Recording computational steps
https://coderefinery.github.io/reproducible-research/organizing-projects/

**This is a demo, not exercise or type-along.  You can try but we recommend trying it after the course.**

- the example project shown: https://github.com/coderefinery/word-count
    - I think there is a typo in the webpage, where it reads: `python statistics/count.py data/isles.txt > statistics/isles.data`. Should it not be `code/count.py`?
    - Yes, thanks for noticing!  Will push a fix

- What's a script?
  - short code with a series of instructions which you can run and it will then run the series of instructions
    - If data are the ingredients, the script is the instructions for preparing the tools (warm up the oven at 180degrees) and the order of operations to cook the cake

- How widespread is this Snakemake thing? When relying on automated tools, it is sometimes a concern that developer base is not large and ultimately lack of reproducibility will come from the tool, not the code itself.
  - I personally haven't used it *that* much, but have heard about it quite a bit.
  - (but yes, there are other similar things, maybe better for your case - we can only demonstrate one, so check more yourself.)
  - Check what is commonly used in your field
  - In the broader context of data science outside academia, MLOPS is something you want to explore as a field of pipelines and operations useful in machine learning in commercial contexts (Flyte, container orchestration, solutions on cloud providers such as Azure/AWS/GoogleCloud, databricks...)

- I didn't fully understand what snakemake is used for.
   - to describe computational steps in terms of dependencies. see also next question for when it can be useful to express steps as rules and dependencies.
   - When the same process needs to be run many times, and you don't want to write your own tool to monitor that each run went well, some runs need to be run again, etc...

- Could a "main" function be used instead of snakemake that uploads data and runs several scripts? What are the advantages?
   - advantage of snakemake (or workflow tools) is that it does not have to rerun all steps every time. it has the possibility to check whether a step is done. if something changed, it only reruns all the steps that depend on it.

- Sorry, I got confused, what is the main reason for the recording computational step?
    - ing sure you can reproduce the same results, same figure, as you did X months ago.
    - to document the series of steps instead of having to remember them. and even if we remember them, then others get the chance to re-run them.
        - tnx.

- So what will be the outcome of this step? A recorded video? to be checked later by us or other people?
    - Do you mean this lesson or what we are doing in the lesson?
        - No, I mean this lesson. The outcome of recording comp... step.
    - Yes this week we do demos. Participants can run the examples by themselves if they wish to learn how to run these examples.
        - tnx.

- What is the advantage of using snakemake instead of a (python) script?
    - Snakemake is a reusable solution rather than coding yourself something like "if output from book N does not exist, then run for book N"
    - The main thing: what happens if you only want to run some in the loop?  Then you modify the loop to run only some.  And can go deeper and deeper.  The workflow manager can more easily figure out what is new/missing, and do only that part.
        - (I often start with a simple loop, but when it gets too hard to manage partial-running, then Snakemake comes in)
          - yes! the "partial running" is a nice description
    - see also few questions up: "advantage of snakemake (or workflow tools) is that it does not have to rerun all steps every time. it has the possibility to check whether a step is done. if something changed, it only reruns all the steps that depend on it."

- Why do you add {} on file?
   - I think these are placeholders/variables/wildcards.
   - How do you specify the variables?
   - Yeah, just part of Snakemake syntax.  Unfortunately we can give demos but it probably needs more reading later.

- How we should produce this Snakemake for our own project? IS there any template for that?
  - We have this one template, but realistically you need to look at Snakemake tutorials to learn a bit more to use yourself.  (Or another workflow manager)
      - tnx.

- Is Snakemake useful for projects where you are coding as you make progress? I see how it can be great for reproducing an analysis in a different machine, but much of the work is actually making incremental problems, changing inputs, doing small modifications...
    - In some fields you need to process multiple subjects, books, hyperparameters. So snakemake is a tool that helps you keeping track of all the various inputs or simulations you are running. It can be used in a project that is progressing for example when you have a new study participant to process, snakemake knows what to do and will only process the added subject.
    - Also: sometimes when running large computations (e.g. 1000 time the same code with different inputs), some of the runs might fail. Snakemake helps you track what failed and what needs to be rerun, rather than you writing your own solution for that.
    - I believe it can. Since you don't have to remember what to re-run after partial changes but it will look at script and data timestamps and only re-run what has changed and what depends on changes. If the computations are time consuming and multi-step, it can be useful also during code development.

- Can Snakemake also be used for the Projects that are merely some approaches/algorithms, etc And how it is mandatory or recommendable?
  - can you clarify a bit?
      - If I have only some python codes implementing for example an approach or mechanism, still is it highly recommended to have a snakemake?
         - I would consider it if the approach consists of multiple steps, does a sweep over several parameters or input data, and if it takes more than seconds. In other words, it can be useful if you would benefit for being able to easily run only part of your analysis on part of your data, without having to manually keep track of which to re-run. Is this a bit clearer?

- Is the `--cores` flag doing the work of a scheduler in the sense that it makes resources available for the code? Is there one for GPUs as well?
  - On the surface level `--cores` says "use this many cores", it doesn't make them available but assumes they are
  - There are ways for SnakeMake to connect with a cluster and request resources but I don't know these details
  - Snakemake Slurm resource requests: https://snakemake.readthedocs.io/en/v7.20.0/executing/cluster.html

- somehow this reminds me of Airflow, but seems to be easier to set up
  - Yes, there are many different ones.

- I don't understand the code. How come it runs for multiple books? The file is only run once?
    - So evrything in the data folder?
    - Yes, these tools can say "for every input data, make an output." and so on.  So adding data makes output automatically [...]?

- A very nice example, but in this project, all code and data are internal in the project. But what if it relies on external data, e.g. in a database, and other code repositories/packages?
    - There could be a step like "run query and get data".
    - Yeah, I think it could easily enough reference outside questions.

- What if there is a text file that I don't want to run in the folder ? It seems that it detects txt files in general?
    - easy solution could be to rename the files you don't want to run or put them in a different folder.
        - this is for small project, how about for a large one?

- This is actually what I was looking for :) Thanks for the example!
   - wonderful! and this tool is only an example for dozens with the same idea. so this is really about the idea.

- In snakmake you make a rule called "count_words". Do you need this name? Can I call it smth else
   - you decide how it is called. the name "all" is reserved. but names like "count_words" are up to us.

- for data/{book}.data. Does it mean it will run through only all the document that ends with .data in the data folder
    - it will run through all {book} and it collected the books in line 2 of Snakefile. The "statistics/{book}.data" will construct the file name for all books:
      - statistics/isles.data
      - statistics/abyss.data
      - ...
   - so in short: yes. but it collects the books to analyze from line 2 in the Snakefile and later it replaces file names.
   - I see, so it is like to build empty object and set upp the rules for naming the object?
     - yes

- Could snakemake be useful in the case where I have 3 different approaches and want to run a loop with a set of data and compute estatistics for each approach to compare the results? How much strat up cost is there in setting this up in snakemake isntead of as loops?
    - it can be useful if the steps take more than seconds. start-up cost: writing a script similar to https://github.com/coderefinery/word-count/blob/main/Snakefile
    - the approach is: instead of explicit steps and loops, express it as dependencies and use wild cards to collect data.
        - Thank you. I feel like there is a lot of potential for this to solve some of the issues I have been facing, althogh I don't yet fully understand how it works. The concept of wildcard is a bit foreign.

- I could change the variable name "book" and "file" to something else, right
    - yes. goal is to make it meaningful for humans. for the computer, it can be anything, it only needs to be consistent.

- Can the variables communicate between rules?
    - I am unsure.
    - in general you would not need to, like in this example we are using wildcards rather than variables, but afaik the variables are global for the workflow file


## Recording dependencies
https://coderefinery.github.io/reproducible-research/dependencies/

- Are you using any dependency and/or environment management tool in your work?
    - No: oo
        - why not?
            - I'm working alone most of the time, I didn't take the time to look into it.
            - ..
    - Yes: oooooooooconda list --export > package-list.txt
        - which?
            - virtual environments: ooooooo
            - conda ooo
            - containers
            - ...

- If I build my own package, in R, How do you add github project without version numbers in the description file? And How do I specify a specific branch?
   - there is an example for this in the R tab just below https://coderefinery.github.io/reproducible-research/dependencies/#demo - if this is what you meant
   - You can use `@branch-name` or even without the `@` for "always the latest" (if you are willing to handle it breaking if that project changes...)

- The example have version number. If the repository I want to use do no have version number?
    - if it is a Git repo, then you can refer to versions by branch (but they can move over time) or to commit hashes.
    - Can you give an example how to write this? I don't understand how the desrciption file can automatically know which are CRAN or repository packages

- When working with Matlab, and if code refers to an older version, would user of code really need to isntall older version of Matlab to run it? What would be a better? Installing Matlab takes so long.
   - only if the code does not run anymore on latest Matlab (not sure how likely that would be). Sometimes it can be less work to change the code than to get an older version installed.
   - You can containerize older versions of Matlab. In some cases this is a necessity (e.g. for tools who use graphical interfaces built with Matlab). I don't think there are ready made solutions for this, if you are at Aalto, we have such solution in our cluster.

https://coderefinery.github.io/reproducible-research/dependencies/#demo
- which adv/disadvantages do each of these have??
    - A:
    - B:
    - C:
        - There might be problems when dependencies are updated, because versions are not defined
        -
    - D:
        - If Github stops, can't be run anymore.  Or those projects get blocked on github
    - E:

- The difference between E and D also depends on the project "anotherproject", if the authors made tags, etc, right?
    - partially. The "sometag" entry in D would only be possible, if they had tagged, but you can always refer to a specific commit (which might come in very useful with a fast developing project, where you don't want to update your code when they introduce breaking changes, and you oonly use some 'basic' functionality you are certain is bug-free)
        - Ups I thought you were comparing C and D
    - and not only made tags but it assumes that they are sharing the project as a package on service like PyPI or CondaForge or similar.

- How do you decide whether to use conda (Mambaforge) and or Python venv?
  - Some always use conda, some use venv if they want.  I don't know if I can say for sure which to always use.  Conda is more "self-contained" and likely to work everywhere (but I try venv first...)
  - I use Python venv if it is a "pure" Python project. I find venvs a bit simpler. But if I cannot, I move on to Conda.
  - When installing conda, one has to accept propetary licence.
  - I use pyenv for Python stuff and renv for R

- I am confused. You mention Git clone for dependencies of other packages, but why not conda (or venv) and install? Or do you use .yml files to install?
   - the yml files describe the environment and the environment will be installed based on that description. But maybe I misunderstood the question. In this case can you please rephrase?
   - Dependencies can be written in yml files so that conda understands it when installing the virtual environment. Inside the yml file there can be some "git clone" because some code is experimental and is not released in one of the official channels (i.e. you are not able to "conda install" it or "pip install" it with python). While you can do the installation interactively within conda, having it scripted is more useful because 1) you only need to keep the yml file (no need to write down what you installed manually) 2) when doing the installation from yml file, conda tries to resolve the dependencies between the various packages at once. This can avoid the situation that a newly installed library inside the active conda environment will be incompatible with other existing ones.

- Can you give an example how to write repository packages in the description file in R? I don't understand how the description file can automatically know which are CRAN or repository packages
    - `remotes::install_github` will install the dependency from GitHub and not from CRAN
        - You mean I write `remotes::install_github`  in my description file?
           - Ah now I got the question. I admit that I don't know yet how to do that correctly in the description file (I am an R beginner).
           - Yeah, unfortunately here we focus on the installing part.  But now you know what to search to find this later!
             - yes. Goal of this session is not to remember how but to start thinking about dependencies and how they might still work or not over the lifetime of my project.
             - we should do a course on packaging ...

- In the demo you used source activate but the documentation says conda activate?
    - looking ...
    - "conda activate" is new, "source activate" is older, but on some (ours at least) HPC cluster we recommend "source activate" because of the way we discribute conda with modules.
    - ... so probably it's a mistake in updating the text.

- What if I use conda/mamba and some other user of the code will use something else, e.g. venv/pipenv? Or can I use conda independent of what other are using?
    - for many popular libraries, if they are Python libraries you can use the one or the other (but venv/pipenv is for Python projects)
    - Conda for example can also understand and use requirements.txt files (used by pip, internally it will then use pip to install the packages into a conda environment)

- Mamba sounds wonderful to avoid the hyper-long waiting times from conda resolving environments. However, a brief look at installation instructions make it seem like you need to configure your system around it a bit: start with miniconda, nothing in your base...
    - you can also look at micromamba. super minimal and fast (this is what I use). Let's see if I find out how I installed it ...
        - Thanks! `brew install micromamba`?
             - for example. I think I installed it from a script (I am on Linux).
        - `"${SHELL}" <(curl -L micro.mamba.pm/install.sh)`
    - It's actually good to not have anything in your base, so you are forced to make a new environment for every project (cons: expensive with disk space).

- In order to get reproducible results, all code should have the same version, but what about data? Will you discuss data version control, such as DVC? Previously I have been using Python Pickle files, which are huge in size. Will you discuss this? Should these be under Git despite the size or better to use data version control?
    - we will talk about it a bit after the longer break today. but excellent point that we also need to keep track of data as it evolves. if the data is big, traditional Git repos are not a good fit but DVC can be a solution or git-annex (open source) or Git LFS (proprietary).
    - Parquet file format is useful for storing largeish datasets, toolwise it is well-supported

- can you simplify things, it is very advanced!
    - thank you for feedback. this is an advanced section but let us focus on why we are doing and what we do but not so much about the how. in short: we are installing a different operating system into a file. we will be able to run a different OS inside our own OS.
  - can you discuss it more
      - Did this section help: https://coderefinery.github.io/reproducible-research/where-to-go/ ? Or do you have any more specific follow up questions?

– Would you recommend saving virtual environment files (f.ex. pip packages) in the same directory as the project or somewhere else? What are (dis-)advantages of both?
   - What I do is to have the requirements.txt and environment.yml as part of the Git repository. I also create the environment in the same place where my project is. I like to have the environment close to my project and not somewhere else on my hard-drive but that is personal preference. But strong recommendation to create a separate environment for separate projects.


## Recording environments
https://coderefinery.github.io/reproducible-research/environments/

- Have you heard about or been in contact with containers (docker, singularity, podman) in your work? How did you come across them?
    - No: ooooooooo
    - Yes: oooooooo
    - Yes, but have never ever been able to make them work :-(
    - Nope.
        - Thanks to our IT support at the university, they helped us to make a Docker container for our project.
        - docker, someone set it up for JupyterHub servers and I learned by seeing and modifying.
        - I have seen dockerfiles before and was wondering what kind of dark magic it is

- What is the motivation and the main reason to use a container?
    - to document not only code dependcies but the entire operating system. think of it as "operating system inside a file". when do you need it? if it is hard to install dependencies on your own operating system or if you want to have a common basis and make sure that all your collaborators are using precisely the same OS (as documented in the container definition)
        - thanks.

- Can you give some example of good software development practices that can be discouraged by the use of containers?
    - using a container when developing code can have pros and cons. one risk is that when always using my container which always works, I might not notice that my code became harder to install outside of a container.

- Containers remind me a bit of virtualizing a system in your machine. This used to be a problem for being able to access files in your drive other than in the part of your filesystem where you are locating your virtual machine. Is it the same case here?
  - Yes, same idea!  But at a different technical level, you aren't vitualizing the hardware or core operating system kernel.
      - Could you please address the second part of the question?
          - (reading ...)
              - :-)
                - with container technology like singularity/apptainer it is not a problem anymore to access files and folders "outside" the container. you might need to "bind" a directory (make it visible to the container).
                    - Great!

- What if I develop on MacOS but I know it will run later on Linux server? Should I instead develop from scratch on Linux using container remotely? Or can I be sure that if I use identical packages (same versions) on Mac it will work on Linux?
   - same packages, same versions -> it might just work also on Linux
   - but if you want to make sure it works, you can use locally a Linux container (no need to run it remotely) and then everybody else can then also use this container and then it should run everywhere where that container technology is supported.
   - What langague do you use? Python
   - But your question is very good: it's some of the main decisions to make to balance portability and ease of development.  Each project will be different, so learn more and see what works for you.
   - Thank you for the answers.

- Related to the above question. Have any of you tried VS Code Remote Development? I would love to see a tutorial on this. Great, thanks!
    - Yes, and we will have a workshop including this coming in April (Tuesdays Tools and Techniques for HPC)

- So, if I do a lot of development on my own Linux computer (including conda environments), can I create a docker of the current state of my computer (including the conda environments) to run on a super computer?
  - The containers aren't usually "take my existing computer" (even though that's what the meme says): it's basically scripting a *new* computer setup in the container - that is reproducible.  And then moving that.
      - OK, so I would try to create a container with only the "minimum" amount of software to run whatever I need?
      - Exactly.
         - the approach that I use when developing using a container: instead of installing into my system and then figuring out what I installed and getting it into the container, I install into the container and use it from there. Then I have both installed it and documented it.
             - Great, thank you!

- What about their size (in Go eg)?
  - Size of the containers?  Since they usually only contain the minimum for the software, they can be much smaller than you expect.
     - often 100 MB to 1 GB or few GB
  - Bigger problem: for example they have NVidia drivers in them, which can get multiple GB, then many images, so all libs are duplicated.  But space is cheap and debugging software is hard, so still worth it usually.
      - okay thanks.

- The main difference with a virtual env is that you dont have a graphical interface?
    - A virtual environment usually only has Python packages (or similar for a different language). A container has everything an operating system needs to run. So a lot more system libraries and packages.
        - I meant virtual machine sorry!
    - OK. The graphical interface is a big difference, although you can run graphical software from a container.
    - Creating containers is often scripted (like we did, with a text file). For a virtual machine you would usually need to set things up manually.

- Is there any modular contatiner not to have to work merely on the command prompt?
   - can you give an example of how you would use it or interact with it?
       - I would use the mouse appart from writing the command.
       - Docker Desktop is an example of graphical container management tool https://docs.docker.com/desktop/
       - We often show examples that are command-line based because many supercomputers do not allow (or make it difficult) to run graphical interfaces.
           - thanks


- This is slightly outside of this. But I am struggling to find a way to structure my files and folders on my computer. As an example, I can have folders for e.g. meetings, meeting notes, presentations (mine and others), conferences, research papers, projects, code etc. But I could also organise so that everything (or most anyway) is a project and within that folder add related folders for the above. But then everything will end up in one folder, e.g projects. Any suggestions or “template” for this? Or perhaps use sym links for a more flat folder structure? You showed a project structure but I am looking for a structure for all folders and files on my computer so that it is "easy" to find everything.
    - I still think that one folder per project is the best solution. Project is a flexible term that can work also for things that will not end up in a scientific publication
    - comment from a fellow student: I use year-based folder system, eg. in the Documents-directory of my computer, I have folders per year and in those year-based folders, I have folders for projects. If the project continues over one year, I just copy everything to the new year-based folder and continue from that. Eg. the folder structure is like ~/Documents/2024/projectname
    - thanks.


## Feedback from part 1

This lesson was:
- too fast: ooo
- too slow:
- right speed: oooooooooo
- too advanced: o
- too basic:
- right level: o
- I will use what I learned today: oooooo
- I would recommend today to others: oooooooo
- I would not recommend today to others:
- too slow sometimes, too fast other times:

*Consider for questions below: Did you like this format where we did only demos with less exercises?*

One good thing about this lesson:
- I am sure this will be useful to me. Thank you.
- Learning about Snakemake. oo
- it's a good way to get started with the tools I'm interested in
- Became aware of various aspects to take into consideration when "trying" to work in a systematic and organized way ;-)

One thing to improve for next time:
- I missed the exercise sessions, the course is much more useful with them o
- I struggled a little bit following. Was a new concept for me. Perhaps I could have benefited from the very nice materials. Thank you!
- The exercises enforces to focus - hence that works better for me

Any other feedback?
- Only demos were sufficient.
- No time to follow the whole day or even one session some days, excellent to have videos to pause and play - thanks!
- ..


## Social coding and open software
https://coderefinery.github.io/social-coding/


### Question 1: Why would I want to share my scripts/code/data?

**Choose many**. Vote by adding an `o` character:

- A: Easier to find and reproduce (scientific reproducibility)
  - votes:ooooooooooooooooooooooo
- B: More trustworthy: others can verify correctness and find and report bugs
  - votes:ooooooooooooo
- C: Enables others to build on top of your code
     (derivative work, provided the license allows it)
  - votes:oooooooooooo
- D: Others can submit features/improvements
  - votes:oooooooooo
- E: Others can help fixing bugs
  - votes:oooooooooooo
- F: Many tools and apps are free for open source, so no financial cost for this
     (GitHub, GitLab, Appveyor, Read the Docs)
  - votes:oooooo
- G: Good for your CV: you can show what you have built
  - votes:ooooooooooooo
- H: Discourages competitors. If others can't build on your work,
     they will make competing work
  - votes:
- I: When publicly shared, usually we time-stamp or set a version,
     so it is easier to refer to a specific version
  - votes:oooooooo
- J: You can reuse your own code later after change of job or affiliation
  - votes:oooooooooooo
- K: It encourages me to code properly from the start
  - votes:oooooooooooooooo


### Question 2: The most concerning thing for me, If I share my software now

**Choose one**. Vote by adding an `o` character:

- A: It will be scooped (stolen) by someone else
  - votes: ooooooo
- B: It will expose my "ugly code"
  - votes:ooooooooooooooo
- C: Others may find bugs and mistakes. What if the algorithm is wrong?
  - votes:oooooo
- D: I will get too many questions, I do not have time for that
  - votes:ooooooooo
- E: Losing control over the direction of the project
  - votes:ooo
- F: Low quality copies will appear
  - votes:oo
- G: I won't be able to sell this later. Someone else will make money from it
  - votes:ooo
- H: It is too early, I am just prototyping, I will write version to distribute later
  - votes:oooooooo
- I: Worried about licensing and legal matters, as they are very complicated
  - votes:oooooo


### Question 3: Why is software often treated differently from papers?

Free-form answers:
- They are very different from papers. So it is normal that they are treated differently. People do not go to code so much for learning about new results. You only do it for reproducing stuff. What is the right analogy? An instrument to make measurements, maybe?
- The previous generation treated them differently
- Because of publishing right and Plagiarism
- ...
- ...
- ...


### Question 4: When you find a repository with code/library you would like to reuse, what are the things you look at to decide whether you use it?

Free-form answers:
- is there many contributors? oo
- Licence ooo
- is the project still alive oo
- Dependencies ooo
- Are there tons of open issues?  Are there no issues?  Are issues even available somewhere?
- How issues are resolved and how project handles contributions o
- if it is useful to my work o
- License, Documentation, Community Support, Dependencies

- I have noticed in different lesson of coderefinery the mention of issues and wether or not repository is still active. Also learning from watchign other repositories. Most reserach software I have found that I would like to reuse has a single commit. It is share as a single version on github. Is this somwhat uncommon?
  - I guess it's common enough I'm not surprised.  It tells me "either they make the repo after it's done" or "they re-did it to lose the history".  It makes me think "this repository is just to share it, I don't expect interaction here." (fair enough...)

- What does exactly fall under 'software'? Is that also python codes for doing analyses to get to the results of a paper?
    - yes!  that's an important part, and probably most projects.

- How far to go not for sharing code but accompanying data? In my community there is a current trend of wanting as much data being deposited as possible. Understandable given relevance of ML for training, but is it not too much at some point? So how far to go? My idea is typically to share as much as is needed to reproduce results, but not more.
  - yes!  data is just as important if not more so.
      - I think that also depends on the type of data, in social sciences you often can't share data because of sensitivity and privacy
      - Other perspective: I think that in social sciences, data sharing is possible but it cannot be done as an afterthought, but preplanned in research design phase.

- Can you give examples of repositories you have worked on as a reseracher and as a research software engineer. I ask because I have been working for years as researcher in largely the same code, making improvements and building it. I wonder if this is too large project or I am just really inefficient.
  - Tomorrow we have some links form our pasts... maybe someone can give some now.  Back when I was a resercher my work was much worse than now!
  - Hopefully I manage to raise this on stream. Great question!

- What was the biggst thing that raised your concience or led you to adopt better practices? Was it working as a developer? Or in a specific project? Or something else?
   - changing affiliations
   - I'd say for me seeing good practices in others (and feeling that my good practices help someone else)

- How does citing work when you use codes from several other projects or from for example stack overflow?
  - Oh, we get there!  At least the copyright/license side.  You can cite multiple things as sources of course.

- During this workshop I have been thinking it might be helpful for me to create a sort of code template with the whole infrastructure around my main approaches that I could reuse. My work mostly consists on extracting information from images. The mess in my repositories is usually not mostly in the approach itself but in the surrounding code that uploads data, runs tests and computer statistics on results, etc. Can you comment on this?
  - Oh yes!  At first we often start with "figuring it out", but by now I have some templates of all the common things I need, and simply copy each time I need it again.
  - I would spend lots of time seeing best practices in other repos and building on that.  And making a good template and re-using.
      - This might be part of the issue that I have not seen too many examples. Hopefully now I will more actively search for this and get some examples from here as well :)


## Software licensing
https://coderefinery.github.io/social-coding/software-licensing/

- Does AI-fuelled coding not bring to the table some questions about whether one should be able to own rights on software?
  - yes, discussed by voice.

- Do you have specific advice on default licenses that are in general a good idea for scientific projects? It is sometimes difficult to choose from the "menu" of available licenses.
  - We usually say "MIT or GPL".  MIT if you are happy with any kind of use, even commercial that gets closed-source (if you become that famous then you've made it anyway, right?)  Or GPL if you want maximum reuse (commercial reuse would be OK but the output has to also be open-source, so they can't really sell "your code" but some extra service).

- Instead of sharing the code, with a license, what about just sharing the output from the code, e.g using a REST service? An example can be time series requested by another scientist, e.g. if the code is in Python but the user use Matlab.
  - That works sometimes, and might be a nice service anyway (if you can host that many resources)
  - But then, no one can really understand for sure what's going on, build on it, or whatever - this would usually be considered un-scientific.  Unless they re-implement it and then everyone would use that other implementation, and what did you gain?

- Can we combine licenses, for exemple: the core code with GPL-3 license, and plugins code with LGPL license ? Or the other way around ?
    - yes. in this case both ways. in the situation where you take a component and mix it with your code so that the combined product becomes derivative work, LGPL is less restrictive than GPL.


### Question 5: Which of these are derivative works?

**Choose many**. Vote by adding an `o` character:

- A. Download some code from a website and add on to it
  - votes: oooooooooo
- B. Download some code and use one of the functions in your code
  - votes: ooooooooo
- C. Changing code you got from somewhere
  - votes: ooooooooo
- D. Extending code you got from somewhere
  - votes: oooooooooo
- E. Completely rewriting code you got from somewhere
  - votes: ooo
- F. Rewriting code to a different programming language
  - votes: ?oooo
- G. Linking to libraries (static or dynamic), plug-ins, and drivers
  - votes:
- H. Clean room design (somebody explains you the code but you have never seen it)
  - votes: oo
- I. You read a paper, understand algorithm, write own code
  - votes: ooooooo

end poll

- Generally what is the most used license for code relating to scientific publications? (The questions refers to code, not publication text :) )
  - I don't have stats (there is probably some survey on it), but my guess is same as most software: MIT or GPL depending on needs. oo
      - I think for papers you may want to be a bit more conservative than with code. Specifically: `ND: No derivatives or adaptations of your work are permitted.`
          - a license doesn't mean you can impersonate the person, but reuse. for example, someone quoting you in presentations, re-showing your figures, etc.  People can't change your words and call it yours, that's just fraud and independent of licenses. (that's why publishers offer CC-BY as the main licesnse)
      - For papers, the publisher often decides, but also, the text from there isn't reused, the ideas are (and ideas can be re-implemented without being a derivative work)

- Difference between MIT and Creative Comons licenses?
  - MIT is more designed for code, Creative Commons for non-code things.  CC has different licenses with different levels of permissiveness, CC-BY is sort of the same level as MIT

- What if someone uses your code without permission, how can you show that they used it?
   - we will hopefully discuss it. on my list ...
     - another motivation to share your code. then you can at least prove that yours existed earlier (git history)
   - Very good point.  In the end, it comes down to "do you want to go to court" or "can you scare them enough to not".  You can find plenty of examples of license violations, and you've got to find+prove
   - It makes me think of the random software program "busybox" which was known for trying to enforce: https://en.wikipedia.org/wiki/BusyBox#GPL_lawsuits
   - More practical: you might make an academic misconduct complaint about not following licenses.

- Could you please explain a bit about the difference between licence and copyright? I get confused.
  - Copyright is the legal idea that: an author has the right to prevent others from coping.
  - License is: a declaration from an author that you are allowed to do something (usually the reusing and sharing by default prohibited by copyright)

- I have been working with Matlab due to constraints related to specific project and colleagues. There was strong preference for background libraries to be a product (Matlab) rather based on open source libraries like opencv. My question is, when you are stuck working in Matlab due to project requirements, how can you be more open and collaborative? Any advice for someone that hates working with Matlab and is somewhat stuck with it?
  - I guess the best you can do is share your original creations (even if it can't be reused without Matlab+other proprietary libraries).  At least someone can see that code and has a chance of understanding even if they don't have access to Matlab and those libs?
  - (I'm following the course, not a teacher) Would it help to test compatibility in Octave?

- Have you ever had such workflow where you reserach in Pyhton, and after the final approach is somewhat stable you re-write in, let's say in CPP, because that's one of the formats your colleagues would accept as input?
   - yes. often. I would prototype in a language where I can move quickly. Later maybe rewrite it to something else if needed.



## Software citation
https://coderefinery.github.io/social-coding/software-citation/

- I see the CITATION.cff file has the specific version 2.0.4. Would you recommend citing the specific version?  For reproducibility I see the point of specifying the exact version, however this will lead to users citing a variety of different versions, each accummulating only few citations. It may be preferable to have one version or the "general software" to accummulate many citations?

- Here's a link to Zenodo's explanation of DOI versioning: https://zenodo.org/help/versioning.   It seems they don't use a sub-DOI but a new DOI for each new version for reasons explained on the link.  I can't quite see if it is easily possible to gather the sum of all citations of individual version DOIs. Using what they call the "Concept DOI" seems more straightforward, though it does not then point to the specific version used.


## News for day 4

- We covered the things mentioned in the schedule
- It was all demo-based, no exercises
- There are many good questions and answered in the Notes, available on the website.  Check it out!
- There is nothing to prepare for days 5-6 since it is also demo
    - But if you do, you will be able to try yourself after the course.  There is plenty to actually try.
- Remember, the "why" is more important than the "how" - we cover the "why" and link to the "how".


## Feedback from part 2

Today was:
- too fast:
- too slow:
- right speed: ooooo
- too advanced: oooooo
- too basic: o
- right level: oooo
- needed more exercise time:
- needed less exercise time:
- I will use what I learned today: ooo
- I would recommend today to others: ooo
- I would not recommend today to others: ·
- too slow sometimes, too fast other times:

One good thing about today:
- Very good and useful. Nice teaching format.
- I am excited about using SnakeMake in the future.
- Very informative, but will take some time to digest.
- I like that all the time is now really used to learn us information, instead of taking 10 minutes to make an exercise

One thing to improve for next time:
- I would have liked more time for discussion in the collaborative document
- Looking forward to Thursday's topics :)
- I am hoping the "bring your own code" sessions are long enough. Many things I would like to ask :)
- Bring radovan also on Thursday!
-

Any other feedback?
- No time to stay in Live - great to have video and pause + play - thanks!
