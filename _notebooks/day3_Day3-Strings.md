---
layout: post
title:  Day3-strings
date:   2019-08-11
day: 3
---


# Strings 

What is a string?
How is it different from another data type (ex. int)?

## Basics 

Let's define a string and save it to a variable.



```python
a = "Woof"
```


```python
a = "Woof"
b = "Meow"
c = "Squirrel"
```

We can print the contents of a string in a simple and straightforward manner:


```python
print(a)
```

    Woof


Python strings can be written using ' or ", as long as they match.


```python
print('Hello')
print("Goodbye")
```

    Hello
    Goodbye


We can add two strings together (this process is commonly called *concatenation*).


```python
"Woof" + "Meow"
```




    'WoofMeow'



We can also do this with strings stored in variables.


```python
a = "Woof"
b = "Meow"
a + b
```




    'WoofMeow'



Can I use multiplication instead of addition? How about division?


```python
a * 5
```




    'WoofWoofWoofWoofWoof'



*Challenge*: Take the strings "Hello" and " World", and print the sum twice back-to-back.


```python
print(("Hello" + " World") * 2)

```

    Hello WorldHello World



```python
# First sum the two strings
my_string = "Hello" + " World"

# Print the new string twice by multiplying it times 2
print(my_string * 2)
```

    Hello WorldHello World


### Strings are basically lists

Yesterday, we learned about lists. Python sees strings as a list of characters. So, we can access characters in strings just like we do with elements in lists.


```python
c = "Squirrel"
c[1]
```




    'q'




```python
c[10]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-11-ea0c20b3b68b> in <module>
    ----> 1 c[10]
    

    IndexError: string index out of range


Just like in normal lists in Python, we also use negative indices.


```python
c[-1]
```




    'l'



*Challenge*: How would we find the sixth character of the string 'race car'?


```python
"race car"[6]
```




    'a'



What if I want to include some quotation marks in my string? If I write them as part of the string, Python gets confused:


```python
newstring0 = "And then I told her, "Well you better go catch it!""
```


      File "<ipython-input-14-10b748bdfde9>", line 1
        newstring0 = "And then I told her, "Well you better go catch it!""
                                               ^
    SyntaxError: invalid syntax



How can I fix this problem?? Hint: I have to tell Python somehow that I don't want this character to be special.


```python
newstring1 = "And then I told her, \"Well you better go catch it!\""  
print(newstring1)
```

    And then I told her, "Well you better go catch it!"



```python
newstring2 = "Here is\na new line"
print(newstring2)
```

    Here is
    a new line



```python
newstring3 = "Here is a\ttab" 
print(newstring3)
```

    Here is a	tab



```python
newstring4 = "And I put a backslash \\ into this string." 
print(newstring4)
```

    And I put a backslash \ into this string.


## Important Functions 

So what are some built-in things we can do with strings? Just like with lists, we can use the `len( )` function to find the length of the string.


```python
a = "Woof"
len(a)
```




    4




```python
c = "Squirrel"
len(c)
```




    8



We can remove the white space surrounding a string using a function called `strip()`.


```python
line = "     Lots of     spaces        "
print(line.strip() + ".")
print(line.lstrip() + ".")
print(line.rstrip() + ".")
```

    Lots of     spaces.
    Lots of     spaces        .
         Lots of     spaces.


We can also get rid of all the white space in a string and save each word into as a seperate element of a list using a function called `split( )`.


```python
line = "So     many    spaces               everywhere!"
new_list = line.split()
print(new_list) # note that this is a list of strings, not a string itself!
```

    ['So', 'many', 'spaces', 'everywhere!']


We can turn the new list of strings back into one big string.


```python
print(" ".join(new_list))
```

    So many spaces everywhere!


*Challenge*: Break the following sentence into individual words: "This is a boring sentence." Then print each word, one per line.


```python
s = "This is a boring sentence.".split()
for word in s:
    print(word)
```

    This
    is
    a
    boring
    sentence.


We can replace characters too!


```python
print("cat".replace("c","h"))
```

    hat


How do I get only the words out of this screen name?


```python
a = "harry_james_potter"
```


```python
a.split("_")
```




    ['harry', 'james', 'potter']



Oh but this is a name! We should really capitalize the first letter of each word.


```python
name_list = a.split("_")
for i, name in enumerate(name_list):
    name_list[i] = name.title()
    
