+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 5"
+++


## Icebreaker

- How would you explain your current job to someone in the year 1700? (if you don't know, write what you do and we'll try to figure out!)
   - We have really big complicated machines.  I help people use them. (hpc/research software engineer) o
   - Reading letters and writing letters. (email and chat ...)
   - Organizing assemblies of people to discuss.
   - Mathematically rephrasing what people had already inventend in 1700.
   - Keeping a team of skilled craftsmen (and craftswomen) engaged and collaborate on building an advanced tool
   - I try to figure out how to do new things (research scientist)
   - We will be writing the scripts not on the stone using hammer and chisel but on someting else which takes less efforts and easy to store for longer time.

- What's the best documented project you've seen?
   - I think pytorch's docs are quite good, even though it's changing rapidly.
   - Scikit-learn: o
   - Big things like Python/Numpy/SciPy.  Pandas has always been a bit hard.
   - Flutter
   - core Tidyverse packages for R: o
   - Might be one of the problems that I haven't read too much documentation
   - obviously the well known libraries like numpy, pandas, sci-kit learn. But also, the open sorce codes in geospatial projects like qgis is also among the well documented projects.

- Do you prefer reading short social media posts or long blogs? How about short code snippets or long source codes?
    - short social media posts: ooooo
    - long blogs: oooooooo
    - short code snippets: ooooooo
    - long source code: oooo


## Day 5 intro
https://github.com/coderefinery/workshop-intro/blob/master/daily_intro.md#welcome-to-day-5-of-the-coderefinery-workshop


## Documentation: Motivation
https://coderefinery.github.io/documentation/wishlist/

- Is project documentation important? Why?
    - If the future is important, yes
    - Very much. Even for myself I feel some documentation would be good.
    - Yes. For quick and right understanding on what is the purpose of the written code and relevant details.

- How would you describe a useful documentation?
    - Someone not being involved in the project can understand/modify/expand it without the help of the creator. o
    - Clear, engaging, not too long.
    - Nice examples that help me to get started. Big plus if the examples are not "foo/bar" examples. Big turn-off if they are foo/bar examples. o
    - For quick questions, quick to find the answer.  For detailed questions, possible to find an answer.
    - Can be contributed to as easy as the code can be contributed to
    - accessible, easy format
    - reusable like one would reuse code (not some separate format)
    - Easy to navigate / search for modules
    - Instructions about prerequisite
    - "Boring" in arrangement, so you know where to look for common things.  "installation", "quickstart", "howto" "reference",
    - documentation should be up to date, outdated documentation is more harmful than helpful
    - the one which describe the purpose of the code, important steps followed (i.e. algorithm), all the libraries used to run the code, possible outcomes the script will provide with effective examples which will show how to call the defined function, catch error details if the inputs are required from user or automation process.

- How can you motivate your colleagues to contribute to the documentation?
    - By money.
        - (jokingly: you mean, by it being their job?  but correct, it's their job to get citations, not write docs)
    - By explaining that a good documentation makes it a lot more likely that their code is used, and therefore their work cited. +1
    - Raising awareness for need and having resources/time
    - By telling them: You will not be able to understand your code after one year.
    - With academic credit that not only looks at number of citations and rank of journal.
    - Take this course
    - Have a template that is easy to understand and use for everyone how to document.
    - that constructive feedbacks for a good documentation will help to make the existing code more useable, reliable and will provide if there is necessity for further updations or completely new code in future.

- is (at least OK) documentation needed for the project to become big?
    - I'd say yes, otherwise it's only for a very few experts, which than means it won't become "big" in the wider field
    - How to become big (famous) without having an advertise (documentation) to familirize people with.
    - Yes, very essential.


### Checklist/Wishlist: What should good documentation contain? What should it be like?
https://coderefinery.github.io/documentation/wishlist/#creating-a-checklist

What should good documentation contain?
- Examples ooo
- Clear/Not repetetive
- What is the purpose of the thing.
- How to install o
- FAQ
- Structure of code
- Long API reference (to the degree it makes sense)
- The code should also explain itself
- What is that, how to use, how to modify, why is that and what is the area that can be modified.
- Link to code
- Where to report problems
- Do the authors want problems to be reported (is this actively maintained or archive?)
- How to contribute to the project

- What should a good docstring contain in Python?
    - Similar for other programming languages
    - We'll come to this in a minute
    - How I look at it (not sure it is useful explanation): "what information would I like to see about the function/module from invoking help, without even looking at the function: what it expects, what it returns, how it can fail"
    - variable types!
        - can you please expand this point?
                - ah types of variables :-) I got confused by "variable types" and understood it as types that are changing
                    - Yes, It is confusing when there is no information about types of variables
                        - indeed. type information/annotation helps a lot. especially for languages like Python.



