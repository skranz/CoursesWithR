---
title: Guide to fixing errors with R and RTutor
output:
  html_document: 
    toc: yes
---

# 1 General procedure when you encounter an error or get stuck in an RTutor problem set

1. If you encounter an error during package installation or working on an RTutor problem set, first check this guide and try the recommended solutions.

2. If you just get stuck with an RTutor problem set, first choose `Addin -> Check Problem Set` and then `Addin -> Hint` to get a hint how to proceed. Often, though not always, the hints should provide sufficient help. Many hints are also adaptive and change, once you change your code. (Secret Tip: If you add a ___ (three underbars) in your code, your hint may change and you see a scrambled version of the solution for the ___).

3. If your course has a question and answers forum, first check it and see whether your problem has already been discussed there before. If you are more proficient in problem solving, you can also google the error message, perhaps adding "R" to your search phrase. That is how I usually quickly find a solution to a strange error.

4. Only if steps 1-3 don't solve your problem write a question in the questions and answers forum (or if no forum exists per email to your teaching assistant or lecturer). Make sure that you describe in detail what you have done, add e.g. the code you have entered, and copy the R output including the error message (can be several lines). If it is a complicated problem, we may directly contact you to schedule a Skype / Webex session where you can share your screen (please make sure that you can then quickly replicate the steps leading to the error). 

# 2 General Advice: Restarting RStudio

- Some strange errors simply go away if you restart RStudio or (faster) choose in RStudio `Session -> Restart R`.

- For a restart to work, it is important that you have adapted the RStudio workspace global option as explained in the setup file and [this Youtube video](https://youtu.be/YxnFAhVoOHg). Here is a short reminder: Go in RStudio to the Menu `Tools -> Global Options`. Set the options for `Workspace` as highlighted in yellow in the Screenshot below and then press "OK".

![](options_saveworkspace.PNG)

(See also this )

# 3 Errors or warnings during package installation

Depending on your operating system and R version, you may already encounter some warnings or errors during package installation. Some can be ignored, others have to be solved for successful installation.

## 3.1 Warnings or errors that can be ignored

```
WARNING: Rtools is required to build R packages but is not currently installed. Please download and install the appropriate version of Rtools before proceeding:
```

You can completely ignore this warning. This would only be relevant if you needed to compile packages with C or C++ source code yourself, but this will not be the case for our courses.

```
> install.packages("rstudioapi")
Error in install.packages : Updating loaded packages
```
This error means that the package (in this example `rstudiapi`) is already installed. You can ignore it.

## 3.2 Other errors: Look for the first error in the output and find the troublesome package

Other errors during package installation may fail to install the package. Sometimes a very long output can occur with multiple errors in your R console. Often later errors are a consequence of an earlier error. So search for the first time an error occurs. Often that is a specific troublesome package that is missing and cannot be installed. First try to install that package.

Here is an example error message:
```
Error: package or namespace load failed for ‘dplyr’ in loadNamespace(j <- i[[1L]], c(lib.loc, .libPaths()), versionCheck = vI[[j]]):  there is no package ‘vctrs’:
Error ‘dplyr’ could not be loaded and execution stopped.
```
We could not install `dplyr`, but looking at the error message we see that the problem is that a package `vctrs` was missing. So we first would need to install `vctrs`. So try typing in the R console:

```
install.packages("vctrs")
```

Possibly, that package was not correctly installed because of the next point:

## 3.3 Don't install source packages when asked

Sometimes you get a question like the following when installing a package:

```
  There are binary versions available but the source versions are later:
          binary source needs_compilation
tibble     1.3.4  1.4.2              TRUE
dbplyr     1.1.0  1.2.2             FALSE
tidyverse  1.1.1  1.2.1             FALSE

Do you want to install from sources the package which needs compilation?
y/n: 
```
You then should type `n` (for no) in your R console to install the binary packages. (Possible if you run more than one code line, you first have to remove some code from your console input to just type `n`). Installing source packages can be complicated and cause failures, in particular since you probably don't have RTools installed.

## 3.4 Packages possibly cannot be installed for your brand new R version

If you have installed a brand new R version it can unfortunately sometimes happen that some R packages are not yet available. Then you get an error message like:

```
    "packages ‘magrittr’, ‘Lahman’, ‘highflights’ are not available (for R version 7.1.0)"
```

I don't know a better solution than installing again a previous release of R instead of the newest version. Here is a website with earlier R releases for Windows:

http://cran.r-project.org/bin/windows/base/old/


# 4 Problems on Mac-OS: Install xquartz

If you have a Mac (or Linux) computer sometimes installing or loading packages can be more complicated because some additional system libraries must be installed. One common problem for Mac is that several packages need xquartz. You may get an error like

```
Error: package or namespace load failed for ‘compareGroups’ in dyn.load(file, DLLpath = DLLpath, ...):

 kann shared object '/Library/Frameworks/R.framework/Versions/3.6/Resources/library/systemfonts/libs/systemfonts.so' nicht laden:

  dlopen(/Library/Frameworks/R.framework/Versions/3.6/Resources/library/systemfonts/libs/systemfonts.so, 6): Library not loaded: /opt/X11/lib/libfreetype.6.dylib
```

This problem could be solved by installing:

[https://www.xquartz.org](https://www.xquartz.org).

# 5 Problems when solving an RTutor problem set


## 5.1 Cannot Check Problem Set? Make sure you have extracted the RTutor problem set files from the ZIP file

Make sure that you always extract all files from the ZIP that contains an RTutor problem set before you open it in RStudio. While it is possible to open the Rmd file directly from inside the ZIP, you won't be able to check your problem set but get an error like:

```
Error in readChar(con, 5L, useBytes = TRUE) : cannot open the connection
```

## 5.2 You don't see the `Check Problem Set` Addin?

If you don't see in RStudio in the `Addins` menu the `Check Problem Set` addin, you probably have not yet correctly installed all packages. In particular, you are missing the `RTutor` package. Install your packages again.


## 5.3 You have not installed all required packages?

Possible some package installation went wrong but that is realized only when trying to check an RTutor problem set. You may get an error like:

```
Error: .onLoad failed in loadNamespace() for 'pkgload', details:

  call: loadNamespace(i, c(lib.loc, .libPaths()), versionCheck = vI[[i]])

  error: there is no package called ‘backports’
```

In that case try to install the missing package, here `backports` by typing in the *console* (**never type `install.packages` in your problem set code**) via

```
install.packages("backports")
```

If your RTutor package is missing or several packages are missing, just rerun the complete package installation code provided with the course.

## 5.4 Error `figure margins too large`

The error message "figure margins too large" can occur when you show any plot in RStudio when your "Plots" pane is too small. Increase the size of the plot pane and then it should work. See also [here for screenshots](https://stackoverflow.com/questions/23050928/error-in-plot-new-figure-margins-too-large-scatter-plot/23050985#23050985).
