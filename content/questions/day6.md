+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 6"
+++


## Icebreakers

- What should we say for our "audio test"
    - longer words than 1 2 3 4 5
        - but what exactly?
    - something that actors use before going on stage but that rhymes with fair software?
      - from GPT: "Sally scripts sleek software solutions swiftly"
    - "A Unix saleslady, Lenore,
       Loved her work but she loved the beach more.
       She found a great way to combine work and play:
       She sells C-shells by the seashore."

- What's the worst bug you have seen or experienced?
  - Typical stages of debugging: "how come this is not working anymore? that's impossible!", "ah ...", "how come this ever worked before?"
  - Not being able get same results when running the exact same code for iterative algorithm for numerical solution of a particular tiny problem on two different machines. Eventually turned out that differences in computer architecture led to larger than expected differences in rounding/numerical precision propagated over iterations (third or fourth digit after ca 10 iterations). This taught me about the importance of not testing for exact equality against expected results but allow some tolerance (here the tolerance needed to be fairly large). CHoosing a suitalbe tolerance can be a bit of a dark art...
  - Implemented a new section of a code and somehow a different section broke. I was not using version control or tests, so it was hard to figure out. Also, it was a memory bug in a C code...
  - Some climate model decided to randomly let a supervolcano erupt for no reason. No idea how they fixed it. (It was a new model and not yet very well tested)
    - wow :-)
  - ETL code which at first seemed to work fine but corrupted the data in a way which was not obvious (eg. corruption was very difficult to detect )
      - what does ETL mean?
      - Extract, Transform, Load - it was code for migrating data from a legacy system (DB) to a new one
        - thanks!
  - A colleague scripted a pipetting robot to put a stock solution from one tube to another, but defined the coordinates wrong, didn't test the script, and then a very expensive stock solution was pipetted into the void..... :(

- How do you make sure your code continues to work when collaborating with others?
  - We agree on a set of tests that we want to still work.
  - Automated tests that we run regularly. If you don't want others to accidentally break your code, create an automatic test for your code.

- You just got an idea on how to change your code. But how do you make sure it continues working after the change? Any tricks you use and can share?
  - I run the code after each change and compare results. I use "git add" (staging) often.


## Automated testing: motivation
https://coderefinery.github.io/testing/motivation/

- This is about testing code, but what about testing that e.g. a python package installs correctly on all systems?
    - also this could be part of an automatic test suite where the install step and/or packaging step is being tested on a range of versions and operating systems (containers)

- Also testing for data, eg. if some transformation are done it is sensible to test, if the result is valid.
    - yes. very good point.

Vote in the notes and we’ll discuss soon. It is always a balance: there is no “always”/”never”.

  1. Jupyter or R Markdown notebook which produces a plot and you know by looking at the plot whether it worked?
   - votes: ooooo
  2. A short, “obviously correct” Python or R script which you never intend to reuse?
   - votes:ooo
  3. A simple short, “obviously correct” shell script?
   - votes: o
- Can you give other examples?
  - How obvious is obvious? What is obvious to me, might not be obvious for others.
  - Much of your exploratory data analysis is done interactively : you cannot go about testing as you do the exploration

- Give examples of things (from your work) that are easy to test.
  - Most numerical outputs are easy to test