## Popular tools and solutions
https://coderefinery.github.io/documentation/tools/

- Do you use any kind of diagrams in your documentations? For example showing different functions and data flow between them? What simple tools would there be for this?
  - I don't but would be very interested in easy ways to make simple diagrams like that.  Could be very powerful.
  - this can be interesting: https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/
     - this works not only in github; have seen it also in other places
     - I see a Sphinx extension for this too... would you recommend mermaid as the best format to look at?
        - it's the one I know for diagramms for markdown-y documentation. maybe there are others. but this is the one I would use for my own project.


## In Code Documentation
https://coderefinery.github.io/documentation/in-code-documentation/#in-code-documentation


- What Comment is better:
    - A: o
    - B: oooooooo

- Is comment B wrong on purpose?
    - no, not on purpose. this is a bug/typo in the lesson. comment B was meant to be more useful. It was not meant to be subtly confusing.
    - https://github.com/coderefinery/documentation/issues/288


## README files
https://coderefinery.github.io/documentation/writing-readme-files/

- What is the difference between markdown and Rmarkdown. Is there only one markdown language? For example, does HAckMD and HedgeDoc use the same markdown language?
    - unfortunately there is not the one markdown language standard. there are a number of Markdown flavors with own features which then might work on some platform and not on others.
       - correcting myself: maybe "CommonMark" is the standard? https://en.wikipedia.org/wiki/Markdown

- Could you share the link of the github repositioy shown?
    - Do you mean numpy or the one where we played around with the README?
      - I think so, please share that one too.
        - it was a temporary repository. the additions to it are summarized here:  https://coderefinery.github.io/documentation/writing-readme-files/#exercise-have-fun-testing-some-readme-features
    - numpy: https://github.com/numpy/numpy
    - Could you let me know again how to view the code of the readme file on this page?
        - first click on the file itself: https://github.com/numpy/numpy/blob/main/README.md
        - then click on "Code" (top left) -> https://github.com/numpy/numpy/blob/main/README.md?plain=1
        - Note: You cannot edit this file, except if you create a fork, not even for preview changes.


- Is there any documentation to write the markdown? similar to the html documentation?yes write the syntax...
  - do you mean, what is the syntax of markdown?
  - e.g. https://www.markdownguide.org/extended-syntax/
  - Markdown isn't standardized, basics are the same but at the level of Sphinx it is different.  Myst-parser syntax: https://myst-parser.readthedocs.io/en/latest/syntax/reference.html


## Sphinx and Markdown
https://coderefinery.github.io/documentation/sphinx/#sphinx-and-markdown

*Like yesterday, this is a demo - watch and try later.  Ask questions!*

- We can do the whole thing in myst-markdown now.  We'll update once we can.
   - example for how to do the index page in myst-markdown (the index page of the current lesson): https://github.com/coderefinery/documentation/blob/main/content/index.md?plain=1

- No we can not see the lower part of your screen
   - thanks for this feedback!

- IS Sphinx similar to smth like quarto website?. Is there a yml file that rules the overall struture, or that is the index file in this case?
     - yes, I think similar idea like quarto. In the sphinx case, configuration is in conf.py and the document tree structure is in index.md or index.rst. But overall similar to Quarto: it's something that generates HTML (or PDF) from Markdown files (or RST files).
     - Could you expalin a bit what configuration means and what does conf.py in this specifc case?
        - configuration could be: theme, extensions, versioning
        - example for a conf.py file: https://github.com/coderefinery/documentation/blob/main/content/conf.py
          - this is not the conf.py file for the project now on stream that is being built up but for the current lesson, but it is similar. When you run `sphinx-quickstart`, it will generate a conf.py for you which you later can customize.
          - If use css/Sass rules ,are they specified here
               - yes, I forgot about CSS. They would be specified there.


- Is sphinx more suitable for python.
    - No, sphinx is pretty flexible and not bound to one language
    - it can be used for any language in principle. however: 1) for python you can relatively easily create documentation from docstrings so it is extra good for Python, and 2) other languages might have similar tools that might have some extra support for their language. to be more specific: I use sphinx for all kinds of languages but for R, I would use something based on Rmd. Some languages have their standard way of documenting a project. But for those that don't, I would go for Sphinx. For Python projects, Sphinx is the most popular solution.

