# Introduction and fundamentals

Hello everyone and welcome to the first of ten episodes for my introductory course on C++. This course is going to be targeted towards beginners, with more advanced courses, as well as courses on other languages coming in the future. Let's get right into it.

Here's what you're going to learn in this episode:

- You're going to learn how to set up your IDE on Windows and on MacOS, and how to set up your build tools on Linux.
- You're going to learn how to make your first program that writes something on the screen.
- You're going to learn how to add comments to your code and how to ensure that your code always looks neat and easy to follow.

As always, feel free to skip ahead to any sections that interest you, there's all the time codes in the description, as well as links to all accompanying materials.

## 1. Setting up your IDE

Setting up your IDE is fairly easy on both Windows and MacOS.

For Windows users, you're gonna want to download Visual Studio Community either 2019 or the 2022 preview, follow the steps on screen for the installation, and just make sure to select the "Desktop development with C++" option.

For MacOS users, you're gonna want to download either Xcode 12 or the Xcode 13 beta from Apple's website.

The links to everything are in the description.

For Linux users, there are several different IDEs you can use, although most of them are outdated and pretty awful. CLion is a pretty popular IDE that also has a Linux version, however I would not recommend it to anyone unless you have a free license from your university, since otherwise you'll have to pay a $90 yearly subscription. I would recommend just using any editor you like (I prefer Sublime Text 4) and building your software using the command line utilities. How to install the build utilities depends on your particualr linux distribution, for Ubuntu the command is

```bash
apt install build-essential
```
while on Arch Linux it's

```bash
pacman -S base-devel
```

(both commands are to be ran as root). For every other Linux distribution, a quick Google search will help you find the appropriate command to install the build tools.

## 2. Your first program

Typically, the first program that any new developer makes when learning a new language is what's called a "hello world" It's a simple program that writes "Hello, world!" on the console output. We're gonna jump right into it, what you can see on the screen right now is the code for a simple "hello world" in C++. Don't worry about what everything does for now, I'll explain everything in time.

```c++
#include <iostream>

int main(int argc, const char* argv[]) {
    std::cout << "Hello, world!" << std::endl;
    return 0;
}
```

In the first line, we have an `#include` statement. We use the `#include` directive (hashtag include) to include code from other files.

This will be used for several things once you start making larger projects of your own but for this beginners' course we're only going to use it to access the C++ Standard Library (STL).

In this first example, we're including the `<iostream>` header, which contains all the functions and objects needed for basic input and output (reading user input and writing our program's output).

The next piece of code, at line 3, is the standard declaration of the **main** function. The main function is the start point for your code.

You need something that tells the computer what functions and what code to run in which order, this happens in the main function.

Don't worry too much about what everything in that line means in particular just yet, for now just try to remember it, but we'll go over what it all means in some of the next episodes when we talk about data types, variables and arrays.

The next important piece of the code is the curly bracket at the end of our function declaration. The purpose of curly brackets in C++ is to mark regions of code that belong together<sup>1</sup>. These regions of code are also called "scopes".

We're using the curly brackets here in this case to create a region of code which is the contents of our main function, in other words we're creating the region of code that will run when we run our program.

Lastly, we're left with the actual contents of our function. In C++ you use the `cout` object (`cout` stands for character output) to display an output to the user. You use the two lower-than symbols to forward data to cout, and lastly, `endl` is used to terminate a line and flush the output stream onto the screen (or in other words, `endl` indicates the line is finished and it's time to write everything onto the screen).

Finally, we're left with the `return 0;` line. The return instruction stops execution of the current function, and returns the given value. As for why we are returning 0, it is customary for software to return the value 0 from their main function when the software ran without errors, while any other value is used to indicate a failure.

Now that we're done explaining everything, we can try executing our code and seeing how it works. For our Windows and MacOS users, just write the code into a new source file and use the run button to execute your code. For the Linux users, first use the `g++` command to compile the code, and then execute it manually after you compiled it. We should now see "Hello, world!" on our screen, which indicates our software ran as intended!

## 3. Keeping your code clean

Now, as a last quick bit of information, I'm gonna tell you how to add comments to your code, and how to make sure your code stays clean and organized.

Comments are extra notes that you can add to your code to make it easier to understand, which are ignored by the compiler. In C++ you have two<sup>2</sup> ways to add comments. You have single line comments, which look like this:

```c++
// I am a single line comment, everything from the // to the end of the line is ignored by the compiler
```

and you have multi line comments, which can be as long as you want

```c++
/* I am a multi line comment, everything is ignored that is between the /* and */

/*
 * Multi line comments can be as long as you want, and you can stylize them and make them look quite neat.
 */
```

Lastly, the key to making your code clean is spacing and indentation. Make sure to leave space between large blocks of code, and don't let your lines get too long, as those can become hard to follow. Adding some line breaks and some empty lines for spacing can make your code much easier to read.

As for indentation, most modern IDEs already handle that for you. Just make sure to add an extra tab for every scope you create, and remove a tab for every scope you leave, this way it's always easy to keep track of what sections of code belong together.

So when in doubt, remember,

```c++
#include <iostream>

int main(int argc, const char* argv[]) {
    std::cout << "This is good!" << std::endl;
    return 0;
}
```

but

```c++
#include <iostream>

    int main(int argc, const char* argv[]) {
std::cout << "This is a mess!" << std::endl;
            return 0;}
```

# Exercises

Here's a few exercises to make sure you have a grip on everything we talked about in this episode!

1. Add comments to our original code to explain what every line (apart from the empty line) does.
2. Modify the code, so that it now writes "Hello, world!" three times, followed by a pun of your choice.

### Footnotes

<small>1: Curly brackets are not always used to create regions of code, they can also be used for initializer lists, and for declaring the values of arrays and structs.</small><br/>
<small>2: You can theoretically also use the `#if 0` directive to create comments.</small>