- Give examples of things (from your work) that are hard to test.
  - something that requires human interaction (moving mouse, clicking somewhere)
    - browser automation, for example Robot Framework could be used for this (https://robotframework.org/)
  - Plots, especially ones that don't need fitting and have to be evaluated by eye
  - When testing would involve handling of large datasets or testing would take long time.
  - random/non-deterministic results
  - something that uses an AI model developed by somebody else where the model is changing

- What is a test suite? What is difference between it and writting test as code?
  - my understanding: a test suite would be a collection of automated tests that are run.

- You mentioned the firts type of test would be a print. What are the next types, with increasing complexity until a suite?
    - I missed that part but I will try to answer but please ask more if I answer a question that wasn't asked:
      - easiest is maybe to compare result against expected result (string or number)
      - it gets more complicated when we test opening and reading and writing files or databases
      - even more complicated if the function we test depends on other side effects
    - in short: the fewer side-effects a function/component has, the easier to test

- Did you just say that pytest is the only one you know about? Are unittests not the standard? Or nose? Or are they part of the same thing?
   - I agree, unittests are standard, they have been around longer. Also nose. They all do the same thing and all are fine. Pytest is a good one to get started with but there is nothing wrong about "nose" or "unittest". In my personal experience I prefer pytest because I can achieve the same with less typing and more compactly.
       - Well, that comes as a relief because I have always found the nose/unittest part of developing software in python a great challenge
   - We know of others, we haven't seen them used that often.  I've used unittest, but pytest adds enough extra benefits (and removes boilerplate you need) that we rarely see it directly used in practice
       - "boilerplate": jargon for repetitive verbose code that sometimes feels tedious to type
   - Note that `nose` is no longer developed, there's now [`nose2`](https://github.com/nose-devs/nose2), but even its developers encourage you to use `pytest` instead:
     >   pytest is an excellent test framework and we encourage users to consider it for new projects.
     > It has a bigger team of maintainers and a larger community of users.
       - Surprising!


## Testing locally
https://coderefinery.github.io/testing/pytest/

- I have some trouble to follow. I would like to understand the why for what we are doing here!
     - instructors are demonstrating how to add a test for a simple function. the function is one that adds two numbers. the new thing here is to write a test functon (here: "test_add"), which will test the add function.
     - but please ask more about unclear steps and I will try to explain.
         - The what is clear. The why is hard to understand. Is there an option between a "print" and this?
              - I am sorry I don't understand "Is there an option between a "print" and this?"
              - why: we wanted to show how an individual function can be automatically tested and we demonstrate this with a function that is so simple that it would not need a test. but if we would go to a complex function, what we wanted to show, the 'how', might be harder to see.

- Why to use a suite? How it differs from writting a test in my code?
    - Automation, I think and ease of diagnosis. I think you'll see in a minute.

- So does the testing function is nothing more than running the same function with real-life values?
    - yes, running it with pre-defined values and comparing result with expected result and to complain if they don't match
    - Can you then at least explain something about difference between different tests (for instance, unit test, and so on?)
       - unit test: testing one function or one component
       - end-to-end test: testing your whole code (feed it some data, compare the end result against reference)
       - there is a lot more but I don't think one needs more to get started and I would start with the end-to-end and add unit tests only to the most confusing looking functions and those that you plan to change next.

- Possible to use AI to do the test, or write the test? Or a part of it? If so, I suppose it is not free?
     - yes. these days you can ask AI to write a test for a function. you can even do the reverse and write a test and ask the AI to write the implementation for you (sometimes this is simpler). Thank you.

- I don't understand exactly how this works with a more advanced code? Because you sort of give the answer in the test function, but when it is more complicated, you're writing the code so you don't have to do it yourself? I don't get it
    - complicated codes can be broken down into smaller chunks, and each chunk could be tested separately
        - but then you end up testing silly functions :-(
            - let's see if the episode on test design afte the break helps with that, if not please bring it up again :)

- So my greatest problem with testing is that I find it super-difficult to go from routine testing of very easy functions (the `add()` function case you are showing) to more useful tests that actually cover the true functionality of the code. To me, the former ends up being a rather esterile exercise; the latter, too difficult ant time consuming. Maybe better to have some run-through applications of easy examples in a notebook. I am sure I am wrong, but for me that's the bottleneck. oo
    - we have some more real examples: https://coderefinery.github.io/testing/test-design/
    - but I understand your point. going from "hello world" to real world is a big jump
    - in real code I would start by adding a test to the function that I need to change, before changing it. And that might be very difficult already if the initial function was not well designed (if it has many side effects that are hard to control)
    - alternatively I would always first start with an end-to-end test before going into unit-testing everything.

- Should we always have the test, in the file we are wishing to test? I mean our script that we wanna test
    - The tests could also be in a separate file

- This explains how to use a specific tool for a simple test. I would be interested to understand regardless of what tool how create better tests. How to make sure my example is representative.
     - after the break, we will talk about test design, if that does not help with your question, please bring it up again

- Can you test a particular `test_` function without running through all the functions in a file?
    - Yes, you can run only a subset by name of it or all that match a certain name pattern.

- There was a mention that the benefti of this approach evrsus test as plain code is that it can be automated. How is it automated? When is it run?
    - eg using GitHub actions, coming up now on stream
    - this way the tests are run after each "git push" or pull request and it can automatically become part of code review

- Ho have you used this in developign research code? Can you give som examples?
    - "this" refers to automated testing? or what precisely?


## Automated testing
https://coderefinery.github.io/testing/continuous-integration/

- Why is substract still a + b? thanks
  - A demo of something broken in the exercise.

- I am so confused. Is it only me?
  - probably not alone. which part is most confusing? let me help and try to explain/comment.
      - Trying to figure out how this could be applied to my work. Would you usually build one big test that tests the whole thing? When does github run it? When I do a commit? Seems a bit inpractical to have many little tests. Is this somethign you usually do?
         - assuming you have a code that has no tests as starting point, I would start by testing the whole thing and make this a GitHub workflow (if you are on GitHub) so that the whole thing is tested on each commit. this is a good starting point if the whole test takes seconds. but what it it would take hours? then you perhaps rather want to test components. in addition you can test components (functions) but I would not test all but only those that recently broke or those I plan to change (and where I want to have a safety net)

- Repository on stream: https://github.com/rantahar/cr2024-pytest-example

- automated testing for R or Fortran or any other languages will follow the exact same steps or is there any other function or scripting?
    - it is the same approach in all languages:
      - end-to-end test: express in words how you make sure your code works, now translate words to a script, then run that script on every git repo change
      - unit test: write a function that tests another function, find a framework that can automatically run all test functions, make this run on every git repo change
    - also for the local testing we will soon have examples for other languages than Python (thanks to the contributor who just contacted me about this and is working on those)


## Test design
https://coderefinery.github.io/testing/test-design/

- Do you have a practical way to test low level functions that interact with external hardware?
    - emulate the external hardware for the purpose of the test
    - this is not an answer but maybe helpful anyway: some things are just hard to test but try to move the hard to test part to the "outside"/"surface" of the code and make the "insides" of the code not depend on external devices and side effects and thus easy to test. is that clear? should I give some example?
        - I think it's clear, my question was like : I have a C++ driver that configures a motor drive with a lot of sequential steps. Is there a way to make sure that nobody breaks that configuration?
            - in this case there might be an API layer between the driver and the motor and there could be a model motor that has the same API and the test would interact with the model motor ("software motor"). and now people changing the motor need to make sure they don't change the API without telling you.
                - ok, understood, thanks :)

- For example of a complex solver, where one subroutine calls another subroutine in another script (inlcuding all variables), how to design the test without running the whole solver?
   - in this case you would test a subroutine or few of those by reading their input data from a file and comparing to a reference. I would probably start testing the whole solver but with data that has small enough dimensions/size so that I can test everything in seconds/minutes.
   - thanks!

- Could we discuss a little about theory?
   - theory of testing?

- I am trying to understand a good workflow in Python. If I do a test it will apply to the current version of the code, but if I e.g. add a function in Python I also need to add a test for the new function. So what is a good workflow? Do a new test for each function? And how to do the commits, one for the original code and one for the test code? It is a bit confusing right now.
   - when writing a new functionality, if you decide to also write a test for it, I would add both in the same commit. They go together. In a sense, the test can be considered documentation for the function. But also no problem to add the test function in a separate commit later, especially when adding a test months after the original function has been written.
   - and maybe you think: I want to make sure that all commits of the git history should be correct. But that is maybe too ambitious and not needed. In reality some commits will be broken and that is fine. This is why we do releases where we can tag certain versions that we know to work well.
   - Thank you, good suggestions.

- Usually in my work I have some kin d of research test, which determines how successfull the propose d approach is. Would it make sense to formulate this as an end to end test, where if the reserach error is too high, the test fails? Is this something you would usually do?
   - yes. I find it useful exercie to write down in words how you check that the code is working. This may sound silly but I find it helpful step towards writing an end to end test. Such test could be: "I check that result x is within the range [a, b]"
   - such an end-to-end test can be very useful for another person who does not know where/how to look where it works.

- So far I ahve no tests in any of my code. I usually work with images. So usually I plot the results on top of the input image and evaluate visually if it was successful. I am thinking I could formulate this as a test by manually annotating a couple images and evaluating if I am too far from the annotation. What is the advantage of this during the development stage?
    - You could start with tests that don't even look at the output: does the code run without errors?
    - can you give it a blank image which should always return a null value?
    - can you make an artificial input image that gives a positive result?
    - if you wanted to test everything, one could program to compute some sort of "diference" between image and overlay. but this might be too difficult. here I might stop by testing all the non-trivial inside functions but still do the check visually. But the visual inspection can be scripted if you really would like to do that.

- Do you consider the "research test", where you plot results a test? I am thinking how it relates t this type of testing. Does this make any sense? Also, bit silly detail, maybe. I have been trying since one of our previous lessons to have my directories organized in better and more standardized way. Would you have under directory ./test rather than ./src the research tests?
    - second question: many/most projects like to have src and test as directories and thus to have them separate. personally, I prefer to have my tests close to the functions they test since I read tests a bit like documentation.
    - first question: it could be interesting to write down in words on how you look at the plot to evaluate whether it is reasonable. this can be sometimes a good starting point to evaluate it purely by code. but often evaluating visually is enough. already a readme that describes how to check the plot would be a useful thing for me as next student in this project.

- This an example how one my "research tests" is formulated. Could you comment on this? Ideally, the parameters should not be hard coded, but uploaded from file, correct? Main question is, I guess, - how to do this better?
   - if the test fails, how will it fail? what will be printed or what will be the result?
       - Right now it is visual inspection of image. I am trying to find specific point in image so visually it is quite obvious. I am thinking now to compare it to labelling of image values. In the image I am "testing" one image. After that I ru na  loop and compute the results for all images and compute statistics. I guess the reason why I added the "one image" is because I did not want to waste the time of runnign it for the whole dataset if the resul is horrible. Therefore I was thinking this might be worth formulating as a test.
          - it is good strategy and good idea to have a small subset to quickly check instead of running everything.
          - in this case if the test has to happen visually, I would describe it in the documentation for the next person
          - (this does not answer the question) in this code what I would try to improve is to provide the file or image number as argument to your script. it will make the code more reusable if you can run it on different images without changing the inside of the code.
              - It's good. It answers the question "what to do better". Thank you. It's quite clear after re-reading.
                 - yes. or even not have a for loop but process one image at a time. then you can iterate/loop over them outside of the matlab code and this might make it easier to process many at the same time.
                    - When you say outside of Matlab? You mean with soem of these tools we learn here? Like with the github tests?
                        - outside of matlab could be tools like snakemake (from tuesday) or it could be a shell script. this is only relevant if the processing takes a too long time and you want to process many at the same time to make use of many cores in your computer. if runtime is not an issue, it is simpler to have the for-loop inside your matlab code.

- does the big project include test codes in the source code or do we see only the final version of codes which were tested previously?
    - you mean other big projects? they typically have both source and test. when we download and install them, we often don't run the tests anymore but we rely on others having tested them well for my computer and I only install the source or binary. but in the repositories we always find both.

---

## Modular code development
https://coderefinery.github.io/modular-type-along/
*This is purely a demo: watch and give suggestions*

Questions:
A. What does "modular code development" mean for you?
   - Code is organized such that functions are reusable and extendable.
   - No need to copy-paste code within one project because I can use the same function once more.
   - I've to admit that I have no idea what it is
   - I can copy-paste functions from one project to another and it will still work.
   - Reusing parts of one project in another project.
   - may be bunch of different functions performing bigger actions.


B. What best practices can you recommend to arrive at well structured, modular code in your favourite programming language?
   - Functions that do one thing instead of many different things.
   - Write functions that do not have hidden side-effects.
   - Make your code testable.
   - Give functions names that make sense
   -

C. What do you know now about programming that you wish somebody told you earlier?
   - This workshop exists.
   - Simpler is better than sophisticated.
   - Simple is better.
   - Sharing code before it's beautiful and perfect.
   - Any code that works is right code.
   - code management
   - "the problem you are solving, is not probably unique"

D. Do you design a new code project on paper before coding? Discuss pros and cons.
   - Sometimes on whiteboard with collagues. Pros: we think a bit before all the typing.
   - I have not done it all - considering structure before starting - and startign to realize the importance.
   - Only seen once while learning how big project gets develped.
   -

E. Do you build your code top-down (starting from the big picture) or bottom-up (starting from components)? Discuss pros and cons.
   - I would start with the components because then it's the easiest to test each component separately before you get a really big thing that doesn't work and you have no idea where it doesn't work (if that makes sense) o
   - Design: big picture. But the coding from bottom up: make components work and then combine them.
   - Unfortunatly not. I am thinking if I did it it might end up with a organization that makes more sense.
   - bottom-up.

F. Would you prefer your code to be 2x slower if it was easier to read and understand?
   - That depends on the size of the project, if it takes 2 seconds instead of 1 second, fine, but if it takes 2 hours instead of 1 hour, not fine
   - No if it is an Earth System Model
   - It depends. If e.g. it is something running in real-time as a service that delay can cause problems on a web server. If there should be an output each minute and the underlying algorithm takes half a minute then there will a problem if it instead take a minute.
   - Yes. What I am doing currently is not too time critical. And I feel if I liked more my code and organization I might really be more productive.
   - Yes, absolutely.
   - No, I would rather like to improve the code with updates on making the computing faster with version control. So that I can have both easy readable version of code and advanced version of code with me.
   -


## Below here, ask and give us suggestions what we should do with the code
https://coderefinery.github.io/modular-type-along/lesson/


### Done

- do not load data always when you are creating a plot, eg. separate data load
    - good point. let's create a data loading function

- Separate the "read data from file", "compute statistics" and "plot results" steps out into different functions.
    - and separate into 3 different cells

- should the filename .png also be changed to the N of the measurements
    - yes!

- Optional arguments in '''plot_results''' for color and linestyle
    - thanks! (moving this to "done")

- how about version control?
     - in progress ... (moving this up to "done")

- Let '''get_temperatures_from_file''' take the file name as an input.
    - yes, this would make it more reusable if the file name changes
    - and maybe instructors won't do it but it is a good idea

- Use argparse from terminal with different input
    - great suggestion. I think we will try later
    - related: Later it would be nice if I can change the number of measurements without going into the code
    - instructors use "click" instead but both would be fine. Interesting, did not know about click.

- show how/where to track dependencies like "click" and "pandas", e.g. in `requirements.txt`

- would you also include a test_ function for this? like in the previous part and if yes, how?
     - yes! we will try that in a moment. for example for the statistics function (in this case it is a very simple example)
         - ok cool :-)


