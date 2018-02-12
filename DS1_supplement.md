# DS1 Course Supplemental Resources

## Unit 1: Getting Started

### 1.1 Demystifying data science

For a fairly good overview of data science methods, read through [this blog post](http://www.thearling.com/text/dmtechniques/dmtechniques.htm). It provides a good overview of the many methods used in data science. It’s not a complete list, though; “data science” is a pretty broad umbrella.

### 1.2 Start thinking about your Capstone Project

Capstone projects are intended to assess your ability to apply the DS1 tool set, and your affinity for using data science to answer interesting questions. Most of the work will be done in Unit 9, so we have time and flexibility to figure out what you want to work on.

Start with Springboard's Capstone Project Guidelines (the PDF in Unit 1.2), and take the time to follow the links.

If your employer doesn't have a dataset that you want to work on, finding data can be challenging for new data scientists. In addition to the data sources listed in the Project Guidelines, I provide an [annotated and organized list of potential data sources](Project_ideas_and_data_sources.md).


## Unit 2: Programming in R

### Assignment operators

The R examples that you'll find on the web typically use one of two assignment operators, "`=`" and "`<-`." People coming from a math or programming background often prefer `=`, because they're used to it.

In fact, R supports at least four methods of assignment: the two above, plus `<<-` and `assign()`. In addition, the two arrow operators can be flipped around, like `->` and `->>`.

Each of these assignment operators work a little differently, mostly by dealing differently with environment scoping. If you're not clear what the impact of those differences will be on how your code runs, then stick with `<-` until you know what you're doing with the other operators. You can't quite trust that `=` behaves the way you intend, but `<-` normally will.

In addition, it's a good idea to adopt a consistent style to make your code easier to read. The _de facto_ standard is to assign with `<-` to a variable name on the left-hand side; stick with it.

See `?assignOps` and `?assign` for details.

### Subsetting and extraction

[Subsetting and extracting](http://rpubs.com/tomhopper/182940) data using bracket notation and _dplyr_'s functions. R’s bracket notation, or bracket operators, is a frequent source of confusion for new users. Follow the link for further explanation of how these operators work.

### Installing R and RStudio

#### Windows

Windows users sometimes get tripped up when installing R if they don't have administrator privileges or if their Documents folder is synced to networked storage (fairly commonly set up by corporate IT to automatically back up data). [Installing R without admin privileges](http://rpubs.com/tomhopper/windows_nonadmin_install) walks you through correctly installing and setting up R and RStudio in these circumstances.

### Setting up Git and GitHub

#### Git and GitHub&mdash;there's a difference?

Git is a version control system that runs on your computer. It enables you to retain past revisions of your documents. You can "roll back" changes to any of those earlier versions, or you can branch off and attempt different versions of your work.

GitHub is an online file service, somewhat similar to Dropbox, that is designed to work with Git to store and share your version-controlled files online.

#### Installing Git on Windows

The easiest way to install Git, for Windows users, is to install [GitHub Desktop](https://desktop.github.com) (also available for Mac OS). Follow GitHub's [directions](https://help.github.com/desktop/guides/getting-started-with-github-desktop/installing-github-desktop/).

GitHub Desktop provides a desktop app to sync your local files to your online GitHub storage. With GitHub Desktop, you can easily sync your git repositories with your online GitHub account by _pulling_ repositories from GitHub's online servers to your local computer, or _pushing_ from your local computer to GitHub.

Mac OS X 10.9 and later come with Git pre-installed, so Mac users don't need GitHub Desktop to have Git, but the GitHub Desktop application is still nicer to work with than Git's command line interface.

You can check if you have Git installed, and which version you have, by opening the Terminal (Mac OS) or Command Prompt (Windows) and typing `git --version`.

#### Setting up RStudio to connect to GitHub

Though setting up RStudio to connect to GitHub is fairly easy, sometimes a little extra guidance helps. Here are two good resources:

* One of the more accessible guides to [using GitHub with R and RStudio](http://www.molecularecologist.com/2013/11/using-github-with-r-and-rstudio/) is at the Molecular Ecologist blog,
* This nice [step-by-step guide](https://github.com/numeract/learning-R/tree/master/RStudio-IDE/github) by a Springboard mentor, or
* RStudio's own [Using Version Control with RStudio](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN) is a good secondary read.

#### Learning more about git

GitHub's own [Bootcamp](https://help.github.com/categories/bootcamp/) provides a good tutorial for people new to Git, and few resources are as complete as the [Git Pro](https://git-scm.com/book/en/v2) book.

### Extra Practice Problems

Unit 2 does a great job of providing hands-on examples, but it does not provide any opportunity to share work with your mentor or to stretch your skills by working "without a net." The problems below provide some additional practice of the skills taught in that unit and will help me gauge where I can best focus our efforts to accelerate your learning.

Once you've completed Springboard's Unit 2 lessons, please try your hand at these. Do not spend more than thirty minutes, total, on these problems. Write your code in an R script file, sync it to GitHub, and send me the link so that I can run the same code and check the results. During our next video call we will talk about how this went and what, if anything, challenged you.

1. Create a vector named *my_vec* that holds 5 numbers that you, the programmer, type in.
2. Create a vector with a new name whose elements are twice *my_vec*.
3. Create a new vector of five random numbers with either a normal or uniform distribution.
4. Create a new vector whose elements are ten greater than those in the vector from (3).
5. Create a new character vector named *my_names* containing five names (e.g. Disney names, or five of your friends, or five food items).
6. Create a data frame that contains all five of the above vectors.
7. Using dplyr, sort the data frame by alphabetical order of the names, and save the sorted data frame back to the same data frame variable name.
8. Check the data type for the *my_names* column and ensure that it is a factor.
9. Using tidyr, arrange the data in three columns and save the result to a new variable name. The columns should be: *my_names*, *variable* and *value*, where *value* contains the values of the numeric columns and *variable* identifies which column the numbers originated from.

## Unit 6: Data Story

### The importance of the data story

When the Space Shuttle Challenger exploded 73 seconds into launch on January 28, 1986, the engineers who designed the solid rocked boosters at Morton Thiokol knew what had happened. They had predicted it.

They also failed to effectively tell the data story to NASA decision-makers. Their data story failed them, with disastrous results. Edward Tufte has looked at this part of the failure, and you can see some of the slides prepared for the after-accident investigation, and one much clearer redesign by Tufte in [this blog post by Bruce Tognazzini](http://www.asktog.com/books/challengerExerpt.html).

As Tufte concludes in his analysis, "_there are right ways and wrong ways to show data; there are displays that reveal the truth and displays that do not_."[^1]

The data story is, in many ways, much more important than the data analysis itself.

### Writing the report

You have two main deliverables in the capstone project: a written report and a slide deck (e.g. PowerPoint). Writing technical reports is an art in itself, and there is no better guidance in how to write them than [Katzoff's 1964 "Clarity in Technical Reporting"](https://ocw.mit.edu/courses/media-arts-and-sciences/mas-111-introduction-to-doing-research-in-media-arts-and-sciences-spring-2011/readings/MITMAS_111S11_read_ses5.pdf). I _strongly_ recommend reading this 25 page booklet in preparation for writing your project report.

The science magazine Nature also provides an ebook, [_Communication for Scientists_](https://www.nature.com/scitable/ebooks/english-communication-for-scientists-14053993/contents), that goes into somewhat more detail than Katzoff's work. NASA's Lewis Research Center likewise offers a more details-oriented tract, [Vidoli's "Technical Report Writing"](https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/19930013813.pdf).

### Examples

It's much easier to learn what good data stories looks like, compared to "wrong" data stories, with paired examples. Unfortunately, most people don't publish bad versions of their analyses, so these are hard to find. In addition to the example above, Edward Tufte's (inactive) discussion forum contains examples, including a good thread on [cancer survival rates](https://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=0000Jr&topic_id=1&topic=Ask+E%2eT%2e), where Tufte and his readers iterate through the same data multiple times.

Garr Reynolds, of [Presentation Zen](http://www.presentationzen.com), also tries to fill this gap with his books and blog posts on presentation design. Some of the more starkly-contrasted examples are drawn from comparing presentations by Steve Jobs and Bill Gates. The differences in [visual complexity](http://www.presentationzen.com/presentationzen/2005/11/the_zen_estheti.html) and [message clarity](http://www.presentationzen.com/presentationzen/2007/09/steve-bill-redu.html) are clear. Reynolds even compares [Bill Gates to Bill Gates](http://www.presentationzen.com/presentationzen/2010/08/the-naked-transformation-of-bill-gates-the-presenter.html).

## Unit 7: Introduction to Machine Learning

### Time Series

Many data sets are in the form of time series&mdash;data collected over time, with some sort of time stamp. Knowing [how to analyze and decompose time series](http://rpubs.com/tomhopper/354688) will be useful to nearly every data scientist, Six Sigma practitioner, and engineer. Unfortunately, time series is not covered in the DS1 course. Follow the link above for an introduction that may help you with the course.

## Unit 9: Capstone Project



## References

[^1]: Tufte, Edward Rolf. *Visual and statistical thinking: Displays of evidence for making decisions ; displays of evidence for making decisions*. Graphics Pr., 2003.