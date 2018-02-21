# DS1 Course Supplemental Resources


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

### Pipe operator

In Unit 3, you will be introduced to the _dplyr_ package and the pipe operator (`%>%`). I provide a small preview here to show a broader application of the pipe.

_dplyr_'s pipe operator is used exclusively with data frames and the _tidyverse_'s extension of the data frame, the _tibble_, but is borrowed from the _magrittr_ package. With _magrittr_, the pipe and may be used in all of your code to create code that is easier to both write and read. The advantages of the pipe operator are espoused in the [_magrittr_ vignette](https://cran.r-project.org/web/packages/magrittr/vignettes/magrittr.html).

Borrowing from the vignette, the following sets of code are equivalent. The first version is a standard function call, as you will have practiced them in Unit 2:

	car_data <- 
	  transform(aggregate(. ~ cyl, 
	                      data = subset(mtcars, hp > 100), 
	                      FUN = function(x) round(mean(x, 2))), 
	            kpl = mpg*0.4251)

As we read this code, we have to build an "outside-in" understanding of what it's doing: "assign to *car_data* the transform of the aggregate data that is the rounded mean of the second column of a subset of *mtcars*, converted to *kpl*."

The _magrittr_ version uses the same functions, and while less compact, it is easier to read thanks to its top-down flow; we can just read straight through what is done.

	library(magrittr)
	
	car_data <- 
	  mtcars %>%
	  subset(hp > 100) %>%
	  aggregate(. ~ cyl, data = ., FUN = . %>% mean %>% round(2)) %>%
	  transform(kpl = mpg %>% multiply_by(0.4251)) %>%
	  print

This might be read as "with *mtcars*, get the subset of records where *hp* is greater than 100, *then* aggregate by calculating the mean, *then* transform the result to *kpl*."