### Discussion/questions

- What is your opinion for the fact that if the libraries like Pandas already have many functions embedded in it. So, making it modular will give you same computing time or longer?
    - do you mean that we should try to not re-implement something that a library already contains?
      - Yes, you got me right. However, I understand that in this course it is being shown just as an example but I want to understand this in context of bigger projects with number of modules.
         - if a functionality is already available as part of some of the popular libraries, it is almost always better to use those instead of writing own. they are well tested, potentially more efficient, and also to the code reader they might be familiar and they don't even then have to read the code instead of trying to understand my own re-implementation. re-implementing can be fun for understanding and learning but takes time. i would only re-implement if including an external library unnecessarily increases project complexity.

- I'm a real noob, but does it matter whether you describe the function before the function or as it is now, in the function itself? Because the comments were written before the function. or is it personal taste?
    - to somebody reading the source code it does not matter and both are fine. one advantage of the docstring documentation is that this can become visible to people using the function and they don't even have to open up the code. for instance in the jupyter notebook you can ask for help about function and it will show the docstring. or you can auto-generate documentation from docstrings. and then the latter can be advantage. but for my own code, only used by me, tiny project, both are fine.

- should the color or font or marker (in other cases) be global variables, which are defined outside any def?
    - because you would like to change it for all plotting functions in your project in one place?
        - yes exactly, i don't want to define color/font etc in every def, but i get the point
    - upside: one place controls all -> convenience
    - downside: the function becomes less copy-pasteable to other notebooks/projects which might not have the globals defined.
    - personally I try to avoid global variables. Although they are convenient but they might bite me later when I use a function somewhere else.

