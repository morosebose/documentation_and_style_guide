# Style and Documentation Guide for Udacity Student Project Submissions

## Introduction and Rationale
This document provides an overview of the coding style and documentation guidelines for Udacity student projects. Style and documentation are explicitly part of the assessment criteria for some projects, but students are encouraged to follow these guidelines for all projects. 

Why should code adhere to documentation and style conventions? Admittedly, such conventions are arbitrary. Different style guides sometimes flatly contradict each other. For example, [Ray Wenderlich's Swift Style Guide](https://github.com/raywenderlich/swift-style-guide) says: "Indent using 2 spaces rather than tabs to conserve space and help prevent line wrapping". [GitHub's Swift Style Guide](https://github.com/github/swift-style-guide) says the exact opposite: "Tabs, not spaces". 

Paradoxically, it is the very arbitrariness of coding practice that makes following clearly identified guidelines important. Style guides help make code readable to programmers other than the original coder. Large organizations such as Google specify how code is to be written and documented so that when many different programmers are working on a single project, anyone who picks up a source code file will know what to expect. What if you prefer to use spaces to indent your code and I prefer to use tabs, and you then inherit some of my code? Imagine how much time and aggravation it will take you to change out the tabs in my code to spaces. This isn't just a question of aesthetics; if the language we're using is, say, Python, a file we both have worked on, and which consequently has a mixture of tabs and spaces, may not even compile. 

Documentation and style guidelines thus represent **agreed-upon shared conventions within a particular community of coders**. For the projects you submit to Udacity, the community includes your fellow students, the Nanodegree instructors, the coaches, and the project reviewers. Following the specified conventions is necessary for two reasons:

* It speeds up the review process. Reviewers can work through your code much more quickly if it follows conventions rather than being idiosyncratic. 
* It provides good practice toward becoming a professional. As noted above, most large organizations (and even many small ones) have an internal style guide. Even though the guidelines specified by your future employer will certainly vary in greater or lesser degree from the ones given here, following Udacity's style and commenting requirements will habituate you to keeping conventions in mind as you code. 

Learning to follow conventions is more important than the conventions themselves. The point isn't that tabs are objectively better or worse than spaces. The point is that however strongly you may feel right now that using tabs is obviously correct, and requiring spaces instead is just ridiculous (or vice-versa), participating in a community of coders requires respecting the community's norms. 

The overall goal of those conventions is to make your code readable for the community. Joel Spolsky, the founder of [StackOverflow](http://stackoverflow.com/), has [identified](http://www.joelonsoftware.com/articles/fog0000000069.html) "a cardinal, fundamental law of programming": **It’s harder to read code than to write it**. The job of a programmer isn't just to write code; it's to write code that is readable and maintainable. Following the guidelines in this document will help you do so. 

The rest of this document focuses on specific aspects of style and documentation: 

- Style conventions
- Writing clean code
- Commenting guidelines
- Best practices for git commit messages
- README file guidelines. 

## Style conventions
Coding style covers a wide range of topics, from the purely aesthetic to the rigidly technical:

- **Format**. Tabs or spaces?
- **Naming conventions**. How should variables, classes, and methods be named?
- **Program Structure**. Are global variables permissible?
- **Syntax**. Is it okay to write ternary expressions that have side-effects?

The following guides are recommended for Udacity projects. 

#### Python
- [PEP 0008 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/). PEP stands for Python Enhancement Proposal. PEP 8 provides the coding conventions for all code that is part of the Python standard library. The focus is on layout and naming conventions rather than on syntax.
- [Google Python Style Guide](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html). This guide is consistent with PEP 8 in its format and layout recommendations. It also includes additional recommendations for syntax. 

We recommend that you adhere to the layout, format, and naming conventions of PEP 8, and the syntax recommendations of the Google Python Style Guide. If there is a contradiction between the Google Guide and PEP 8, resolve it in favor of PEP 8. 

#### Swift
- [raywenderlich.com Swift Style Guide](https://github.com/raywenderlich/swift-style-guide). Ray Wenderlich is a well-known iOS guru whose [website](http://raywenderlich.com) is an indispensible resource for any Swift programmer. The style guide does a good job of explaining the reasoning behind its syntactic and stylistic choices.
- [GitHub's Swift Style Guide](https://github.com/github/swift-style-guide). Considerably shorter than the Wenderlich guide, this document covers much of the same ground. It includes some points that are missing from the other, however, so it is worth checking out. 

The two style guides are in agreement on almost every point. Where they differ (as in the tabs vs. spaces example discussed above), resolve the contradiction in favor of the Wenderlich guide.

#### HTML, CSS, and JavaScript
Udacity's [Front-End Nanodegree](https://www.udacity.com/course/front-end-web-developer-nanodegree--nd001) team has developed a style guide for these languages:
- [HTML](http://udacity.github.io/frontend-nanodegree-styleguide/index.html)
- [CSS](http://udacity.github.io/frontend-nanodegree-styleguide/css.html)
- [JavaScript](http://udacity.github.io/frontend-nanodegree-styleguide/javascript.html). 

Follow the recommendations of those style guides when submitting code written in any of those languages.

#### Java
- For *non-Android projects*: The [Google Java Style Guide](https://google-styleguide.googlecode.com/svn/trunk/javaguide.html) is an excellent resource. As its introduction says, "the issues covered span not only aesthetic issues of formatting, but other types of conventions or coding standards as well".
- For *Android projects*: Udacity's [Android Developer Nanodegree](https://www.udacity.com/course/android-developer-nanodegree--nd801) team has developed a [style guide](http://udacity.github.io/android-nanodegree-guidelines/index.html) for use in app source code. This style guide is a subset of the standard [Android Code Style Guidelines for Developers](http://source.android.com/source/code-style.html). 

## Writing Clean Code

Ideally, code should be so clear and lucid that comments become superfluous. This ideal has been most eloquently championed by Robert C. Martin. In [*Clean Code: A Handbook of Agile Software Craftsmanship*](http://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882/) Uncle Bob, as he is affectionately known, writes:

>If our programming languages were expressive enough, or if we had the talent to subtly wield those languages to express our intent, we would not need comments very much—perhaps not at all.

How does one wield a programming language expressively, so as to minimize the need for comments? One way is to use intuitive identifiers, i.e., variable or method names. Consider the following example. The code is in Python 2.7, but the principles apply to any language:

```python
def mean(arr):
    return round(float(sum(arr)) / len(arr), 2)
```

That's pretty cryptic. Although it's possible to figure out what the code is doing, the code itself isn't exactly readable. An inexperienced programmer might be tempted to explain how the code works:

```python
def mean(arr):
    '''
    Given the array of student scores, take the sum of the array,
    cast the sum as a float, then divide it by the number of array elements.
    Return the result rounded to two decimal places.
    '''
    return round(float(sum(arr)) / len(arr), 2)
```

That really isn't much better, though. The comment merely restates the workings of the code. And the restatement is longer than the code itself! It would be preferable to explain what the code is supposed to accomplish in context:

```python
def mean(arr):
    '''
    Calculate and return the average score rounded to two decimal places. 
    '''
    return round(float(sum(arr)) / len(arr), 2)
```

But the cleanest strategy would be to use intuitive names, eliminating the need for comments altogether:

```python
def get_rounded_average(studentScores):
    return round(float(sum(studentScores)) / len(studentScores), 2)
```

The key takeaway: clean, readable code trumps heavily commented code every time. 

#### When are Comments Necessary?

Does this mean that comments are never necessary? Not quite. There might still be circumstances where code might perforce become somewhat unintuitive. An elegant syntactic formulation might yet be tricky to read, or accounting for edge cases might add complexity. Here's a safer formulation of the `get_rounded_average()` procedure that illustrates both of these:

```python
def get_rounded_average(studentScores):
    return round(float(sum(studentScores)) / len(studentScores), 2) \
        if studentScores else None
```

The revised code makes use of Python's ternary operator to ensure that the program will not crash if the `studentScores` array is empty. However, the revised code is no longer as intuitive to read. A brief comment would improve readability:

```python
def get_rounded_average(studentScores):
    '''
    Return the average of the student scores rounded to two decimal places.
    Return None if the scores array is empty. 
    '''
    return round(float(sum(studentScores)) / len(studentScores), 2) \
        if studentScores else None
```

## Commenting Guidelines

#### Best Practices

When it is necessary to add comments to code, follow these best practices:

- **Be concise**. Keep your comments brief. As we've seen, one or two lines explaining *what* a given function accomplishes can be helpful. But *how* the code works should be clear from the code itself, not from lengthy comments. 
- **Use inline comments sparingly**. It is rarely necessary to explain individual lines of code. A brief comment might occasionally be needed to explain a block of code within a function, but if your function has several such blocks, consider refactoring the code into smaller functions. 
- **Remove all commented-out "dead code" or "legacy code"**. It's never a good idea to leave superseded or not-yet-live versions of the code in commented-out form within the source file. These [two](http://programmers.stackexchange.com/questions/190096/can-commented-out-code-be-valuable-documentation) [posts](http://programmers.stackexchange.com/questions/45378/is-commented-out-code-really-always-bad) on StackExchange explain why. 

In addition, specific languages have guidelines about the best way to document code.

#### Python
Python code is expected to include **docstrings**. A docstring is a string surrounded by triple quotes `'''` that occurs as the first statement in a module, function, class, or method definition. Docstring conventions are laid out in [PEP 0257](https://www.python.org/dev/peps/pep-0257/). As stated therein:

>All modules should normally have docstrings, and all functions and classes exported by a module should also have docstrings. Public methods (including the __init__ constructor) should also have docstrings.

A docstring becomes the special __doc__ attribute of its object, which can be retrieved for reference purposes. Taking the code above as an example, the command `print get_rounded_average.__doc__` yields the following output:

>Return the average of the student scores rounded to two decimal places.
>Return None if the scores array is empty. 

#### Swift
Apple's programming language has a rich set of comment creation and formatting techniques. Some notable features are:

- Option-clicking on the name of a method or a class opens a hovering documentation pane that displays the documentation for that method or class. To enable this, set off single-line comments by using `///` at the beginning of the line. Embed multi-line comments between `/** ... */`. 
- The comment labels `// MARK:`, `// TODO: `, and `// FIXME: ` are treated as special and rendered as part of the documentation pane. 
- Comment text can be made bold or italicized . 

[NSHipster](http://nshipster.com/swift-documentation/) has a brief but thorough explanation of documentation creation mechanisms for Swift. 

#### Java (including Android)

#### JavaScript


## Git Commit Messages
Udacity's instructors have developed a [Git Style Guide](http://udacity.github.io/android-nanodegree-guidelines/git.html) that details how to write a concise, thorough, and informative Git commit message. Note that commit messages are in present imperative rather than past declarative tense. I.e., they specify what the commit should do rather than what was done to the code:

- `feat: Add method to calculate average`     *(preferred)*
- `feat: Added method to calculate average`   *(not preferred)*

## README files
- describe how to run app, how app works
- Teresa Aysan's PFwP file
- Template? Is it filled in, is it accurate?
