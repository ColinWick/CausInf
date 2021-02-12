Assignment 2
================
Colin Wick
2/10/2021

Data for Economists
===================

#### 1. Summarize briefly the point of chapters 2- 8 in less than one page.

The general gist of the paper is to highlight some basic best-practices
that social scientists can use in their empirical workflow. Social
science is a mode of thinking, empirical methods, and body of theory
that is often framed as independent from hard data science or computer
science. This mismatch on primary skills leads empiricists to have naive
(if not actively horrible) digital workflows and data management skills.
The authors highlight this thoroughly in the introduction.

There are two loose groups that these advice fall into; private workflow
and public presentation. The former roughly encompassing automation,
directories, abstraction, and keys. The latter focused on version
control, documentation, and management. This distinction helps to
understand the general thrust of the paper’s argument. It comes from two
directions.

1.  Social scientists are bad at doing their own projects.
2.  Social scientists are bad at sharing their projects.

Automation and abstraction ought to have been paired, since they both
address the same sort of nitty-gritty coding habits. Economists should
attempt to make their code and process as human-readable as possible,
which includes creating functions that can be documented with a single
line and do a lot of things at once. For example, splitting scripts up
and having them refer to each other (automation) and having an
elasticity function written so they do not need to enumerate the same
diffucult function every time.

The directories and keys are the meta-personal workflow questions,
having to do with data and process management. Having clean data and
directories make for a more efficient workflow when in the process so
that in the future the researcher can re-start without significant
manual work or re-orienting.

The public-facing suggestions are all focused on making the project as
clear as possible to a naive reader. Instead of relying on the esoteric
chain of logic that one can get into when in the middle of a project,
all work should be oriented around brand-new eyes on the project. This
serves two purposes. To the researcher, it forces thinking about clarity
both on a theoretical level and on a presentation level. Forcing clean
directories and documented code will ensure the researcher has thought
through their own process instead of trying random things until
something works.

The transparency afforded by this type of documentation and clarity
lends significant credibility to the researcher’s project. This is no
small thing when doing research and trades at a high premium. Someone
reviewing for publication, replication, or curiosity will be able to
follow each step and replicate as-needed.

#### 2. Why do Genztkow and Shapiro think these elements of modern empirical work are so important?What problems does each element solve?

This was addressed above, but the main issue this paper addresses is
bringing empirical work into the 21st century. Economists have worked
with data since the beginning of the profession, but the profession did
not keep up with the explosion of computing technology. This slows down
empirical work, makes it less reliable, and mystifies the process of
actually doing economics.

Each element addresses best-practices adapted from data science and
programming communities. These include coding style, file management,
and documentation. Each solves the kinds of problems that social
scientists are not trained for since the primary direction of their
education focuses on theoretical implementation of code, but very little
wrt the practical side, so there are huge gaps in knowledge.

#### 3. Give an example of the sort of problem that could arise in the course of an empirical project if someone were to fail to adopt these principles.

Last semester I had a project where I was managing dozens of files and
preparing them for regression analysis. I stored them all in a wide
directory with very little organization to it. Some of the files
required cleaning which I did using Excel, and then finally wrote
everything as an R Markdown file. I was hoping to use this project as a
writing sample but it will require me to go back through everything and
re-do it because in retrospect I don’t have the confidence to publish it
formally until I do. This will take days.

#### 4. How do you plan to incorporate these solutions into your own work?

I’ve already started incorporating this into my process. For example,
creating “Raw Data” and “Cleaned Data” directories when working, and
chopping scripts into “Cleaning” and “Analysis” scripts. However, the
main thing this showed me is that there are huge gains to being even
more intense with my project management. If I have 10 text files instead
of 3, but I can easily navigate to different sections of my work with
ease, that is a low-cost high-margin change I can make. Similarly, I
need to document my code much more explicitly. I am mostly self-taught,
so my code is relatively human-readable but I should improve it.

Github
======

#### 5. Create a new section in the document you used to answer questions 1-4. Briefly explain what git and github are used for, how they are similar and how they are different.

Git is a file management and version control system. GitHub is the most
popular hosting service for this system. One way to think about it is R
and R Studio. R is the language itself; the commands your keyboard send
to your processor and such. R Studio is the way we interact with R,
building all the necessary infrastructure to actually code.

#### 6. Name a benefit of using git to organize your empirical research. What types of common problems can occur if you don’t use git?

Using git is a great way to work on a team since each person can make
edits and there isn’t risk of loss or overlap. People can work on
separate sections of a project and simultaneously edit them, resolve
differences, and roll back when something goes wrong.

If we don’t use git we fall into the problem of having files like
“final2\_FINAL\_version7.r” which is totally unmanageable.

#### 7. What about using git is challenging for you for right now? What steps can you take to minimize those challenges such that you can adopt git for this class?

Right now my main issue is getting all my integrations set up. I want to
work using R Projects and Git, but I’m still working out how to get that
whole process rolling. It seems like, for the purposes I’m using Git,
the main thing I need to do is use it and tinker with it.

#### 8. Name the four main Git operations. What does each operation do and how are is each operation different from one another?

Stage - get a file ready to send to git

Commit - confirm that you are sending a file to git

Pull - Pull any edited files from github

Push - Lock your new files into Git

#### 9. The first step in your new empirical workflow is the creation of a Github repository (“repo”). You can either do this independently or do this through R functionality. You need to create a github account, then create your first repository called “Titanic”. Initialize with a Readme and create the separate folders that we discussed in class on Monday.

#### 10. Post a link to your repository

#### 11. Please clone our course github repository on your desktop

Done.