- how far should you include 'exceptions' in your code? for example NA's or if it is not a .csv file
    - and here you mean python exceptions or more generally error messages?
    - if it is just me running my code and the csv file is not there, I will get an error message from Python and understand it. But if I want somebody else to run my code, I don't want them to wonder about an error message they have never seen and want to give them a "nice" error. So for other people I will implement error messages and exceptions.
    - if I expect mistakes or missing values in the data, it is good to preare the code for it. to tell it what it should do with missing data (e.g. stop? or replace by zero?). libraries like pandas can do that.
    - in short: good idea.

- Would you say a modular code is usually a code with more functions? Could we talk more about advantages of having modular code? Can't having code split into many small functions making editting and finding errors more difficult?
    - modular code is often code with functions. i find functions easier to read when I don't have to scroll over many screens so I try to keep them short and simple. Splitting code into smaller units can increase number of files and maybe I have to do some navigating in my editor, but it can make the overall "top level" code easier to follow because then you don't have to read all details but can focus on the big picture.
    - Splitting the code is actually the best way to show how modular the process is. So, as with other technologies (like a car), you can open the box and find which component is not behaving as it should. A long file with lots of code and many nested calls will make it much more difficult to find the broken bit.

- What are the differences between click and argparse?
    - both solve the same thing. take the one that you like better. argparse is part of python already. click needs to be installed.
    - I personally use click because I like how new arguments are introduced.
    - If you want to compose command line interfaces in a project that combines libraries with their own command line interfaces, then click is better because it has been written to solve that problem.

