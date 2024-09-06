---
layout: project
type: project
image: img/catNap.png
title: "Cat Nap"
date: 2024-01-05
published: true
labels:
  - GitHub
summary: "A countdown timer that prints the number of days, minutes and seconds from some fixed (hardcoded) date.
          From EE491F Software Reverse Engineering with Dr. Mark Nelson"
---
SRE Lab 2 Catnap
================

Ready... Set... Sleep!

| **Estimated time to complete** | 180 minutes | **Prerequisites** | Advanced Programming Assessment         |
|--------------------------------|-------------|-------------------|-----------------------------------------|
| **Point Value**                | Medium      | **Link**          | https://classroom.github.com/a/3ejOw7Qf |


The goal of this lab is to:
  - Remember everything you've forgotten about programming
  - Write more algorithms in C
  - Work with structs
  - Research API calls


This idea behind this is very simple... write a countdown timer that prints the
number of days, minutes and seconds from some fixed (hardcoded) date.  It can
count upwards or downwards.  It should "count" once per second, so you'll 
likely have to research a function that can pause for 1 second.

After 10 seconds, it should quit.

You are required to use `struct tm` to convert a reference time.

The output of the program should be in the following strict format:
````
Reference time: Thu May  4 22:41:00 2000

Years: 22  Days: 277  Hours:  9  Minutes: 59  Seconds: 57 
Years: 22  Days: 277  Hours:  9  Minutes: 59  Seconds: 58 
Years: 22  Days: 277  Hours:  9  Minutes: 59  Seconds: 59 
Years: 22  Days: 277  Hours: 10  Minutes:  0  Seconds:  0 
Years: 22  Days: 277  Hours: 10  Minutes:  0  Seconds:  1 
Years: 22  Days: 277  Hours: 10  Minutes:  0  Seconds:  2 
Years: 22  Days: 277  Hours: 10  Minutes:  0  Seconds:  3 
````

To make Catnap, use the following commands:

| Command              | Purpose                                                    |
|----------------------|------------------------------------------------------------|
| `make`               | Compile your program (using clang as the default compiler) |
| `make clang`         | Compile your program (using clang)                         |
| `make doc`           | Build documentation for your program                       |
| `make valgrind`      | Test for memory leaks                                      |
| `make lint`          | Checks your code for bad practices                         |
| `make gcc`           | Compile your program (using gcc                            |
| `make catnap_past`   | Compile the upward counting program                        |
| `make catnap_future` | Compile the downward counting program                      |
| `make test`          | Compile your programs and run them                         |
| `make debug`         | Compile your programs with debug mode ( `DEBUG` is defined)|
| `make clean`         | Remove all compiler output                                 |


# Documentation
Catnap uses Doxygen's automatic documentation generator.  We will use this to 
(hopefully) write better, cleaner and more expressive code.  

To generate documentation, run `$ make doc`

Doxygen should run clean... if it generates any warnings, this means you need 
to document something.  Every global variable, function, parameter and return 
value should be documented.  Here's an example:

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

Do the lab.  When you're ready to turn it in:

    $ git status
    $ git add .
    $ git status
    $ git commit -m "Initial implementation"
    $ git status
    $ git push

After you've pushed your assignment, go back to Laulima and submit the lab.  
You can continue to make commits until the lab's due date.


# Rubric
  - Should count **forwards** or **backwards**
  - Change the dates in `past.h` and `future.h`
  - The numeric columns should align... when transitioning from `59` to `0`.
  - Must use `struct tm`
  - No compiler warnings in both `clang` and `gcc`
  - `$ make doc` runs clean
  - `$ make valgrind` runs clean
  - `$ make lint` runs clean
  - The source code must be neat, well formatted and free of "junk" code
  - Write a thorough `// Result:`  or `// Example:` section in your `catnap.c` header




# Project Checklist
  - Accept the assignment and clone your repo to Popoki
  - Start with Hello World
  - Compile and test by running:  `make test`
  - Research the function `mktime` 
  - Allocate a `struct tm`     Checkout:  `man tm`
  - Populate `tm` and then convert it into a reference time (in seconds)
  - Write a loop... Exit after 10 iterations
  - Wait for 1 second inside the loop… you need to find a library function that 
    does that for you
  - Get the current time (in seconds)
  - Compute the difference between the reference time and the current time and 
    print the results.  _This may be harder than you think._

When you think you’re finished… use this checklist to close out your assignment
  - Re-read the spec
  - Write a thorough `// Result:`  or `// Example:` section in your `catnap.c` header
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


<a href="https://github.com/SRE-Nelson/sre_lab2_catnap-Zeniscribbles.git" style="display: inline-block; padding: 10px 20px; font-size: 16px; color: #fff; background-color: #007bff; text-align: center; border-radius: 5px; text-decoration: none;">Visit Repository</a>


