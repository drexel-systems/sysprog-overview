## C Programming Style

#### Introduction
As somebody who has worked as and with software engineers for years the topic of a rigorous and *correct* programming style has always eluded me.

Is programming style important?  In my opinion yes, but there are some caveats that I want to share in this writeup.


#### Style of Code
Topics around how to name variables - should they be concise, long and descriptive, underscore delimited, camel case, where curly-braces go, and many other decisions around how to style code are often debated in the software engineering circles.  Below I will share my opinions (correct or incorrect)

1. **A codebase should have a consistent style**.  One of my bugaboos is looking at a body of code and seeing massive inconsistencies in coding conventions.  I personally am less concerned about a **correct** or debating a **better** style than seeing a consistent style across a codebase.  Thus, if you are working on a body of code by yourself, my view is that consistency is the most important thing.  If you are working in a team, then getting team consensus on coding conventions.

2. **Concise is better than verbose in most situations**.  IMO, Concise code is easier to read and easier to understand.  Having variables with names often used in languages like Python, for example `pointer_to_head_of_buffer` can often be replaced with things like `buff_ptr` to improve the readability of code.  Also, having to scroll right on code is a massive turn off.  If a line of code cannot fit within 60-80 characters it's normally a red flag.

3.  **On initializing variables**.  Some software engineers have strong opinions on if variable declaration should be independent of variable initialization.  For example, which one do you think is better:

    ```c
    void my_fun(){
        int x;

        x = 5;
    }
    ```
    versus

    ```c
    void my_fun(){
        int x = 5;
    }
    ```
The first example treats variable initialization and creation as separate activities.  There is merit to this approach; however, it can also be error prone.  I personally favor the second approach where it is very clear that not only am I intending to create a variable, but I want its initial value defined as well.

4   **Useless and "over" documentation**.  Somewhere in teaching programming history some educators started instilling in students that every line of code needs to be documented.  IMO, this is a ridiculous and counter-productive practice. This makes the code much harder to read.  Also, documentation is often not maintained and updated as code is maintained.  This results in useless and confusing artifacts being left in the source code.  My advice on this is to first assume that anybody reading your code understands the programming language, and whenever possible writing clear code that is **self documenting**.  Consider the following example:

    ```c
    int my_strlen(char *str){
        int l = 0;
        while (!*(str+l)){
            l++;
        }
        return l;
    }
    ```
    versus

    ```c
    int my_strlen(char *str){
        int l = 0;
        while (*(str+l) != '\0'){
            l++;
        }
        return l;
    }
    ```

The second version seems much easier to read, the first version should have a comment on the loop body to explain what is going on.

My advice is to use block comments to explain the intent of code where appropriate/necessary and then write clear versus clever code. Please never do this as it gets me annoyed:

    ```c
    int i = 0;      //define variable i
    i++;            //increment i

    //make sure i doesn't go over limit
    if (i < SOME_DEFINED_CONSTANT)
    ```

These comments are obvious and distracting.

5.  **Defining Pointer Types**.  C is somewhat forgiving in the way pointer types can be defined.  Consider the two examples below on defining a pointer to an integer variable:

    ```c
    int* i;
    ```
    versus

    ```c
    int *i;
    ```

Both do exactly the same thing.  I personally find the second approach better becuase in my mind it makes it clear that `i` is a pointer, and that when I put a `*` in front of it (aka `*i` I get a value that is of type `int`).  Some would argue the first approach is better because it kind of reads that the type is `int pointer`.  As I mentioned above, I have a personal preference for the second way, but highly recommend that you pick what works for you and be consistent. 

#### Conclusions
This document is a work in progress, if you have any suggestions for improvements, feel free to contribute an issue to this repo with suggestions and I will add them in as appropriate. 