- For clarification: The order of the @click.option lines need to match the order of the arguments in main() ?
     - yes, it will map them to the arguments of the function that comes right after

- Correction: https://click.palletsprojects.com/ is not part of Python 3 though. You need to install the dependency. It is part of the [CodeRefinery software environment](https://github.com/coderefinery/software/blob/main/environment.yml).
   - it is not part of standard python :-)

- Click uses a BSD-3-Clause license. Does this mean repos using click can not be licensed under the MIT license?
     - if we install and import it, we treat it as library/plugin and it does not affect the license of our code since we don't need to distribute the library with our code (people can then fetch the library themselves)
     - it would be different if I copied part of click code into my code, then I would have to think about license compatibility.


### Maybe we didn't do this (for time) but these were good ideas

- Set fixed ylimit in order to make comparing the plots easier
     - plt.ylim
        - good suggestion!

- Can calculate max and min of dataset to decide y axis limits

- can make the max value a flexible value as the max of the dataset in pandas. same is the case of min value.


### Suggestions/questions to presenters

("done" suggestions moved up to make it easier for presenters to read what is left to do)

What do you think is better for sharing software:
 - A good command line interface: oooo
 - A notebook anyone can run: o

- Should you learn the command line?
    - From the article "Five reasons why researchers should learn to love the command line" https://www.nature.com/articles/d41586-021-00263-0 :
        - It facilitates handling large datasets efficiently.
        - It supports the automation of repetitive tasks.
        - It enhances reproducibility in scientific research.
        - It offers powerful tools for data manipulation and analysis.
        - It is essential for using many scientific software and conducting high-performance computing tasks.

