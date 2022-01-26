# Self Assessment
  >  “The secret to getting ahead is getting started.” - Mark Twain

+ Must Read +
  
  Read the Assessment *[or]* Try to Answer the Questions without Opening the Accordion.
  
+ What are some characteristics of the Python programming language? +

  - General Purpose Programming Language
  - Interpreted
  - Strongly Typed (i.e. type checking and type inference is enabled)
  - High Readability
  - Lot of libraries
  - Everything is object oriented

+ What built-in types Python has? +
  
  - Text Type:	str
  - Numeric Types:	int, float, complex
  - Sequence Types:	list, tuple, range
  - Mapping Type:	dict
  - Set Types:	set, frozenset
  - Boolean Type:	bool
  - Binary Types:	bytes, bytearray, memoryview

+ What are the Mutable and Immutable Datatypes? +

  1. Mutable:	List, Dictionary, Set
  2. Immutable:	String, Integer, Float, Boolean, None

+ What is Mutability? +
  
  - Mutability refers to the ability to change/modify the value of an object.
  - Mutable objects can be changed.
  - Immutable objects cannot be changed.

<!-- tabs:start -->
#### **Program**

```
1 > 2
'b' > 'a'
1 == 'one'
2 > 'one'
```

#### **Output**
```
False - One is not greater than two
True - Since 'b' is greater than 'a' in ASCII
False - 1 is a integer and 'one' is a string, since == checks for equality it does not throw an error
TypeError - Since 2 is a integer and 'one' is a string, since > checks for greater than it does not throw an error 
```
<!-- tabs:end -->

+ What is the result of `bool("")` and `bool(" ")` ? Explain +

  - `bool("")` is False
  - `bool(" ")` is True

+ Give Output: `[] is not []` +
  
  - `[] is not []` is True <br>
  `[]` is not `[]` because `[]` is not the same object as `[]` 

+ What is the result of running `True-True` ? +
  
  - `True-True` is `0`

+ String is an immutable data type in Python - True or False? +
  
  True

+ How to check if a string starts with a letter? +

  ```
  import re
  if re.match("^[a-zA-Z]+.*", string):
  ```

  string built-in:

  ```
  if string and string[0].isalpha():
  ```



+ How to check if all characters in a given string are digits? +

  `string.isdigit`



+ How to remove trailing slash ('/') from a string? +

  `string.rstrip('/')`


<!-- tabs:start -->
#### **Program**
What is the result of of each of the following?
- "abc"*3
- "abc"*2.5
- "abc"*2.0
- "abc"*True
- "abc"*False 

#### **Output**

- abcabcabc
- TypeError
- TypeError
- "abc"
- ""
<!-- tabs:end -->

<!-- tabs:start -->
#### **Program**
Improve the following code:

```
char = input("Insert a character: ")
if char == "a" or char == "o" or char == "e" or char =="u" or char == "i":
    print("It's a vowel!")
```
#### **Output**

```
char = input("Insert a character: ") # For readablity
if lower(char[0]) in "aieou": # Takes care of multiple characters and separate cases
    print("It's a vowel!")
```
*OR*
```
if lower(input("Insert a character: ")[0]) in "aieou": # Takes care of multiple characters and small/Capital cases
    print("It's a vowel!")
```
<!-- tabs:end -->


+ How to define a function with Python? +

  Using the `def` keyword. For Examples:

    ```
    def sum(a, b):
        return (a + b)
    ```
  

+ In Python, functions are first-class objects. What does it mean? +

  In general, first class objects in programming languages are objects which can be assigned to variable, used as a return value and can be used as arguments or parameters.<br>
  In python you can treat functions this way. Let's say we have the following function

  ```
  def my_function():
      return 5
  ```

  You can then assign a function to a variables like this `x = my_function` or you can return functions as return values like this `return my_function`



+ Write a function to determine if a number is a Palindrome +

  - Code:

  ```
  from typing import Union

  def isNumberPalindrome(number: Union[int, str]) -> bool:
      if isinstance(number, int):
          number = str(number)
      return number == number[::-1]

  print(isNumberPalindrome("12321"))
  ```

  - Using Python3.10 that accepts using bitwise operator '|'. 

  ```
  def isNumberPalindrome(number: int | str) -> bool:
      if isinstance(number, int):
          number = str(number)
      return number == number[::-1]

  print(isNumberPalindrome("12321"))
  ```

  Note: Using slicing to reverse a list could be slower than other options like `reversed` that return an iterator.

  - Result:

  ```
  True
  ```

