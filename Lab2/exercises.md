# Exercises (Modify this file)

Answer and complete the following exercises.

## Python Standard Library

1. How you name functions and member functions matter. Take a look at the [dictionary](https://docs.python.org/3/library/stdtypes.html#typesmapping) 
and [list](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range) member functions in the SL. 
Do the names of the member functions correlate to what they do? That is, are they good 'verbs' where the name of the function describes the action the code is doing? A good example would be a function called 'pop' which only removes one element. A bad example would be a function called 'pop' where one element is removed **and** that value is returned. A better name would be 'popAndGet' or 'popAndReturn', which captures the two events happening.

*Edit your responses here*
Yes, most names of the member functions correlate to what they do, except for 'pop', however, 'popAndGet' or 'popAndReturn' is too long to use in coding. So 'pop' is still acceptable.

2. How does a dictionary differ from a list? (i.e. What is the underlying data structure of each container.)

*Edit your response here*
dictionary: underlying data structure is a hash table; unordered; k-v pair; access by key
list: underlying data structure is a dynamic array; order collections; not k-v pair; access by index

3. Does a list allow for random access? Meaning can I access any element(e.g. myList[7])?

*Edit your response here*
Yes, as long as the length of your list is more than 7

4. Observe that all the container data structures (i.e. list, set, dictionary, etc.) can work with any data type (integers, floats, custom data types, etc.). 
What do you think are the pros/cons of a library that can work with any data type?

*Edit your response here*
pros: don't need to create separate data structures for each data type; A function written for a generic data type can be used in many different scenarios; quicker to develop; easier to understand 
cons: can introduce errors if the code assumes certain operations will always succeed; hard to debug; understanding generic programming concepts is also harder

## requests

1. Take a look at the requests API documentation here: https://requests.readthedocs.io/en/latest/  
Comment if the functions are well named in the Requests module (Follow the previous link to the documentation to see if you can find the Requests module (hint: look for API Reference)).

*Edit your responses here*
Yes,  "request" is straightforward and describes the action it performs – making an HTTP request. Functions like "head", "get", "post", "put", "patch". "delete", exceptions and sessions all well named and showed their actual abilities.

2. Take a look at the [Requests](https://requests.readthedocs.io/en/latest/api/#lower-level-classes) class. APIs that have more than say 5 arguments in a function can be confusing or error prone to use. This is a heuristic of course, but do you see any member functions that include lots of arguments?

*Edit your responses here*
Yes, I can give an example: def create_user(name, age, email, address, phone, gender, username).

3. Take another look at the Requests class. Note that many of the methods includes `**kwargs` as an argument. What is `**kwargs`? Why might it be good for a method to have a `**kwargs` argument? Why might it be bad?  

*Edit your responses here*
kwargs stands for "keyword arguments". When you use **kwargs in a function signature, it allows that function to accept any number of keyword arguments that aren't explicitly defined in the function's signature.

Why might it be good: 1can add new keyword arguments without modifying the function or method signature, which can be especially useful in library code that might be extended or overridden; 2when designing APIs that might have many optional parameters, rather than listing them all out, we can capture them all with **kwargs.

Why might it be bad:   1reduced clarity and readability; 2if we decide to take an argument out of **kwargs and make it explicit, it can be challenging to refactor; 3easier to make mistakes, such as misspelling

4. Take a look at the [Session class.] (https://requests.readthedocs.io/en/latest/api/#request-sessions) Not only can you read the API's for that class, you can also view the source code by clicking the 'source' text. 
Notice how some methods have arguments that are set to `None` while other arguments are not set to anything. Why is that? Can arguments be set to anything besides `None`? Why might it be good to set an argument by some predetermined value?


*Edit your responses here*
Why: If an argument in a function definition is assigned a default value (e.g., None), it becomes an optional parameter when calling the function. If there's no default value provided, then it is a required argument, and the caller must provide a value for it.
Arguments can be set to anything besides `None`, could be a number, string, list, dictionary, or even complex objects
Why might it be good to set an argument by some predetermined value: 1.If there's a common value that many users would use, it makes sense to set that as the default 2 we can give an implicit hint about the expected type or nature of the argument. 3  having a default value prevents errors that would arise if the argument was omitted.