print(name_list)
```

    ['Harry', 'James', 'Potter']


Similarly, we can change letters to upper and lower case with `.upper()` and `.lower()`.


```python
print('MY SHOUTY SENTENCE'.lower())

print('my shift key has broken'.upper())
```

    my shouty sentence
    MY SHIFT KEY HAS BROKEN


### Testing Strings

We can test if a character or even a string is inside another string using the "in" keyword.


```python
"a" in "car"
```




    True




```python
"cat" in "The cat is over there."
```




    True




```python
"cat" in "The quick brown fox jumped over the lazy dog's back."
```




    False



Note that the in keyword is case senstive.


```python
word = "Hello World"
```


```python
print(word.count('l')) 
```

    3



```python
print(word.find("H")) 
```

    0



```python
print(word.index("World")) 
```

    6



```python
"2334".isdigit()
```




    True




```python
print(word.isalnum())         # check if all char are alphanumeric 
print(word.isalpha())         # check if all char in the string are alphabetic
print(word.isdigit())         # test if all char in string are digits
print(word.istitle())         # test if string contains title words
print(word.isupper())         # test if string contains upper case
print(word.islower())         # test if string contains lower case
print(word.isspace())         # test if string contains spaces
print(word.endswith('d'))     # test if string endswith a d
print(word.startswith('H'))   # test if string startswith H
```

    False
    False
    False
    True
    False
    False
    False
    True
    True


### Python III: Return of the Slice

So how would we go about changing a letter in a string? Unfortunately we can't just use an equals sign as you would do for a list.


```python
my_string = "Hello World!"

my_string[0] = "h" # Let's try to change the H to an h
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-39-3a8e474667eb> in <module>
          1 my_string = "Hello World!"
          2 
    ----> 3 my_string[0] = "h" # Let's try to change the H to an h
    

    TypeError: 'str' object does not support item assignment


What happened here? Just like with tuples, strings are *immutable*, which means that we cannot change characters in a string once it has been created. So how would we do it? Instead of changing the letter in the existing string, we need to create a new string made up of the old string along with any modifications we make. We can achieve this through slicing.

Let's try changing the first letter again:


```python
my_string = "Hello World!"

new_string = "h" + my_string[1:]
print(new_string)
```

    hello World!


What if we want to change a letter in the middle of our string, say change the 'w' to a 'W'? For this we'd slice up to the letter we want to change, add in our changed letter, then add the slice from the letter after that up to the end. 


```python
new_string = my_string[:6] + 'w' + my_string[7:]
print(new_string)
```

    Hello world!


## Practice Problems 

Create a list containing some strings. Then add all of the strings together and print the result.


```python

```

Write some code that determines how many words are in a string. (Assume that the string is a sentence where words are all seperated by a space).


```python

```

Write some code that doubles every letter. For example, 'Help' would become 'HHeellpp'. Store the elongated string as a new string, and print it.


```python

```

Write some code that takes a string as input and prints the string, written in reverse. For example, if given the string 'coconut" the cell would print 'tunococ'.


```python

```

Write some code that inserts the character 'h' at a given location inside another string. For example, create an integer and initialize it to 5. Then insert 'h' after the 5th position of the string 'She sells seashells'.


```python

```

## Advanced Problems

*Numbers*: Write some code that determines if a string contains any number (any of the following: 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9) and returns True or False.


```python

```

*Vowels*: Write some code that determines the index (or indices) in a string of all the vowels. 


```python

```

*Palindrome*:  
From Wikipedia (https://en.wikipedia.org/wiki/Palindrome):  
A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. Allowances may be made for adjustments to capital letters, punctuation, and word dividers. Examples in English include 'A man, a plan, a canal, Panama!', 'Amor, Roma', 'race car', 'stack cats', 'step on no pets', 'taco cat', 'put it up', and 'Was it a car or a cat I saw?'.
  
Write some code that determines if a string is a palindrome. Make it case insensitive. Deal with punctuation as you choose (or not at all).


```python

```


```python

```
