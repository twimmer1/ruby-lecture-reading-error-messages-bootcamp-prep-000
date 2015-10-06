# Intro to Reading Ruby Error Messages

## Overview

In this lab, you'll be reading error messages from tests. This lab is designed so that both running the files *and* running the test suite via the `learn` command will show the error messages for you to decode. Moving forward though, you'll be reading error messages mainly through running the test suite.

Get started by opening this lab with `learn open` so you can follow along with the video and solve this lab.

## Objectives

1. Read the three different parts of an errors message.
2. Identify four error types- name errors, syntax errors, types errors, and division errors- and fix them
3. Describe a test suite, where it's found in a lab, and its purpose
4. Use the `learn` command in terminal to run the tests for a lab.

## Video

<iframe width="960" height="720" src="https://www.youtube.com/embed/L_eoziYKLXw?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

[Download MP4]([MP4](http://flatiron-videos.s3.amazonaws.com/ironboard/ruby/ruby-lecture-reading-error-messages/ruby-lecture-reading-error-messages.mp4))

## Reading Error Messages

Error messages have 3 parts:

```
lib/a_name_error.rb:3:in `<main>': undefined local variable or method `hello_world' for main:Object (NameError)
```

1) The location of the error, the "where".

```
lib/a_name_error.rb:3:in `<main>':
```

* `lib/a_name_error.rb` is the file the error occurred in.
* `3` is the line of code the error.
* `<main>` is the scope of the error.

2) The description, the "why".

```
undefined local variable or method `hello_world' for main:Object
```

The interpreter does the best job it can to tell you what it thinks went wrong.

3) The type of error, the "who".

```
(NameError)
```

This is a [Ruby Error Type](http://www.ruby-doc.org/core-2.2.0/Exception.html)

You've solved games of *Clue* with less information. This is my favorite part of programming, debugging, fixing errors. It's like you're a detective solving a crime. The only bad thing is that more often than not, you're also the criminal that caused the error in the first place.

Errors are clues, reading them is the interpreter telling you what to do to fix the program and move on.

## Four Common Error Types

### Name Errors
NameErrors are caused when a given name is invalid or undefined. Whenever the Ruby interpreter encounters a word it doesn't recognize, it assumes that word is the name of a variable or a method. If that word was never defined as either a variable or a method, it will result in a name error.

### Syntax Errors
Syntax errors are pretty self explanatory: they're the result of incorrect syntax. Thankfully, they're usually followed by a guess about the location of the error. For instance:

```ruby
2.times do
  puts "hi"
```

Will result in:
```text
2: syntax error, unexpected end-of-input, expecting keyword_end
```
Here, Ruby is saying that on line 2, there is a missing `end` (every `do` keyword must be followed by some code and then an `end` keyword). Always read the full details of syntax errors and look for line numbers, which usually appear at the beginning of the error message.

### TypeErrors

When you try and do a mathematical operation on two objects of a different type, you will receive a TypeError.  For example if you try and add a string to an integer, Ruby will complain.

```ruby
1 + "1"
```
Will produce the following error:

```
TypeError: String can't be coerced into Fixnum
```

### DivisionErrors
DivisionErrors are caused when a given number is divided by 0.

## What is a Test Suite?

The tests for each lab will be found inside the `spec` directory of that lab. Tests are programs, written using the RSpec testing library, that are written to make sure your program is running properly. Generally, tests will call on the methods you define in your programs and check to see if they are working the way they are expected to.

In the future, you will learn how to read tests more thoroughly and even how to write your own tests. For now, all you need to understand is that the code in the `spec` directory is there to test the code in your program. When you run the `learn` or the `rspec` command in your terminal in the directory of the lab you are working on, the runs the code in your `spec` file and tests your program. The output that appears in your terminal is the result of running those tests. If you pass a test, the output will generally appear green, otherwise, it will appear red and be accompanied by the types of error messages that we're discussing in this Readme. Paying attention to those error messages will help you to pass the test.


## Instructions

STOP. If you haven't watched the above video, you are making life much harder for yourself! Watch the video lecture above before attempting this lab : )

Did you watch it? Okay, great. Let's proceed. The point of this lab is to get you comfortable reading error messages and fixing simple programs.

1. Open this lab with `learn open`.

2. Run each of the files in the `lib` directory using the `ruby` command.

  * From the lab directory, try: `ruby lib/a_division_by_zero_error.rb` to run that program. You should get output about an error in the program. Read the error message and open that file in Sublime and see if you can fix the error. When the error is fixed and you run the file via `ruby`, you'll simply see no output at all, no errors or anything. Confirm this by running the `learn` command and seeing that you have a passing test and 3 remaining failures.

  * Run each file via `ruby lib/<file name>`, fix the errors, and confirm with `learn` until you're done and all the tests pass. Pay attention to the filenames in `lib` if you need hints for what kind of error to look for.

3. Once your code is passing with the `learn` command, submit the lab with `learn submit`

Feel proud, being able to read an error message and fix it, no matter how basic, is a huge step in being a programmer. Get comfortable with broken code, it's totally normal in programming.
