### Which module is required to run anything in C and how do u define variables & types & how to increment or decrement a variable?

- <stdio.h> is the library that contains all standard functions of c like printf,scanf and many more basic functions
- To define a variable we use ==datatype variable name==; data types can be i==nt,char,long int ,float==
- We can make a variable constant not allowing it to change because of code written elsewhere by adding `const` before defining variable like `const int i = 0`
- To increment a variable we can use 2,3methods like for example a variable called counter.Then to increment it by 1 we can do 
    
    ```C
    counter += 1;
    counter = counter + 1;
    counter++; \#Here no.of extra + tell how much to increment 
    ```
    

### How to give an input prompt and how to use them later to print the given inputs?

- First define a variable to store values in order to use it later and use scanf function to produce an input prompt .For example:
    
    ```C
    int x;
    int y;
    printf("What's the value of x: ");
    printf("What's the value of y:  ");
    scanf("%d %d",&x,&y);
    ```
    
      
    
- In scanf ==%d== → takes the input only in normal form 12,012,0x12 are same but ==%i== →accepts the numbers in normal,hexa,octal forms (12,012,0x12) are different here,==%c== → for characters, ==%li== ==&== ==%ld== → does same as i & d but for numbers larger than 2Billion,==%f== →for float numbers 
    
    ```C
    printf("The values u entered are %d and %d",x,y);
    ```
    
- In printf ==%d== → for signed integers ,==%i==→integers,==%c== → for characters,==%li== & ==%ld==→ for long integers,==%f== → for floating points(if you want ==x== decimals to be displayed use ==%.xf)==
- If you want to display decimal value upto n numbers use `printf(”%.nf”,number)`
- A problem with displaying more decimals in floating points is it becomes inaccurate after a certain point as it tries to give closest approximation this is called floating point imprecision. To solve this we use ==double== instead of ==float== ==just like long int for int. To use double in printf or scanf use== ==%lf  

### How does conditionals work in c ,how to define conditionals by boolean expression values & how to define same condition to work on two variables ?