<!-- tabs:start -->
#### **Program**

What is the result of the following block of code? 

```
x = ['a', 'b', 'c']
for i in x:
    if i == 'b':
        x = ['z', 'y']
    print(i)
```
#### **Output**

```
a
b
c
```
<!-- tabs:end -->


+ Explain inheritance and how to use it in Python +

  ```
  By definition inheritance is the mechanism where an object acts as a base of another object, retaining all its
  properties.

  So if Class B inherits from Class A, every characteristics from class A will be also available in class B.
  Class A would be the 'Base class' and B class would be the 'derived class'.

  This comes handy when you have several classes that share the same functionalities.

  The basic syntax is:

  class Base: pass

  class Derived(Base): pass

  A more forged example:

  class Animal:
      def __init__(self):
          print("and I'm alive!")

      def eat(self, food):
          print("ñom ñom ñom", food)

  class Human(Animal):
      def __init__(self, name):
          print('My name is ', name)
          super().__init__()

      def write_poem(self):
          print('Foo bar bar foo foo bar!')

  class Dog(Animal):
      def __init__(self, name):
          print('My name is', name)
          super().__init__()

      def bark(self):
          print('woof woof')

  michael = Human('Michael')
  michael.eat('Spam')
  michael.write_poem()

  bruno = Dog('Bruno')
  bruno.eat('bone')
  bruno.bark()

  >>> My name is  Michael
  >>> and I'm alive!
  >>> ñom ñom ñom Spam
  >>> Foo bar bar foo foo bar!
  >>> My name is Bruno
  >>> and I'm alive!
  >>> ñom ñom ñom bone
  >>> woof woof

  Calling super() calls the Base method, thus, calling super().__init__() we called the Animal __init__.

  There is a more advanced python feature called MetaClasses that aid the programmer to directly control class creation.
  ```


+ Explain and demonstrate class attributes & instance attributes +
  
  In the following block of code `x` is a class attribute while `self.y` is a instance attribute

  ```
  class MyClass(object):
      x = 1

      def __init__(self, y):
          self.y = y
  ```

+ What is an error? What is an exception? What types of exceptions are you familiar with? +

  ```
  #  Note that you generally don't need to know the compiling process but knowing where everything comes from
  #  and giving complete answers shows that you truly know what you are talking about.

  Generally, every compiling process have a two steps.
      - Analysis
      - Code Generation.

    Analysis can be broken into:
        1. Lexical analysis   (Tokenizes source code)
        2. Syntactic analysis (Check whether the tokens are legal or not, tldr, if syntax is correct)

              for i in 'foo'
                          ^
            SyntaxError: invalid syntax

        We missed ':'

      1. Semantic analysis  (Contextual analysis, legal syntax can still trigger errors, did you try to divide by 0,
        hash a mutable object or use an undeclared function?)

              1/0
              ZeroDivisionError: division by zero

      These three analysis steps are the responsible for error handlings.

      The second step would be responsible for errors, mostly syntax errors, the most common error.
      The third step would be responsible for Exceptions.

      As we have seen, Exceptions are semantic errors, there are many builtin Exceptions:

          ImportError
          ValueError
          KeyError
          FileNotFoundError
          IndentationError
          IndexError
          ...

      You can also have user defined Exceptions that have to inherit from the `Exception` class, directly or indirectly.

      Basic example:

      class DividedBy2Error(Exception):
          def __init__(self, message):
              self.message = message

      def division(dividend,divisor):
          if divisor == 2:
              raise DividedBy2Error('I dont want you to divide by 2!')
          return dividend / divisor

      division(100, 2)

      >>> __main__.DividedBy2Error: I dont want you to divide by 2!
  ```