- Could you exapalin abit what is the relationship between index.rst, example.py and confg.py
     - index.rst: is the main entry when visiting the website, contains the table of contents. all other sections are listed here.
     - example.py: some example file the instructors showed how to include into the documentation as code example.
     - conf.py: contains configuration like theme, colors, extensions, version

- Is there a interface for sphinx? For example, in quarto You can see the "source" for code and "Visual" directly for the  output
    - in sphinx, I use the local preview to see how it will look. And I use buttons like the one on top right here to link to sources: https://coderefinery.github.io/documentation/gh_workflow/
    - I would use sphinx-autobuild to automatically regenerate, and either a separate web browser to view updates on each save, or two panes in VS Code.
    - I'm not using it but here is something like it : https://github.com/audreyfeldroy/sphinx-gui

- Could you share the cr2024.... repository link here?
  - https://github.com/rantahar/cr2024-documentation-example



## Deploying Sphinx documentation to GitHub Pages
https://coderefinery.github.io/documentation/gh_workflow/#deploying-sphinx-documentation-to-github-pages

- +1 "always find a template and change paths", same! +1

- documentation.yml is only needed if we want to depoly the website ? Do we need it if we only want the wesite local on own computer
    - No, this is if you want to have the compiled documentation available on github, so that users can easily access it.
    - We'll learn moer about "Github Actions tomorrow" and hopefully becomes a bit more clear then.

- The rendered page on Github Pages: https://rantahar.github.io/cr2024-documentation-example/

- Can this be used for any type of site?
    - yes. coderefinery.org is built and served this way. in this case not using the sphinx part but using the github actions workflow.
    - I mean, things that aren't sphinx.  I guess anything works in theory?
      - yes. anything that generates a "static" HTML will work (pages that don't need a log-in and don't need anything else than an HTML server)

- the index.rst seem to do to things ?(1) set the structure of the pages (2) As an entry page itself?
    - It mainly defines the Table of contents. The structure of the page is defined in the conf.py (more precisely in the theme)
    - Yes, it does both.  conf.py defines root_doc, and looks at root_doc for "toctree" entries, each of those for more, and so on.
    - Thanks! I was a bit confused because Quarto separtes it with yml file only do (1) and an index.qmd do (2)

- Can the documentation.yml be automatically generated in somw way? Is there a general template for it?
    - more general answer: a starting point to get starting templates for the YML "recipes" can be this place: https://github.com/marketplace?type=actions
    - particularly for sphinx, maybe our example is a good starting point
    - the marketplace can work to automatically add a template.  I always "automatically" do it by copying from another of my projects and adding.

Technical question, what tool are you using to stream and display your videos of the instructors and move and scale them around the screen? It works really nicely
- OBS-studio (standard open-source livestreaming software).  Some interesting links:
    - https://coderefinery.github.io/manuals/coderefinery-mooc/
    - https://coderefinery.github.io/manuals/obs/
    - If you want to learn how to, get in touch: https://coderefinery.org/blog/2024/03/17/streaming-training-workshop/
- Brilliant, thank you very much!  I will take a look!

General question considering course certificates: should be submit our assignments in English or is Finnish fine too?
- I'm not one of the grading ones but Finnish is almost certaintly OK.


## Jupyter notebooks
https://coderefinery.github.io/jupyter/

> Note: working with Jupyter in VSCode: https://code.visualstudio.com/docs/datascience/jupyter-notebooks


## Jupyter: Motivation
https://coderefinery.github.io/jupyter/motivation/

- Can share the repository link?
    - https://coderefinery.github.io/jupyter/motivation/#case-examples
    - https://github.com/gwosc-tutorial/quickview

- How does this work with privacy/sensitive data?
    - (great question, I will raise)
    - The sharing online via Binder?
    - Overall, there is nothing special here: don't share confidential data.  Sharing code that deals with it is a good compromise, but also make very sure there isn't any output with confidential data in the notebooks you share!

- What about using Git for notebooks?
    - we will demonstrate challenges and solutions when using Git with Jupyter +1
    - (this is one of the main take-aways of this lesson!)

- But how is the privacy with running the code in googlecolab/juypter? or should you then copy the code and only run it on your computer
  - If you use a remote server for compute, then yes, that matters: you are sending the data to somewhere, you need to see if that's allowed by your organization's rules.
  - More likely you would run Jupyter on your own computer, or a local cluster.  It's easy to do this

