---
layout: post
title: "Writing a MakeFile"
published: true
comments: true
categories: Tech
---

Understanding the concept of Libraries is important if you have to deal with C or C++ code on a daily basis. For me, since these days I am working with OpenVX specification and taking the Operating Systems class, it has become an absolute necessity. 

A good place to look at: <http://www.thegeekstuff.com/2010/08/ar-command-examples/>. 
It has good general things that you might want to look up. I will try to build up on his post.

We have two C files

#### addition.c

```C
int addition(int x, int y)
{
	return x+y;
}
```

#### multiplication.c

```C
int multiplication(int x, int y)
{
	return x*y;
}
```

You must remember that you cannot generate the executables using gcc for any of the two files. gcc complains that it could not find the ```main()``` function.

```sh
$ gcc addition.c
(.text+0x20): undefined reference to 'main'
collect2: error: ld returned 1 exit status
```

But what you can do is, just compile it and create the object files. 

```sh
$ gcc -c addition.c
$ gcc -c multiplication.c
$ ls
addition.c addition.o multiplication.c multiplication.o
```

Let's say we define our main() function in the file main.c somewhere else.

```C
#include<stdio.h>
int main()
{   
    int i,j;
    i=5;
    j=6;

    printf("%d \n", addition(i, j));
    printf("%d \n", multiplication(i, j));
}
```

We see that  "main.c" has dependency on the ```addition()``` and the ```multiplication()``` function. Since our program is small, we can do the following:

```sh
$ gcc main.c multiplication.o addition.o -o result
$ ./result
11
30
```

Suppose that the ```addition()``` and ```multiplication()``` functions are the only way to multiply or add two integers. So this means, any function that has to add or multiply two integers _needs_ our functions. So in other words we have to meet our need by _linking_ to those files which has the requisite functions that we need.

Assume you are the most genius person alive and everybody wants to use the functions written by you. So to prove that, you wrote two more functions ```subtraction()``` and ```division()``` in two different files namely "subtraction.c" and "division.c"

#### subtraction.c

```C
int subtraction(int x, int y)
{
	return x-y;
}
```

#### division.c

```C
int division(int x, int y)
{
	return x/y;
}
```

You generated their object files respectively.

```sh
$ gcc -c subtraction.c division.c
$ ls 
addition.c addition.o division.c division.o main.c multiplication.c multiplication.o subtraction.c subtraction.o result   
```

And now we have a new ```main()``` function that uses all of them. Like this:

```C
#include<stdio.h>
int main()
{   
    int i,j;
    i=5;
    j=6;

    printf("%d \n", addition(i, j));
    printf("%d \n", multiplication(i, j));
 	printf("%d \n", division(i, j));
    printf("%d \n", subtraction(i, j));
       
}
```
To run the `main()` we have do what we did previously

```sh
$ gcc main.c multiplication.o addition.o subtraction.o division.o -o result
$ ./result
11
30
0
-1
```

This is getting awkward really really fast, isn't it! Since we know that these files implement arithmetic operation, won't it be better to **somehow group them together. This is where the role of static libraries chip in.** We _archive_ all the four object files into one file called the `"libarithmetic.a"` also known as a static library . This archiving is nothing but a grouping of the object files just like we use tar in linux or zip in windows. (except few tiny but important details which I will go on in later.)

Let's see how can we archive it using the built in `"ar"` command .