+ Explain Exception Handling and how to use it in Python +

  **Exceptions:** Errors detected during execution are called Exceptions.

  **Handling Exception:** When an error occurs, or exception as we call it, Python will normally stop and generate an error message.</br>
  Exceptions can be handled using `try` and `except` statement in python.

  **Example:** Following example asks the user for input until a valid integer has been entered. </br>
  If user enter a non-integer value it will raise exception and using except it will catch that exception and ask the user to enter valid integer again.
    ```py
    while True:
        try:
            a = int(input("please enter an integer value: "))
            break
        except ValueError:
            print("Ops! Please enter a valid integer value.")

    ```
  For more details about errors and exceptions follow this [https://docs.python.org/3/tutorial/errors.html](https://docs.python.org/3/tutorial/errors.html)

<!-- tabs:start -->
#### **Program**
What is the result of running the following function?

```
def true_or_false():
    try:
        return True
    finally:
        return False
```
#### **Output**
False
<!-- tabs:end -->


<!-- tabs:start -->

#### **Question**
- Explain the following built-in functions (their purpose + use case example):
  * repr
  * any
  * all 

#### **Answer**

- repr:
  ```
  repr(object) -> string
  Return a string containing a printable representation of an object.
  ```
- any:
  ```
  any(iterable) -> bool
  Return True if bool(x) is True for any x in the iterable.
  ```
- all:
  ```
  all(iterable) -> bool
  Return True if bool(x) is True for all values x in the iterable.
  ```
<!-- tabs:end -->


+ What is the difference between repr function and str? +

  | repr | str |
  | ---- | --- |
  | Make Object Readable | Required code that reprdouces object |
  | Generate Output to end user | Generate output for developer |

  **Example**:
  ```
  >> import datetime
  >> now = datetime.datetime.now()
  >> str(now)
  '2022-01-26 11:06:33.927791'
  >> repr(now)
  'datetime.datetime(2022, 1, 26, 11, 6, 33, 927791)'
  ```

+ What is the \_\_call\_\_ method? +

  It is used to emulate callable objects. It allows a class instance to be called as a function.

  - Example code:

  ```
  class Foo:
      def __init__(self: object) ->  None:
          pass
      def __call__(self: object) -> None:
          print("Called!")

  f = Foo()
  f()
  ```

  - Result:

  ```
  Called!
  ```




+ Do classes has the \_\_call\_\_ method as well? What for? +

  \_\_class\_\_ method is used to write classes where the instances behave like functions and can be called.

  - Example code:
  **Program:**
  ```py
  class Foo:
      def __init__(self: object) ->  None:
          pass
      def __call__(self: object) -> None:
          print("Called!")
  f = Foo()
  f()
  ```
  **Output:**
  ```
  Called!
  ```

+ What _ is used for in Python? +

  1. Translation lookup in i18n
  2. Hold the result of the last executed expression or statement in the interactive interpreter.
  3. As a general purpose "throwaway" variable name. For example: x, y, _ = get_data() (x and y are used but since we don't care about third variable, we "threw it away").

+ What is GIL? +
  
  Python Global Interpreter Lock (GIL) is a type of process lock which is used by python whenever it deals with processes. Generally, Python only uses only one thread to execute the set of written statements. This means that in python only one thread will be executed at a time

+ What is Lambda? How is it used? +

  A ```lambda``` expression is an 'anonymous' function, the difference from a normal defined function using the keyword `def`` is the syntax and usage.

  The syntax is:

  ```lambda[parameters]: [expresion]```

  **Examples:**

  * A lambda function add 10 with any argument passed.

  ```py
  x = lambda a: a + 10
  print(x(10))
  ```

  * An addition function

  ```py
  addition = lambda x, y: x + y
  print(addition(10, 20))
  ```

  * Squaring function

  ```py
  square = lambda x : x ** 2
  print(square(5))
  ```
  Generally it is considered a bad practice under PEP 8 to assign a lambda expresion, they are meant to be used as parameters and inside of other defined functions.


+ Are there private variables in Python? How would you make an attribute of a class, private? +

  Yes, there are private variables in Python.

  - Example code:

  ```py
  class Foo:
      def __init__(self: object) ->  None:
          self.__private_variable = "private"
          self.public_variable = "public"
  f = Foo()
  print(f.__private_variable)
  print(f.public_variable)
  ```

  - Result:

  ```
  private
  public
  ```

+ Explain the following: getter, setter, deleter +
  - getter: Used to get the value of an attribute.
    ```
    def get_name(self):
        return self.__name
    ```
  - setter: Used to set the value of an attribute.
    ```
    def set_name(self, name):
        self.__name = name
    ```
  - deleter: Used to delete an attribute.
    ```
    def del_name(self):
        del self.__name
    ```
  
  In the above example, the getter and setter are used to get and set the value of the private variable. The deleter is used to delete the private variable. 


+ Explain what is @property +

  @property is a built-in decorator for the propery() function which is used to give special functionality to the certain methods to make them as getter, setter and deleter.

  - Example code:
  ```
  class Foo:
      def __init__(self: object) ->  None:
          self.__name = "Foo"
      @property
      def name(self):
          return self.__name
      @name.setter
      def name(self, name):
          self.__name = name
      @name.deleter
      def name(self):
          del self.__name
  f = Foo()
  print(f.name)
  f.name = "Bar"
  print(f.name)
  del f.name
  ```


+ How do you swap values between two variables? +
  
  ```
  x, y = y, x
  ```


<!-- tabs:start -->
#### **Question**
Explain the following object's magic variables:
  - \_\_dict\_\_
  - \_\_doc\_\_
  - \_\_module\_\_
  - \_\_name\_\_
  - \_\_class\_\_
  - \_\_bases\_\_
  - \_\_mro\_\_

#### **Answer**

  1. \_\_dict\_\_ is a dictionary or other mapping object used to store an object's (writable) attributes.
  
  2. \_\_doc\_\_ is a string containing the object's docstring.
  3. \_\_module\_\_ is for retrieving the module where the function was defined.
  4. \_\_name\_\_ is the name of the current object.
  5. \_\_class\_\_ is the class of the current object.
  6. \_\_bases\_\_ is a tuple containing the base classes of the current object.
  7. \_\_mro\_\_ is a tuple containing the method resolution order of the current object.

<!-- tabs:end -->


+ Write a function to return the sum of one or more numbers. The user will decide how many numbers to use +

  First you ask the user for the amount of numbers that will be use. Use a while loop that runs until amount_of_numbers becomes 0 through subtracting amount_of_numbers by one each loop. In the while loop you want ask the user for a number which will be added a variable each time the loop runs.

  ```
  def return_sum():
    amount_of_numbers = int(input("How many numbers? "))
    total_sum = 0
    while amount_of_numbers != 0:
      num = int(input("Input a number. "))
      total_sum += num
      amount_of_numbers -= 1
    return total_sum

  ```


+ Print the average of [2, 5, 6]. It should be rounded to 3 decimal places +

  ```
  li = [2, 5, 6]
  print("{0:.3f}".format(sum(li)/len(li)))
  ```

+ What is a tuple in Python? What is it used for? +

  A tuple is a built-in data type in Python. It's used for storing multiple items in a single variable.


+ List, like a tuple, is also used for storing multiple items. What is then, the difference between a tuple and a list? +

  List, as opposed to a tuple, is a mutable data type. It means we can modify it and at items to it.



+ How to add the number 2 to the list ```x = [1, 2, 3]``` +

  `x.append(2)`



+ How to check how many items a list contains? +

  `len(sone_list)`



+ How to get the last element of a list? +

  `some_list[-1]`



+ How to add the items of [1, 2, 3] to the list [4, 5, 6]? +
  
  x = [4, 5, 6]
  x.extend([1, 2, 3])

  Don't use `append` unless you would like the list as one item.



+ How to remove the first 3 items from a list? +

  `my_list[0:3] = []`



+ How do you get the maximum and minimum values from a list? +

  ```
  Maximum: max(some_list)
  Minimum: min(some_list)
  ```



+ How to get the top/biggest 3 items from a list? +

  ```
  sorted(some_list, reverse=True)[:3]
  ```

  Or

  ```
  some_list.sort(reverse=True)
  some_list[:3]
  ```

+ How to insert an item to the beginning of a list? What about two items? +
  - One item:

  ```
  numbers = [1, 2, 3, 4, 5]
  numbers.insert(0, 0)
  print(numbers)
  ```

  - Multiple items or list:

  ```
  numbers_1 = [2, 3, 4, 5]
  numbers_2 = [0, 1]
  numbers_1 = numbers_2 + numbers_1
  print(numbers_1)
  ```

+ How to sort list by the length of items? +

  ```
  sorted_li = sorted(li, key=len)
  ```

  Or without creating a new list:

  ```
  li.sort(key=len)
  ```



+ Do you know what is the difference between list.sort() and sorted(list)? +

  * sorted(list) will return a new list (original list doesn't change)
  * list.sort() will return None but the list is change in-place

  * sorted() works on any iterable (Dictionaries, Strings, ...)
  * list.sort() is faster than sorted(list) in case of Lists


+ Convert every string to an integer: ```[['1', '2', '3'], ['4', '5', '6']``` +

  ```
  nested_li = [['1', '2', '3'], ['4', '5', '6']]
  [[int(x) for x in li] for li in nested_li]
  ```



+ How to merge two sorted lists into one sorted list? +

  ```
  sorted(li1 + li2)
  ```

  Another way:

  ```
  i, j = 0
  merged_li = []

  while i < len(li1) and j < len(li2):
      if li1[i] < li2[j]:
          merged_li.append(li1[i])
          i += 1
      else:
          merged_li.append(li2[j])
          j += 1

  merged_li = merged_li + merged_li[i:] + merged_li[j:]
  ```



+ How to check if all the elements in a given lists are unique? so [1, 2, 3] is unique but [1, 1, 2, 3] is not unique because 1 exists twice +

  There are many ways of solving this problem:<br>
  ```# Note: :list and -> bool are just python typings, they are not needed for the correct execution of the algorithm. ```

  Taking advantage of sets and len:

  ```
  def is_unique(l:list) -> bool:
      return len(set(l)) == len(l)
  ```

  This one is can be seen used in other programming languages.

  ```
  def is_unique2(l:list) -> bool:
      seen = []

      for i in l:
          if i in seen:
              return False
          seen.append(i)
      return True
  ```

  Here we just count and make sure every element is just repeated once.

  ```
  def is_unique3(l:list) -> bool:
      for i in l:
          if l.count(i) > 1:
              return False
      return True
  ```

  This one might look more convulated but hey, one liners.

  ```
  def is_unique4(l:list) -> bool:
      return all(map(lambda x: l.count(x) < 2, l))
  ```

  + You have the following function

  ```
  def my_func(li = []):
      li.append("hmm")
      print(li)
  ```

  If we call it 3 times, what would be the result each call?
   +

  ```
  ['hmm']
  ['hmm', 'hmm']
  ['hmm', 'hmm', 'hmm']
  ```


+ How to iterate over a list? +

  ```
  for item in some_list:
      print(item)
  ```



+ How to iterate over a list with indexes? +

  ```
  for i, item in enumerate(some_list):
      print(i)
  ```

+ How to start list iteration from 2nd index? +

  Using range like this

  ```
  for i in range(1, len(some_list)):
      some_list[i]
  ```

  Another way is using slicing

  ```
  for i in some_list[1:]:
  ```



+ How to iterate over a list in reverse order? +

  Method 1
  ```
  for i in reversed(li):
      ...
  ```

  Method 2
  ```
  n = len(li) - 1
  while n > 0:
      ...
      n -= 1
  ```


+ Sort a list of lists by the second item of each nested list +

  ```
  li = [[1, 4], [2, 1], [3, 9], [4, 2], [4, 5]]

  sorted(li, key=lambda l: l[1])
  ```

  or

  ```
  li.sort(key=lambda l: l[1)
  ```



+ Combine [1, 2, 3] and ['x', 'y', 'z'] so the result is [(1, 'x'), (2, 'y'), (3, 'z')] +

  ```
  nums = [1, 2, 3]
  letters = ['x', 'y', 'z']

  list(zip(nums, letters))
  ```



+ What is List Comprehension? Is it better than a typical loop? Why? Can you demonstrate how to use it? +

  From [Docs](https://docs.python.org/3/tutorial/datastructures.html#list-comprehensions): "List comprehensions provide a concise way to create lists. Common applications are to make new lists where each element is the result of some operations applied to each member of another sequence or iterable, or to create a subsequence of those elements that satisfy a certain condition.".

  It's better because they're compact, faster and have better readability.

  - For loop:

  ```
  number_lists = [[1, 7, 3, 1], [13, 93, 23, 12], [123, 423, 456, 653, 124]]
  odd_numbers = []
  for number_list in number_lists:
      for number in number_list:
          if number % 2 == 0:
              odd_numbers.append(number)
  print(odd_numbers)
  ```

  - List comprehesion:

  ```
  number_lists = [[1, 7, 3, 1], [13, 93, 23, 12], [123, 423, 456, 653, 124]]
  odd_numbers = [number for number_list in number_lists for number in number_list if number % 2 == 0]
  print(odd_numbers)
  ```


  + You have the following list: ```[{'name': 'Mario', 'food': ['mushrooms', 'goombas']}, {'name': 'Luigi', 'food': ['mushrooms', 'turtles']}]```.Extract all type of foods. Final output should be: {'mushrooms', 'goombas', 'turtles'} +

  ```
  brothers_menu =  \
  [{'name': 'Mario', 'food': ['mushrooms', 'goombas']}, {'name': 'Luigi', 'food': ['mushrooms', 'turtles']}]

  # "Classic" Way
  def get_food(brothers_menu) -> set:
      temp = []

      for brother in brothers_menu:
          for food in brother['food']:
              temp.append(food)

      return set(temp)

  # One liner way (Using list comprehension)
  set([food for bro in x for food in bro['food']])
  ```

+ How to create a dictionary? +

  my_dict = dict(x=1, y=2)
  OR
  my_dict = {'x': 1, 'y': 2}
  OR
  my_dict = dict([('x', 1), ('y', 2)])

+ How to remove a key from a dictionary? +

  del my_dict['some_key']
  you can also use `my_dict.pop('some_key')` which returns the value of the key.

+ How to sort a dictionary by values? +

  ```
  {k: v for k, v in sorted(x.items(), key=lambda item: item[1])}
  ```



+ How to sort a dictionary by keys? +

  ```
  dict(sorted(some_dictionary.items()))
  ```

+ How to merge two dictionaries? +

  ```
  some_dict1.update(some_dict2)
  ```


+ Convert the string "a.b.c" to the dictionary ```{'a': {'b': {'c': 1}}}``` +

  ```
  output = {}
  string = "a.b.c"
  path = string.split('.')
  target = reduce(lambda d, k: d.setdefault(k, {}), path[:-1], output)
  target[path[-1]] = 1
  print(output)
  ```


+ Can you implement "binary search" in Python? +

  ```py
  def binary_search(lst,item) -> int:
      low = 0
      high = len(lst) - 1
      mid = (low + high) // 2

      while low <= high:
          if lst[mid] == item:
              return mid
          elif lst[mid] < item:
              low = mid + 1
          else:
              high = mid - 1
          mid = (low + high) // 2    
      return -1
  print(binary_search([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 5))
  ```

+ How to write to a file? +

  ```
  with open('file.txt', 'w') as file:
      file.write("My insightful comment")
  ```



+ How to print the 12th line of a file? +
  
  ```
  with open('file.txt', 'r') as file:
      for i, line in enumerate(file):
          if i == 11:
              print(line)
  ```

+ How to reverse a file? +
  
  ```
  with open('file.txt', 'r') as file:
      lines = file.readlines()
      lines.reverse()
      with open('file.txt', 'w') as file:
          file.writelines(lines)
  ```

+ Sum all the integers in a given file +
  
  ```
  with open('file.txt', 'r') as file:
      lines = file.readlines()
      sum = 0
      for line in lines:
          sum += int(line)
  ```

+ Print a random line of a given file +
  
  ```
  with open('file.txt', 'r') as file:
      lines = file.readlines()
      print(random.choice(lines))
  ```

+ Print every 3rd line of a given file +
  
  ```
  with open('file.txt', 'r') as file:
      lines = file.readlines()
      for i, line in enumerate(lines):
          if i % 3 == 0:
              print(line)
  ```

+ Print the number of lines in a given file +

  ```
  with open('file.txt', 'r') as file:
      lines = file.readlines()
      print(len(lines))
  ```

+ Print the number of of words in a given file +

  ```
  with open('file.txt', 'r') as file:
      lines = file.readlines()
      words = [line.split() for line in lines]
      print(len(words))
  ```


+ Can you write a function which will print all the files in a given directory? including sub-directories +

  ```
  def print_files(path):
      for root, dirs, files in os.walk(path):
          for file in files:
              print(os.path.join(root, file))
  ```

+ Write a dictionary (variable) to a file +

  ```
  import json

  with open('file.json', 'w') as f:
      f.write(json.dumps(dict_var))
  ```

+ How to print current working directory? +
  
  ```
    import os
    print(os.getcwd())
  ```


+ Given the path ```/dir1/dir2/file1``` print the file name (file1) +

  ```
    import os
    print(os.path.basename('/dir1/dir2/file1'))
    # Another way
    print(os.path.split('/dir1/dir2/file1')[1])
  ```

<!-- tabs:start -->

### **Question**

Given the path ```/dir1/dir2/file1```

  1. Print the path without the file name (/dir1/dir2)
  2. Print the name of the directory where the file resides (dir2)

### **Answer**

  ```
    import os

    ## Part 1.
    # os.path.dirname gives path removing the end component
    dirpath = os.path.dirname('/dir1/dir2/file1')
    print(dirpath)

    ## Part 2.
    print(os.path.basename(dirpath))
  ```

<!-- tabs:end -->


+ How do you execute shell commands using Python? +
  
    ```
    import subprocess
    subprocess.call(['ls', '-l'])
    ```


+ How do you join path components? for example ```/home``` and ```luig``` will result in ```/home/luigi``` +

  ```
  import os
  print(os.path.join('/home', 'luigi'))
  ```

+ How do you remove non-empty directory? +

  ```
  import os
  os.rmdir('/home/luigi')
  ```

+ How do you perform regular expressions related operations in Python? (match patterns, substitute strings, etc.) +

  - import re # Using re module

+ How to substitute the string "green" with "blue"? +

  ```
  import re
  string = "green is the color of the sky"
  pattern = re.compile("green")
  print(pattern.sub("blue", string))
  ```

+ How to find all the IP addresses in a variable? How to find them in a file? +

  ```
  import re
  string = "My IP address is 192.168.24.89 and my other IP address is 192.168.42.98"
  pattern = re.compile("\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}")
  print(pattern.findall(string))
  ```

+ Find the first repeated character in a string +

  While you iterate through the characters, store them in a dictionary and check for every character whether it's already in the dictionary.

  ```
  def firstRepeatedCharacter(str):
      chars = {}
      for ch in str:
          if ch in chars:
              return ch
          else:
              chars[ch] = 0
  ```

+ How to extract the unique characters from a string? for example given the input "itssssssameeeemarioooooo" the output will be "mrtisaoe" +

  ```
  x = "itssssssameeeemarioooooo"
  y = ''.join(set(x))
  ```

+ Find all the permutations of a given string +

  ```
  def permute_string(string):

      if len(string) == 1:
          return [string]

      permutations = []
      for i in range(len(string)):
          swaps = permute_string(string[:i] + string[(i+1):])
          for swap in swaps:
              permutations.append(string[i] + swap)

      return permutations

  print(permute_string("abc"))
  ```

  Short way (but probably not acceptable in interviews):

  ```
  from itertools import permutations

  [''.join(p) for p in permutations("abc")]
  ```

  Detailed answer can be found here: http://codingshell.com/python-all-string-permutations

+ How to check if a string contains a sub string? +

  ```
  def is_substring(string, sub_string):
      return sub_string in string
  ```
  
+ Find the frequency of each character in string +

  ```
  def frequency(string):
      freq = {}
      for ch in string:
          if ch in freq:
              freq[ch] += 1
          else:
              freq[ch] = 1
      return freq
  ```

+ Count the number of spaces in a string +

  ```
  def count_spaces(string):
      return string.count(' ')
  ```


+ Given a string, find the N most repeated words +

  ```
  def most_repeated_words(string, n):
      words = string.split()
      freq = {}
      for word in words:
          if word in freq:
              freq[word] += 1
          else:
              freq[word] = 1
      return sorted(freq, key=freq.get, reverse=True)[:n]
  ```

+ Given the string (which represents a matrix) "1 2 3\n4 5 6\n7 8 9" create rows and colums variables (should contain integers, not strings) +

  ```
  string = "1 2 3\n4 5 6\n7 8 9"
  rows = string.split('\n')
  cols = [row.split() for row in rows]
  print(rows)
  print(cols)
  ```

<!-- tabs:start -->

#### **Question**

What is the result of each of the following?

```
>> ', '.join(["One", "Two", "Three"])
>> " ".join("welladsadgadoneadsadga".split("adsadga")[:2])
>> "".join(["c", "t", "o", "a", "o", "q", "l"])[0::2]
```

#### **Answer**

```
>>> 'One, Two, Three'
>>> 'well done'
>>> 'cool'
```
<!-- tabs:end -->



+ If ```x = "pizza"```, what would be the result of ```x[::-1]```? +

  It will reverse the string, so x would be equal to `azzip`.



+ Reverse each word in a string (while keeping the order) +

  ```
  def reverse_words(string):
      words = string.split()
      return " ".join(reversed(words))
  ```


+ What is the output of the following code: ```"".join(["a", "h", "m", "a", "h", "a", "n", "q", "r", "l", "o", "i", "f", "o", "o"])[2::3]``` +

  'mario'

+ What is an iterator? +

  Iterator is an object that can be iterated upon, i.e. you can call ```next()``` on it.

  **Example:**
  ```
  >>> my_list = [1, 2, 3]
  >>> my_iterator = iter(my_list)
  >>> next(my_iterator)
  1
  >>> next(my_iterator)
  2
  ```

+ Explain data serialization and how do you perform it with Python +
  
  Pickle is a Python library that allows you to serialize and deserialize Python objects to and from a binary stream.


+ How do you handle argument parsing in Python? +

  In Python, you can use the ```argparse``` module to parse command line arguments.


+ What is a generator? Why using generators? +

  A generator is an object that produces one value at a time.

  **Example:**
  ```
  def my_generator():
      yield 1
      yield 2
      yield 3
  ```

<!-- tabs:start -->

#### **Question:**

What would be the output of the following block?

```
for i in range(3, 3):
  print(i)
```

#### **Answer:**

No output :)

<!-- tabs:end -->



+ What is ```yield```? When would you use it? +

  yield is a keyword used to return from a function and save the state of the function.

  Usage:
  ```
  def my_generator():
      yield 1
      yield 2
      yield 3
  ```
  when we want to iterate over the generator, we call ```next()``` on it and it will return the next value.


+ Explain the following types of methods and how to use them: Static method, Class method,Instance method +

  - Static Method is a method is defined inside a class and is called without creating an instance of the class.
  
  - Class method is a method is defined inside a class and is called without creating an instance of the class.

  - Instance method is a method is defined inside a class and is called by creating an instance of the class.

  **Example:**
  ```
  class MyClass:
      @staticmethod
      def my_static_method(self):
          print("I am a static method")
      @classmethod
      def my_class_method(cls):
          print("I am a class method")          
      def my_instance_method(self):
          print("I am an instance method")
  ```

+ Difference between Static and Class Method +
  
  | Static | Class|
  |--------|------|
  | Does not take any specific parameter | Takes the class as a parameter |
  | Can be called without creating an instance of the class | Can be called without creating an instance of the class |
  | @staticmethod | @classmethod |

+ How to reverse a list? +

  ```
  def reverse_list(list):
      return list[::-1]
  ```

+ How to combine list of strings into one string with spaces between the strings +

  ```
  def combine_list_of_strings(list):
      return " ".join(list)
  ```

+ You have the following list of nested lists: ```[['Mario', 90], ['Geralt', 82], ['Gordon', 88]]``` How to sort the list by the numbers in the nested lists?``` +

  One way is:
  the_list.sort(key=lambda x: x[1])

+ Explain the following: zip(), map(), filter() +
  
  | zip() | map() | filter() |
  |------|-------|----------|
  | Creates an iterator of tuples | Creates an iterator of the results of calling a function on each item of a given iterable | Creates an iterator of the results of applying a function that you specify to each item of a given iterable |

+ How do you debug Python code? +

  The module pdb defines a debugger that allows you to execute Python code step by step.

+ How to check how much time it took to execute a certain script or block of code? +

  ```
  import time
  start_time = time.time()
  # do something
  end_time = time.time()
  print(end_time - start_time)
  ```

+ What empty ```return``` returns? +

  Short answer is: It returns a None object.

  We could go a bit deeper and explain the difference between

  ```
  def a ():
      return

  >>> None
  ```

  And

  ```
  def a ():
      pass

  >>> None
  ```
  Or we could be asked this as a following question, since they both give the same result.

  We could use the dis module to see what's going on:

  ```
    2           0 LOAD_CONST               0 (<code object a at 0x0000029C4D3C2DB0, file "<dis>", line 2>)
                2 LOAD_CONST               1 ('a')
                4 MAKE_FUNCTION            0
                6 STORE_NAME               0 (a)

    5           8 LOAD_CONST               2 (<code object b at 0x0000029C4D3C2ED0, file "<dis>", line 5>)
              10 LOAD_CONST               3 ('b')
              12 MAKE_FUNCTION            0
              14 STORE_NAME               1 (b)
              16 LOAD_CONST               4 (None)
              18 RETURN_VALUE

  Disassembly of <code object a at 0x0000029C4D3C2DB0, file "<dis>", line 2>:
    3           0 LOAD_CONST               0 (None)
                2 RETURN_VALUE

  Disassembly of <code object b at 0x0000029C4D3C2ED0, file "<dis>", line 5>:
    6           0 LOAD_CONST               0 (None)
                2 RETURN_VALUE
  ```

  An empty ``` return``` is exactly the same as ```return None``` and functions without any explicit return
  will always return None regardless of the operations, therefore

  ```
  def sum(a, b):
      global c
      c = a + b

  >>> None
  ```

[Continue Assessment ➡️](programming/assessment-2)