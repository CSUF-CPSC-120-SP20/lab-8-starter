# Lab 8: Loops

The purpose of this lab is to practice writing loops with the range-based-for syntax.

This lab involves four programs:
`1-args`, `2-average`, `3-max`, and `4-phone`.

## Goals

* Write range-based-for loops.
* Adapt loop patterns to new problems (accumulation, filtering, counting, optimization, initial special case).

## Range-Based For

All of your loops on this lab **must be range-based for loops**, even if you
know how to write other kinds of loops.

# Credits

Just like the previous lab, you should use Atom to write your
names and email addresses in `CREDITS.txt`.
Write each partner's name and CSUF-supplied
email address, ending in `@csu.fullerton.edu.

# `1-args`

This first program is a warmup that involves looping through all of the
commandline arguments and printing them back out. Your program should

1. Print out a message using the pattern
   ```
   <count> arguments:
   ```
   where `<count>` is the number of elements in the `arguments` vector.
   **Hint:** Use the `arguments.size()` function to get the number of elements.
1. Print each of the arguments (including the command name) on its own line,
   surrounded by square braces, like
   ```
   [argument]
   ```
   **Hint:** This is similar to the *Example: Looping Through Arguments* slide.

## Test Cases

Before moving on, check that your program passes the following test cases:

1. `./a.out cat dog` prints output:
   ```
   3 arguments:
   [./a.out]
   [cat]
   [dog]
   ```
1. `./a.out a b c` prints output:
   ```
   4 arguments:
   [./a.out]
   [a]
   [b]
   [c]
   ```
1. `./a.out` prints output:
   ```
   1 arguments:
   [./a.out]
   ```

# `2-average`

This program will compute the average (mean) of its commandline arguments.
Your program should treat all of its arguments as `float` numbers, and print
output using the pattern
```
total is <TOTAL> and average is <AVG>
```
where `<TOTAL>` is the total (sum) of all the arguments, and `<AVG>` is the
average of them.

As you may recall, the average of a list of numbers is the sum of the numbers,
divided by the count of how many numbers are present.

Your program should validate that there is at least one
argument and print an error message when this is not the case.

**Hints:**
1. Remember that the first element of `arguments` is the command name
   `./a.out`, so your loop to compute the sum will need to skip the first
   element. This is explained in the *Loop Pattern: First Element is Special Case*
   slide.
1. There are multiple ways of getting the count of the numbers. One is
   to count them inside a loop. Another is to use `arguments.size()`, but
   don't forget that it includes the command name which is not a number.

## Test Cases

Before moving on, check that your program passes the following test cases:

1. `./a.out` prints
   ```
   error: you must supply at least one number
   ```
1. `./a.out 5 7` prints
   ```
   total is 12 and average is 6
   ```
1. `./a.out 101 13 19` prints
   ```
   total is 133 and average is 44.3333
   ```
1. `./a.out 0` prints
   ```
   total is 0 and average is 0
   ```
# `3-max`

This program performs an *optimization:* it finds the maximum of its arguments.
This process is explained in the *Loop Pattern: Optimization/Maximum* slide.

Your program should
1. Validate that there is at least one commandline argument; if not, print
   an error message and stop the program with an error exit code.
1. Treat all the arguments as `float` numbers, and find the maximum value
   among the arguments. Use the optimization/maximum pattern.
1. Print output using the pattern
   ```
   maximum is <MAX>
   ```
   where `<MAX>` is the largest of the numbers.

**Hint:** This loop will obviously involve the optimization pattern, but it will
also need to handle the first element differently, since the first element `./a.out`
is not a number and needs to be skipped.

## Test Cases

Before moving on, check that your program passes the following test cases:

1. `./a.out` prints
   ```
   error: you must supply at least one number
   ```
1. `./a.out 1 2 3` prints
   ```
   maximum is 3
   ```
1. `./a.out 3 2 1` prints
   ```
   maximum is 3
   ```
1. `./a.out 0` prints
   ```
   maximum is 0
   ```

# `4-phone`

The final program "sanitizes" a string that is intended to hold a phone number.
That means that your program will take a string that contains a 7-digit phone
number, possibly with non-digit characters like `"278-2011"` (a dash), validate
whether it contains the proper number of digits, and print only the digits
like `"2782011"`.

Your program should
1. Validate that there is exactly one commandline argument, and if not,
   print out an error message and stop the program with an error exit code.
1. Store the commandline argument in a `string` variable.
1. Use a loop to count the number of digits in a string.
   **Hint:** use the counting pattern, and the `isdigit` function.
1. If the number of digits is not 7, print an error message and stop the
   program with an error exit code.
1. Print output using the following pattern:
   ```
   phone number: <DIGITS>
   ```
   where digits is **only** the digit characters in the string. In other words,
   skip over all non-digit characters. **Hint:** Use the filtering pattern.

## Test Cases

Before moving on, check that your program passes the following test cases:

1. (missing argument) `./a.out` prints
   ```
   error: you must supply one argument
   ```
1. (too few digits) `./a.out 123` prints
   ```
   error: your phone number must have exactly 7 digits
   ```
1. (too many digits) `./a.out 12345678` prints
   ```
   error: your phone number must have exactly 7 digits
   ```
1. (skips dashes) `./a.out 123-4567` prints
   ```
   phone number: 1234567
   ```
1. (skips parenthesis and spaces) `./a.out "(765) 4321"` prints
   ```
   phone number: 7654321
   ```
   *(Note that you need to put quotes around this phone number, so that all
     of the characters count as one argument instead of two.)*

# Signing Out

When you are done, commit and push all your changes, then delete your local `lab-8-USERNAME` directory.

Then ask your instructor or lab assistant to sign you out. They will check that:
- The web-view of your GitHub repository reflects your recent commits.
- Your names are in `CREDITS.txt`.
- The contents of the four source files look like they would pass all the test cases.

# Grade Rubric

Your submission will be graded according to the following rubric.

- (3 points): You added both partners' names to `CREDITS.txt`.
- (3 points): You removed all the TODO comments from all the source files.
- (3 points): All source files compile cleanly.
- (3 points): `1-args` passes all of the test cases.
- (1 points): `1-args` uses a range-based for, and no other kinds of loop.
- (3 points): `2-average` passes all of the test cases.
- (1 points): `2-average` uses a range-based for, and no other kinds of loop.
- (3 points): `3-max` passes all of the test cases.
- (1 points): `3-max` uses a range-based for, and no other kinds of loop.
- (3 points): `4-phone` passes all of the test cases.
- (1 points): `4-phone` uses a range-based for, and no other kinds of loop.

# Deadline

This lab is assigned on March 11-13, and Due Friday March 20 at 11:59 pm.