- Do define a conditional we use if(for the first condition,else(for last condition) & else if for remaining all.And two define two variables for same condition use ==**||**== ==**t**====o represent or if compared to python.  
      
    ====**NOTE:In order to use boolean expression u need to import a library called**== ==**`stdbool.h`**== 
    
    ```C
    if (x<y|| y>x) \#Just to show the use case of || which represents or in python
    {
    printf("x is less than y");
    }
    else if (x>y)
    {
    printf("x is greater than y");
    }
    else
    {
    printf("x is equal to y");
    }
    ```
    
- While using boolean expressions they should be in ==( )==

  

### How do u define while , for loop & do while loop in C and what’s the difference in use case ?

- While loop is used when we have no idea about the iteration values but we know the [condition.It](http://condition.It) runs as long as the condition is [true.It](http://true.It) may not execute the code if the condition is false(not even once)
- For loop is a bit more complex featured loop as it gives us the ability to specify initial value, condition ,update all in one place
- Do while loop is similar to while loop but it executes the code at least once before it checks the condition
- **While Loop:**
    - Condition is checked before entering the loop.
    - May not execute the code block if the condition is initially false.
- **For Loop:**
    - Initialization, condition, and update expressions are all in one place.
        
        ```C
        for(initilization;condtion;update){
        code in loop]
        ```
        
    - Often used when you know the number of iterations in advance.
- **Do-While Loop:**
    - Condition is checked after executing the code block, ensuring the block is executed at least once.
    - It will do the thing mentioned in do if the while loop condition is satisfied
        
        ```C
        do
        {
        }
        while();
        ```
        

### How to convert data types in c and how to stop compiler taking enter shift as inputs?

- To convert a data type variable y to lets say float use `(float)y`
- `fflush(stdin);` ignores the standard input such as enter,shift,control,command….etc…

### How does running code works and what are the steps?

### preprocessing

- Preloads or just copy paste the code from header file to the current file

### compiling

converts source code to assembly code(2nd fastest language after binary code)

### assembling

The process of converting programming language to low level machine understandable language

### linking

links the present working file to header file which actually contains the functions(stdio.h)

### Data types storage values & how to define functions and how to define them beforehand at start?

- bool → 1 byte
- int → 2 bytes
- long int → 4 bytes
- float → 4 bytes
- double → 8 bytes
- char → 1 byte
- string → ? bytes
- to define a function before hand use `returndatatype functionname(parameters);`just to tell the compiler that this function is going to exist in later part of code
- syntax `returndatatype functionname(parameters){code}`

  

### What is an array & its syntax & how to get the ASCII code of a char using string as an array & how does indexing work in string of arrays?

- An array is a cluster of same data types like for example to store scores of students of an exam which all are integers
- syntax → `datatype name[size of array]`
- A string is an array of characters . So we can use array properties like indexing with string
- To get the ascii code for a char use `printf(”%i”,s[0])` where s is a string.
- To get to the 1st char of 1st string of array use `printf(”%d”,string[0][0]);`
- To define the elements of an array beforehand use `int array[] = {e1,e2…..,en};`

  

### How to calculate the length of a string and how to convert uppercase to lowercase ,vice versa & how to check the exit status of a program?

- There is null character at the end of string unlike array which is useful to calculate the length of string using a while loop
- Or u can use a `strlen()` function from `string.h` header file
- To convert lower case to upper case letter of a string use the condition to check if the entered letter is between ‘a’ and ‘z’ then ASCII code the difference in number between lower case & upper case is always `32.` subtract it from the lowercase number to get uppercase
    
    ```C
    for(int i = 0; i < strlen(s); i++)
    {
    if (s[i] >= 'a' && s[i] <= 'z')
    {
    printf("%c", s[i] - 32);
    ｝
    else
    ｛
    printf("%c", s[i]);
    }
    ｝
    printf("\n");
    ```
    
- Use `islower(),isupper(),tolower(),toupper()` from `ctype.h` library
- To check the exit status of program use `echo $?` that is to know what value the program is returning after it ends.And return 0 & 1 for different cases just for bit useful for command line arguments

  

### Why do we use void in int main(void) & what does it mean?

- The parameter in main function generally takes command line arguments that are to be executed while running the file using terminal like expecting an input from user after typing .`/a.out Pavan` here Pavan is taken as input and as we are not expecting any command line input we use void.
- It takes two parameters the general syntax is `int main(int argc,char argv[])` where `argc` stands for argument count as name suggests it counts the number of arguments passed before running the file and `argv` holds an array of arguments given by user

  

  

# Binary Digit (Bit)

### What’s a bit and base that computer use?

- A bit is a transistor that basically contains two possibilities of 0 and 1 or on and off

![[Screenshot_2023-08-09_at_8.47.45_PM.png]]

- The total number of possibilities or how many numbers computer has access to is $2^x$﻿ where x is number of bits
- 1Byte = 8bits

### Bit pattern ,Ascii code & RGB

- The numbers are read as  
    0-0  
    1-1  
    2-10  
    4-100  
    8-100  
    16-100 so on  
    64 - 100000  
    65 - 100001(This binary code represents capital A ,66 for B and so on)  
    
    ![[Screenshot_2023-08-09_at_8.55.18_PM.png]]
    
- Patterns are used in bits to represent different numbers with just 0 and 1
- ASCII is a 8 bit program with a capacity of 256 characters to express alphabets as numbers and unicode is the latest version of it with a 4 billion characters space available.
    
    ![[C basics/atttachments/Untitled.png]]
    
- In case of emojis to represent various skin tones, the creators came up with a pattern that the first set of numbers define the outline and followed by them are the skin tones colour.
- RGB represents how many out of 255 bits of each colour is used.

### Images,Video and Audio

- Images are simply collections of RGB values.
- Videos are sequences of many images that are stored together, just like a flipbook.
- Music can be represented through MIDI data.