- what is the difference between jupyter notebook in googlecolab and visual studio?
  - we can make sure different things are defined well:
  - there is "jupyter notebook" and "jupyter lab" applications - this is the interface.  jupyter and colab/etc are different
  - There is also the file format, `.ipynb`.  This is the "jupyter notebook file" and is used by different programs.
  - So to answer your qusetion: they can use the same file format, but run differently.
  - (I'm not too sure about what the vscode part is)

- Is there a convinient way to convert notebooks to e.g. python scripts instead of just copy and paste?
    - yes you can export to a python script
    - `jupyter nbconvert --to script [YOUR_NOTEBOOK].ipynb`

- Is it also possible to use without using the terminal? (I'm not very common with using that)
  - Yes - it starts a web browser.  For example Anaconda Navigator can start the notebooks automaticaly.  There are probably other shortcuts that automatically start (the mentioned "jupyter desktop app")

- Will you show how to look at git diffs between notebooks in e.g. VS Code?
    - yes :-) in the notebook. maybe also vs code.

- For reference, if you want to have the precisely same programming environment as the presenter, it is this one: https://coderefinery.github.io/installation/conda-environment/

- can i do this exercise on visual studio?
  - Jupyter can be edited from VS Code but we don't have instructions right now.  (right now, you should mainly watch, we aren't giving time to follow along)

