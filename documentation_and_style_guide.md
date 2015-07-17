# Style and Documentation Guide for Udacity Projects

## Introduction and Rationale
This document provides an overview of the coding style and documentation guidelines for Udacity student projects. Style and documentation are explicitly part of the assessment criteria for some projects, but students are encouraged to follow these guidelines for all projects. 

Why should code adhere to documentation and style conventions? Admittedly, such conventions are arbitrary. Different style guides sometimes flatly contradict each other. For example, [Ray Wenderlich's Swift Style Guide](https://github.com/raywenderlich/swift-style-guide) says: "Indent using 2 spaces rather than tabs to conserve space and help prevent line wrapping". [GitHub's Swift Style Guide](https://github.com/github/swift-style-guide) says the exact opposite: "Tabs, not spaces". 

Paradoxically, it is the very arbitrariness of coding practice that makes following clearly identified guidelines important. Style guides help make code readable to programmers other than the original coder. Large organizations such as Google specify how code is to be written and documented so that when many different programmers are working on a single project, anyone who picks up a source code file will know what to expect. What if you prefer to use spaces to indent your code and I prefer to use tabs, and you then inherit some of my code? Imagine how much time and aggravation it will take you to change out the tabs in my code to spaces. This isn't just a question of aesthetics; if the language we're using is, say, Python, a file we both have worked on, and which consequently has a mixture of tabs and spaces, may not even compile. 

Documentation and style guidelines thus represent **agreed-upon shared conventions within a particular community of coders**. For the projects you submit to Udacity, the community includes your fellow students, the Nanodegree instructors, the coaches, and the project reviewers. Following the specified conventions is necessary for two reasons:

* It speeds up the review process. Reviewers can work through your code much more quickly if it follows conventions rather than being idiosyncratic. 
* It provides good practice toward becoming a professional. As noted above, most large organizations (and even many small ones) have an internal style guide. Even though the guidelines specified by your future employer will certainly vary in greater or lesser degree from the ones given here, following Udacity's style and commenting requirements will habituate you to keeping conventions in mind as you code. 

Learning to follow conventions is more important than the conventions themselves. The point isn't that tabs are objectively better or worse than spaces. The point is that however strongly you may feel right now that using tabs is obviously correct, and requiring spaces instead is just ridiculous (or vice-versa), participating in a community of coders requires respecting the community's norms. 

The overall goal of those conventions is to make your code readable for the community. Joel Spolsky, the founder of [StackOverflow](http://stackoverflow.com/), has identified "a cardinal, fundamental law of programming": **It’s harder to read code than to write it**. The job of a programmer isn't just to write code; it's to write code that is readable and maintainable. Following the guidelines in this document will help you do so. 

The rest of this document focuses on specific aspects of style and documentation: style conventions; commenting guidelines; best practices for GitHub commit messages; and README files.

## Style conventions
Coding style includes everything from matters of format (tabs or spaces?) through naming conventions (how should variables, classes, and methods be named?) to matters of syntax (are global variable okay?). The following resources are considered standard for their respective languages. 

### Python
- [Google Python Style Guide](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html). This guide includes recommendations for both syntax as well as format and layout.
- [PEP 0008 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/). PEP stands for Python Enhancement Proposal. PEP 8 provides the coding conventions for all code that is part of the Python standard library. The focus is on layout and naming conventions rather than on syntax.
We recommend that you adhere to the syntax recommendations of the Google Python Style Guide and the layout, format, and naming conventions of PEP 8. If there is a contradiction between the Google Guide and PEP 8, resolve it in favor of the Google Guide. 

### Swift
- [raywenderlich.com Swift Style Guide](https://github.com/raywenderlich/swift-style-guide). Ray Wenderlich is a well-known iOS guru, and [raywenderlich.com](http://raywenderlich.com) is an indispensible resource for any Swift programmer. The style guide does a good job of explaining the reasoning behind its syntactic and stylistic choices.
- [GitHub's Swift Style Guide](https://github.com/github/swift-style-guide). Considerably shorter than the Wenderlich one, and covers much of the same ground. It covers some points that are missing from the other, however, so it is worth checking out. 
The two style guides are in agreement on almost every point. Where they differ (as in the tabs vs. spaces example discussed above), resolve the contradiction in favor of the Wenderlich guide.  

- Links to style guides or code formatting doc
- No commented out code

## Comments
- Code self explanatory
- No long inline comments, use docstrings for comments

## README files
- describe how to run app, how app works
- Teresa Aysan's PFwP file
- Template? Is it filled in, is it accurate?