- Where to find more resources and examples on modular development and testing for research?
  - a number of papers that start with "ten simple rules for ..."

- Can you give some examples of small, good projects? Or even some good examples from own projects?
   - I am hesitant to share own projects since it could look like self-promotion :-)

One resource, not sure if has been mentioned, is The Turing Way online book: https://the-turing-way.netlify.app/index.html

Also some good stuff at Software Carpentry: https://software-carpentry.org/


### Discussion

What are the benefits?

What else could be done?


## AI and code
- GitHub copilot??

- I have used it to translate Matlab code to Python

- I used to fix some errors in my python code, and somethime to make my code more modular, but not to generate from the scratch. {ChatGPT}

- I use to write initial scripts and for optimization of python code. I also ask for writing scripts for Blender (which works quite nicely).

- Can AI help us to recoding already available analysis scripts, actually any scientific software written in any languages?
   - translating from one language to another? yes, it can do that.

- What AI website/software/model do you recommend?
   - many of my colleagues use either GitHub Copilot or ChatGPT (or both)
       - tnx, possible to have a copilot extension in VSCODE?
          - yes. then you can have code on the right side of your editor, and you can on the left side even chat with the model and ask it for suggestions/improvements
          - tnx, what about Spyder environment?
            - I am unsure. The editors that I know that have integrations with copilot are vscode, neovim, vim, pycharm (jetbrains IDE)
            - tnx.