- what kind of kernel should I choose?
  - one of the Python ones (note we aren't expecting you to type-along now, we will be going fast.)
    - hopefully we are not fast or too fast but the goal is we demonstrate

- what is a jupyter lab?
  - it is the program that can launch jupyter notebooks, but it can do more: there is a text editor and maybe also a terminal shell.
  - "jupyter notebook" is the file format, "jupyter notebook" was also the first web interface.  "jupyter lab" is a more modern one.


## A first computational notebook (demo)
https://coderefinery.github.io/jupyter/first-notebook/


- What about zoom and get values in a plot? Just not a static plot. Interact with it. As an example if I point to a value to see the coordinates, zoom in and so on.
  - what do you mean with "zoom"? ah! interactive plots
  - There are some other plotting libraries that do that.  "Plotly" is one, does anyone know if Matplotlib can do that in Jupyter?
      - it is possible to do that with matplotlib and the interact-widget of jupyter but I would go for a plotting library that supports it on its own
      - If you install `ipympl` (https://matplotlib.org/ipympl/) you can use `%matplotlib widget` at the beginning of a notebook to make plots have pan/zoom, etc.

- How does the computational speed compare between a jupyter notebook and running a script in the terminal?
  - In theory, no difference.  The notebook is running in a normal Python interperter under the hood and doesn't really know Jupyter is seeing results.
      - AAh I see, thank you for the clear answer

- What is the benefit of using jupyter notebook comparing to script in the terminal?
  - Maily the interactivity.  Most of us would recommend terminal and normal programs when that works.  Jupyter good when you need interactive exploration or debugging, but once you know how it works, move to terminal if you need to run a lot.
     - Thx

- Any reason to use JupyterLab instead of e.g. VS Code? Can VS Code accomplish the same things?
- -
  - great question. I will try to discuss it on stream ...
  - VS Code can serve as an interface to the same notebook format: https://code.visualstudio.com/docs/datascience/jupyter-notebooks
  - Our goal is to show the idea of using code/data/results interleaved and tools to support that, not the only the "Jupyter" program.
  - it can accomplish the same thing; it is a matter of preference
  - With supercomputers, the jupyter-lab can run directly on the remote computer. Although one can setup VScode with a remote kernel, it is less trivial to set it up properly, while with jupyter-lab is much more straightforward.

- Just a comment. There is a nice app called - jupyter-notebook-viewer to view Notebooks in e.g. MacOS Finder
- https://github.com/tuxu/nbviewer-app
    - nice! thanks!

- This might be a bit specific but lets say I have folder with images that I would like to access through jupyter and be able to display and move between images with arrow keys. Is there an extension for that? I imagine opening a spearate output window and going through chosen folder image by image.
     - hmm... maybe you can describe also the use case. what it would be used for. maybe this will help us to think about how to solve it technically. but might be too much to share.
     - I found a solution to display multiple images at once but not in this separate window and not such that you could navigate. Here: https://saturncloud.io/blog/how-to-show-images-in-jupyter-notebook/
         - Usually if I generate a lot of images I just then go with file explorer to see them

- Repo used in live-demo: https://github.com/MatiasJJ/jupyter-binder-demo

- Hi!
  A question that is unrelated to this topic but generally in line with the workshop:
  How bad is it to download (from my old institution gitlab) only a subfolder of the repository, corresponding to a submodule that I want to continue developing. The repository is dead since all working on them are not anymore at that institution. Other modules will be in separate repository due to licensing issues.
  I realize I will lose all commit history.
  But the history is so poor.
  - I agree, it's OK to lose history.  it might be nice to not but in 1 year probably no one will care.  Better to have anything that be perfect and not do it.
  - ("do you have license to keep developing that one part" is a different issue)

- A Conda question. Is it possible to automatically switch conda env when switching project folder in the terminal? I assume it switch when using VS Code?
  - yes can be done (but I need to look up details ... later)
    - ah yes it was direnv that I have tried (below; thanks)
  - Oh I'm also interested in knowing about that.
  - I don't think there's a general/built-in solution, but you can do it with bash/zsh scripts, see e.g. https://stackoverflow.com/questions/73335501/automatically-conda-activate-when-in-directory-and-source-export
  - The cleanest is probably to use a solution like [autoenv](https://github.com/hyperupcall/autoenv) or [direnv](https://github.com/direnv/direnv) which allows you to have a shell configuration file for each project, in which you can activate a conda (or other virtual) environment, but also e.g. set environment variables that your project might need.
  - What about this?:https://github.com/bckim92/zsh-autoswitch-conda

- More about Conda. What is the best tool for managing dependencies in Python for research: conda, pipenv, virtualenv, poetry, pyenv? Here you use Conda, but what if others in the organisation (other scientists or developers) use some of the others and want to use the code?
  - Different cases work for different thing, but the main question: Conda package repositories (conda, mamba, etc) or Python Package Index (pip, pipenv, etc).
  - Conda is more self-contained, for science this means it can include C/Fortran libraries necessary to run code without needing to install libraries locally.
  - Python Package Index is for Python only (sometimes with bits of other compiled code along with it, but some situations can be too complex to work well)

- Tomorrow, we see an example of a project that starts in Jupyter and we slowly move to reusable command line scripts.

- How advanced can you get with widgets?  Does anyone have experience with this?
   -  I have used it for a time series where I can slide across years and the figure adjusts to it.
   -  I'd say it is quite powerful in the sense that you can easily set it up and connect it to your code in various ways. It is certainly not a full replacement for a graphical user interface or web site, i.e. you are much more limited in how you layout and style things.

- Mentioned JupyterLab Desktop in the stream: https://github.com/jupyterlab/jupyterlab-desktop
    - See the readme for installation options


## Feedback

:::info
News for day 5:
- We covered documentation and Jupyter, as expected.
- Tomorrow is our last day, and really wraps everything up
    - Testing: putting all the git and github things together to see how to have checks to improve your code.  It's very useful
    - Modular code dev: An exciting live-coding section, we start with a basic plot in Jupyter and show how we make it more and more modular until it's a reusable program.  Don't miss it!
- Don't forget "bring your own code" sessions, where you can bring the exercises or real projects and get live advice. See schedule.
:::

Today was:
- too fast:
- too slow:
- right speed: oooo
- too advanced:
- too basic: o
- right level: oooo
- needed more exercise time: oooo
- needed less exercise time:
- I will use what I learned today: ooooo
- I would recommend today to others: ooooo
- I would not recommend today to others:
- too slow sometimes, too fast other times:

One good thing about today:
- Everything!
- Very good materials. o
- I like the "why" rather than "how" approach.
- Nice jingle!
    - Thank you 🥳

One thing to improve for next time:
- Some trainers are not as easy to follow as others - morning was a little worse than other sessions. I realize it is no easy task. Thank you for all your efforts. o
    - Thank you for the feedback. Sometimes it is also the lesson topic / material flow that affects how the lesson goes. For me it is an interesting question on how to have this kind of lesson flowing as we don't use slides. -M
- More cats. +1

Any other feedback?
- Morning hard to follow but good to have source material to refer to. Thank you for nice materials. Jupyter is not too applicable to my usecases, still nice to have the info. I wish I had a permanente collaborative document to ask all questions :) Tahnk you.
- Sorry, no really time to follow today either... need to look the videos later.
