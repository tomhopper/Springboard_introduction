<style scoped> @import url("rmd_doc_suffix.css"); </style>
# DS1 Course Supplemental Resources


## Unit 2: Programming in R

### The "Whole Game" of Data Analysis

Want to see a whole data analysis? Hadley Wickham walks you through.

[![Whole Game video](https://i.imgur.com/siKpI3i.png)](https://youtu.be/go5Au01Jrvs)

### Types of variables

How we analyze data, and what we do to process data, depends heavily on both the type of data that we have and the analyses that we want to perform&mdash;the kinds of questions we are asking of the data. Having a basic understanding of the theory of measurement scales is therefore very useful in data science, and I [provide an introduction here](http://rpubs.com/tomhopper/r_intro_measurement).

### Assignment operators<a name="assignops"></a>

In examples of R code you'll find that people typically use one of two assignment operators, "`=`" or "`<-`." People coming from a math or programming background often prefer `=`, while long-time R users will often prefer `<-`.

In fact, R supports at least four methods of assignment: the two above, plus `<<-` and `assign()`. In addition, the two arrow operators can be flipped around, like `->` and `->>`.

Each of these assignment operators work a little differently. There is, first, a different order of precedence, so that `x <- y <- 5` produces the same result as `x = y = 5` but `x <- y = 5` produces an error.

Second, the `=` operator actually has two different definitions in R: it is both an assignment operator *and* a syntax token that signals named argument passing in functions. Consider, for example, the difference in meaning between the following two versions of `x = 5`:

```
x = 5
mean(x = 5)
```

In contrast, `<-` can only be used as an assignment operator.

`=` also is not allowed in certain contexts. For example the following all produce different results, and use of `=` will throw an error:

```
if(x = 0)
if(x <- 0)
if(x == 0)
```

In addition, it's a good idea to adopt a consistent style to make your code easier to read. The _de facto_ standard is to assign with `<-` to a variable name on the left-hand side. Following this standard will help others read your code.

If you're not clear what the impact of those differences will be on how your code runs or how others understand your code, then stick with `<-` until you know what you're doing with the other operators. You can't quite trust that `=` behaves the way you intend, but `<-` will.

See `?assignOps` and `?assign` for details, and the answers to this [Stack Overflow question](https://stackoverflow.com/q/1741820/393354) for further explanation.

### Subsetting and extraction

[Subsetting and extracting](http://rpubs.com/tomhopper/182940) data using bracket notation and _dplyr_'s functions. R’s bracket notation, or bracket operators, is a frequent source of confusion for new users. Follow the link for further explanation of how these operators work.

### Installing R and RStudio

#### Windows

Windows users sometimes get tripped up when installing R if they don't have administrator privileges or if their Documents folder is synced to networked storage (fairly commonly set up by corporate IT to automatically back up data). [Installing R without admin privileges](http://rpubs.com/tomhopper/windows_nonadmin_install) walks you through correctly installing and setting up R and RStudio in these circumstances.

#### Programmer's Fonts

RStudio comes pre-configured to use a monospaced font for code. Monospaced fonts use the same width for every character, and this can make code easier to read. There are other font tweaks that make reading code easier. For instance, you want to easily tell the difference between an upper-case letter 'O' and the number '0'. I recommend installing and using one of two fonts.

My personal preference is [Fira Code](https://github.com/tonsky/FiraCode/tree/master/distr). Fira Code not only has nicely-rendered characters, but uses multi-character glyphs to improve readability. For instance, the assignment operator in R is two characters together: the less-than (`<`) and a dash (`-`). Together, they look like: `<-`. Fira Code seamlessly renders this as a single, leftward-pointing arrow on the screen.

For Mac OS and Windows systems, you'll want the TrueType (TT) version of Fira Code.

A good, highly readable alternative is [Anonymous Pro](https://www.marksimonson.com/fonts/view/anonymous-pro). Anonymous Pro does not use multi-character glyphs, but in some ways is easier to read than Fira Code.

After you've installed the font on your computer, you can change the font used by RStudio by selection "Global Options" from RStudio's "Tools" menu, then selecting the "Appearance" pane, and finally changing the font in the "Editor font:" drop-down menu.

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

### Using RStudio projects

The early examples in Unit 2 walk you through the use of the `getwd()` and `setwd()` functions for controlling which directories R searches. RStudio offers a much more powerful alternative: projects. I can't 

RStudio projects is a mechanism for organizing your data, R source and RMarkdown, and output files cleanly and efficiently, with almost no work on your part. When you open a project in RStudio, RStudio automatically cleans up your workspace, ditching data that's not used and saved in the project, switches the working directory to the project's directory, and loads R and RStudio settings and history for the project. You can also automatically set up git version control for each project, making syncing your projects to GitHub a snap. Switching between projects is a simple point-and-click operation, and RStudio supports opening multiple projects at once, each with their own (separate) configuration, history, working directory, and data environment.

RStudio's support site offers a nice [introduction to using projects](https://support.rstudio.com/hc/en-us/articles/200526207-Using-Projects), and you can find some best practices to managing analysis projects at Software Carpentry's [Project Management with RStudio](https://swcarpentry.github.io/r-novice-gapminder/02-project-intro/).

One tip that I'd offer: RStudio will offer to save your workspace to a .RData file. *Always decline*. You can even turn this feature off in RStudio's preferences. As the Software Carpentry article suggests, you should treat generated output&mdash;including data&mdash;as disposable. Design your scripts to reload data at the start of every session. This will keep your code reproducible and save you from the headache of debugging when, at a future point in your code, you discover that your code doesn't produce the data that you've been working with (maybe you applied some data transformation but forgot to save the code to your scripts).

If your raw data is large enough that it's inconvenient to load and wrangle data every time you come back to work on it, you can write your scripts to save cleaned data in a convenient format, and load the cleaned data quickly at the start of your project. By using an `if...else` flow control statement, you can set up your code to only perform the slow loading and wrangling of data once.

Your code for reading in raw data and cleaning it should look like:

```{r}
if(file.exists("data/my_data_frame.rds")) {
  data_df <- readRDS(file = "data/my_data_frame.rds")
} else {
  # Load and wrangle data to data frame data_df
  # This is the part that you don't want to repeat
  # every time you come back to your project.
  
  saveRDS(object = data_df, 
          file = "data/my_data_frame.rds", 
          compress = "gzip")
}
# EDA, statistical analysis, etc.
```

If you ever need to update your data from new raw data, you can delete the file `my_data_frame.rds`, and this code will then load the raw data, wrangle it, and save it.

Whether you choose the RDS file format, as above, or the CSV file format, depends on your needs.

If saving disk space is important, or you want to preserve metadata (descriptions of the columns of a data frame, data source, etc.), then RDS will be the format of choice. If speed of reading and writing is your primary concern, then CSV files using *data.table*'s `fread()` and `fwrite()` functions will be the best format for you, as these are several times faster than any other read and write method in R. The code would look like:

```{r}
library(data.table)
if(file.exists("data/my_data_frame.csv")) {
  data_df <- fread(input = "data/my_data_frame.csv")
} else {
  # Load and wrangle data
  
  fwrite(x = data_df,
         file = "data/my_data_frame.csv")
}
# EDA, statistical analysis, etc.
```

RDS gives the option of saving files with or without compression. gzip-compressed RDS files are generally read into R more quickly than uncompressed RDS files, and take up about a tenth the disk space. There is a small trade-off in write times, as gzip-compressed RDS files take about twice as long to write to disk as uncompressed files, but since you will be writing once and reading many times, this small trade-off is more than made up for in the long-run. `writeRDS()` offers two other options for compression&mdash;bzip2 and xz&mdash;but these result in slower read and write times and typically provide little benefit in file size.

### Extra Practice Problems (optional)

Unit 2 does a great job of providing hands-on examples, but it does not provide any opportunity to share work with your mentor or to stretch your skills by working "without a net." The problems below provide some additional practice of the skills taught in that unit and will help me gauge where I can best focus our efforts to accelerate your learning.

Once you've completed Springboard's Unit 2 lessons, please try your hand at these. Do not spend more than thirty minutes, total, on these problems. Write your code in an R script file, sync it to GitHub, and send me the link so that I can run the same code and check the results. During our next video call we will talk about how this went and what, if anything, challenged you.

1. Create a vector named *my_vec* that holds 5 numbers that you, the programmer, type in.
2. Create a vector with a new name whose elements are twice *my_vec*.
3. Create a new vector of five random numbers pulled from either a normal or uniform distribution.
4. Create a new vector whose elements are ten greater than those in the vector from (3).
5. Create a new character vector named *my_names* containing five names (e.g. Disney names, or five of your friends, or five food items).
6. Create a data frame that contains all five of the above vectors.
7. Using dplyr, sort the data frame by alphabetical order of the names, and save the sorted data frame back to the same data frame variable name.
8. Check the data type for the *my_names* column and ensure that it is a factor.
9. Using tidyr, arrange the data in three columns and save the result to a new variable name. The columns should be: *my_names*, *variable* and *value*, where *value* contains the values of the numeric columns and *variable* identifies which column the numbers originated from.

### Pipe operator

In Unit 3, you will be introduced to the _dplyr_ package and the pipe operator (`%>%`). I provide a small preview here to show a broader application of the pipe.

_dplyr_'s pipe operator is used exclusively with data frames and the _tidyverse_'s extension of the data frame, the _tibble_, and this is how you'll use it in the DS1 course.

However, _dplyr_'s pipe is borrowed from the _magrittr_ package. With _magrittr_, the pipe and may be used in all of your code to create code that is easier to both write and read. The advantages of the pipe operator are espoused in the [_magrittr_ vignette](https://cran.r-project.org/web/packages/magrittr/vignettes/magrittr.html).

Borrowing from the vignette, the following sets of code are equivalent. The first version is a standard function call, similar to those you will have practiced in Unit 2:

	car_data <- 
	  transform(aggregate(. ~ cyl, 
	                      data = subset(mtcars, hp > 100), 
	                      FUN = function(x) round(mean(x, 2))), 
	            kpl = mpg*0.4251)

As we read this code, we have to build an "outside-in" understanding of what it's doing: "assign to *car_data* the transform of the aggregate data that is the rounded mean of the second column of a subset of *mtcars*, converted to *kpl*." Alternatively, we can work from the inside-out, reading it like a recipe. Either way, it can be hard to read.

The _magrittr_ version uses the same functions, and while less compact, it is easier to read thanks to its top-down flow; we can just read straight through what is done.

	library(magrittr)
	
	car_data <- 
	  mtcars %>%
	  subset(hp > 100) %>%
	  aggregate(. ~ cyl, data = ., 
	            FUN = . %>% mean %>% 
	                  round(2)) %>%
	                  transform(kpl = mpg %>% 
	                            multiply_by(0.4251)) %>%
	  print

This might be read as "with *mtcars*, get the subset of records where *hp* is greater than 100, *then* aggregate by calculating the mean, *then* transform the result to *kpl*."