## Outro
https://github.com/coderefinery/workshop-outro/blob/master/README.md


## Feedback

Today was:
- too fast: o
- too slow: ooo
- right speed: ooooooo
- too advanced:
- too basic: ooo
- right level: ooo
- I will use what I learned today: ooooo
- I would recommend today to others: ooooo
- I would not recommend today to others:
- too slow sometimes, too fast other times:

One good thing about today:
- After today, I will start using tests
- I'll try to design test part in a cfd solver
- modularity design
- I am motivated to use automated tests in my projects.
- few inputs on testing codes
- very relevant topics. thank you.
- The caaat!o

One thing to improve for next time:
- I found the modular programming segment quite basic. Might be better suited earlier in the workshop?
- Test design part was complicated as a beginner.
- More focus on concepts, less speceifics.
- I kinda think that maybe at least one open-source code for any reseach topic can be a demo to introduce the concepts, a lite bit more complex.
- I would like to see the same as this course but also for Gitlab, but I understand if that is not possible or take too much time.

Any other feedback about the overall workshop?
- Would like more exersices in second week or in other way being able to work with the topic within the week. oo
- I think this second well will benefit from doing the excercises in groups as in previous workshops. This feeling was shared by most of the helpers here. Should you not have enough helpers / team leaders, the exercise times could be very clear so that part of the people coud work in groups. Kind of "now exercise for 30 minutes", and you go on streaming and those who want dive into the exercises in goups or on themselves.
- I love the quality of the documentation and course materials. Defintely will be shared with more colleagues! oooooooo
- I found the first week incredibly useful. The second week less so, but I will be using some of the things introduced. Either way, the lessons-webpage is a great resources for the future. o
- Do you have more courses? ofocused more on the why rather than how. I find the teaching method where two people discuss very helpful. With richard and radovan on first week dynamic was very smooth and very easy to follow. Topics of second week were of more interest to me, but it was harder to follow. I felt that we got a bit stuck on the how. I think I would have benefited from more discussion of concepts. It is not so relevant for me how to do specific things in python since I won't be using python. Overall, training was good and content was so relevant. Thank you so much for your time and efforts.
- I liked the jingle, but now I cannot get rid of it from my head. ooooooo
- You are all so kind and helpful. I felt safe to ask stupid questions :) ooo
- Really nice rpoject and inniciative. Thank you!!
