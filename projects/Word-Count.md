---
layout: project
type: project
image: img/unduextrois.png
title: "Word Counter!"
date: 2024-02-05
published: true
labels:
  - GitHub
summary: "A personal from scratch version of Linux word count. A EE491F Software Reverse Engineering project from Mark Nelson"
---

SRE Lab 3 - wc
==============

un.. deux.. trois.. CAT!

| **Estimated time to complete** | 2-3 hours | **Prerequisites** | Lab 2 - Catnap                          |
|--------------------------------|-----------|-------------------|-----------------------------------------|
| **Point Value**                | Medium    | **Link**          | https://classroom.github.com/a/45dGM1no |

The Big Goal for this lab is to write your own `wc` program (from the reading 
assignment).  It won’t do everything the Linux `wc` does, but the process of 
writing this program will get us into the complexities of C and, in particular 
file I/O.

The `man` page on the `wc` command is:  https://man.archlinux.org/man/wc.1

Write a version of `wc FILE`   For this version, the only command line parameter
is `FILE`.  No need for `-c`, `--lines`, etc.  We will get to that later.  
The requirements are:

  1. Get `FILE` from the command line.  If there is no filename, print an error message:

         Usage:  wc FILE

  ...and exit.

  2. Try to open `FILE`.  If the file can’t be opened or read, print an error 
     message: `program: Can’t open [FILE]`, substituting in the filename... and exit.

  3. If `FILE` can be processed, count the number of chars, words and lines.  
     Then print:

         nn <tab> ww <tab> cc <tab> FILE

     Where `nn` is the number of lines, `ww` is the number of words, `cc` is 
     the number of characters and `FILE` is the filename.

Sounds easy?  On the surface this program looks easy.  Next week, however, we 
will get into why this program is a lot trickier than it seems.

You don’t need to have any comments if you have great file, function & variable
names.  However, like any program you write, assume another similarly competent
programmer who can’t read your mind may take over this codebase.  Write your 
program as if it’s telling a story to that person.

Do your best.  The instructions are deliberately vague.  I want you to apply 
common sense, anticipate what your boss may want you to do and be confident 
that you won’t be marked down for good, honest effort.  This isn’t ‘gotcha’. 
 This is Defense Against the Dark Arts.

To make `wc`, use the following commands:

| Command              | Purpose                                                    |
|----------------------|------------------------------------------------------------|
| `make`               | Compile your program (using clang as the default compiler) |
| `make clang`         | Compile your program (using clang)                         |
| `make doc`           | Build documentation for your program                       |
| `make valgrind`      | Test for memory leaks                                      |
| `make lint`          | Checks your code for bad practices                         |
| `make gcc`           | Compile your program (using gcc                            |
| `make wc`            | Just compile `wc`                                          |
| `make test`          | Compile your programs and run it                           |
| `make debug`         | Compile your programs with debug mode ( `DEBUG` is defined)|
| `make clean`         | Remove all compiler output                                 |


# Documentation
`wc` uses Doxygen's automatic documentation generator.  We will use this to 
(hopefully) write better, cleaner and more expressive code.  

To generate documentation, run `$ make doc`

Doxygen should run clean... but the template program is just that:  A template, 
and so you'll have to do more documentation than you did in Catnap.  
Every global variable, function, parameter and return value should be documented.  
Here's an example:

    /// The size of #encl_debug_buffer when it's allocated
    static size_t encl_debug_buffer_size = 0;
    
    /// Calculate the length of a string
    ///
    /// @param str The string to process
    ///
    /// @return The length of `str`
    size_t strlen( const char* str ) {
       const char *s;
    
       for (s = str ; *s ; ++s )
          ;
       return( s - str );
    }

Visit https://www.doxygen.nl/ for more information.

You are required to have a clean Doxygen run when you submit your code.

You can view your documentation at:  Your source directory / your repo / `html/index.html`


# Lint
Linting is an automated checking of your source code for programmatic and 
stylistic errors.  This is done by using a lint tool (otherwise known as linter).  
Think of this as a static code analyzer.

Linting can detect errors in a code and errors that can lead to a security 
vulnerabilities.  They can also detect formatting or styling issues and makes 
the code more readable for more secure code.

Using a linter is considered a best practice and can increases overall quality 
of your code.

The linting tool we will use is `clang-tidy`.  Use `$ make lint` to invoke it.
Troubleshoot any obvious errors... anything you disagree with, you should bring
to me.


# Git Commands
To get started, accept the assignment and then clone your repo:

    $ cd src
    $ git clone <Your repo>
    $ cd <The new directory>

# Do the lab.  When you're ready to turn it in:

    $ git status
    $ git add .
    $ git status
    $ git commit -m "Initial implementation"
    $ git status
    $ git push

After you've pushed your assignment, go back to Laulima and submit the lab.  
You can continue to make commits until the lab's due date.


# Rubric
  - Well... It should "just work"
  - No compiler warnings in both `clang` and `gcc`
  - `$ make doc` runs clean
  - `$ make valgrind` runs clean
  - The source code must be neat, well formatted and free of "junk" code
  - Write a thorough `/// Result:`  or `/// Example:` section in your `wc.c` header


# Project Checklist
  - Accept the assignment and clone your repo to Popoki
  - Read the man page / Do the reading assignment
  - Fool around with the actual` wc`
  - Plan your data structure
  - Map out the functions you need
  - Get to it...


# When you think you’re finished… use this checklist to close out your assignment
  - Re-read the spec
  - Write a thorough `// Result:`  or `// Example:` section in your `wc.c` header
  - Thoroughly test your code against all of the conditions in the spec
  - Make sure the indentation in the source code looks good
  - Check your comments and program header blocks (including the `.gitignore` file)
  - Look for any `@todo` or debugging code that should be commented out
  - No compilation warnings (in both `clang` & `gcc`)
  - No documentation warnings
  - No valgrind warnings
  - No lint warnings
  - Double-check the rubric / re-read the assignment
  - All work is committed and pushed to your GitHub repo
  - Submit the assignment in Laulima


<a href="https://github.com/SRE-Nelson/sre_lab3_wc-Zeniscribbles.git" style="display: inline-block; padding: 10px 20px; font-size: 16px; color: #fff; background-color: #007bff; text-align: center; border-radius: 5px; text-decoration: none;">Visit Repository</a>

