

<!-- tabs:start -->

#### **Question:**

How to improve the following block of code?

```
li = []
for i in range(1, 10):
    li.append(i)
```
#### **Answer:**

```
[i for i in range(1, 10)]
```
<!-- tabs:end -->

<!-- tabs:start -->

#### **Question:**

Given the following function

```
def is_int(num):
    if isinstance(num, int):
        print('Yes')
    else:
        print('No')
```

What would be the result of is_int(2) and is_int(False)? 

#### **Answer:**

```
Yes
No
```
<!-- tabs:end -->


+ Can you implement a linked list in Python? +

  - The reason we need to implement in the first place, it's because a linked list isn't part of Python standard library.
  - To implement a linked list, we have to implement two structures: The linked list itself and a node which is used by the linked list.

  Let's start with a node. A node has some value (the data it holds) and a pointer to the next node

  ```
  class Node(object):
      def __init__(self, data):
          self.data = data
          self.next = None
  ```

  Now the linked list. An empty linked list has nothing but an empty head.

  ```
  class LinkedList(object):
      def __init__(self):
          self.head = None
  ```

  Now we can start using the linked list

  ```
  ll = Linkedlist()
  ll.head = Node(1)
  ll.head.next = Node(2)
  ll.head.next.next = Node(3)
  ```

  What we have is:

  ----       -----      ----
  | 1 | ->   | 2 |  ->  | 3 |
  ----       -----      -----

  Usually, more methods are implemented, like a push_head() method where you insert a node at the beginning of the linked list

  ```
  def push_head(self, value):
      new_node = Node(value)
      new_node.next = self.head
      self.head = new_node
  ```



+ Add a method to the Linked List class to traverse (print every node's data) the linked list +

    def print_list(self):
        node = self.head
        while(node):
            print(node.data)
            node = node.next



+ Write a method to that will return a boolean based on whether there is a loop in a linked list or not +

    Let's use the Floyd's Cycle-Finding algorithm:

    ```
    def loop_exists(self):
        one_step_p = self.head
        two_steps_p = self.head
        while(one_step_p and two_steps_p and two_steps_p.next):
            one_step_p = self.head.next
            two_step_p = self.head.next.next
            if (one_step_p == two_steps_p):
                return True 
        return False
    ```

+ Implement Stack in Python +

    ```
        stack = []
        
        # Push
        stack.append(1)
        stack.append(2)
        stack.append(3)

        # Pop
        stack.pop()
        stack.pop()

        # Peek
        stack[-1]
    ```

+ Write a Test to check whether the function returns string in Python? +

    ```
    def test_is_string():
        assert is_string('hello') == True
    ```

+ What is PEP8? Give an example of 3 style guidelines +

    PEP8 is a list of coding conventions and style guidelines for Python

    5 style guidelines:

        1. Limit all lines to a maximum of 79 characters.
        2. Surround top-level function and class definitions with two blank lines.
        3. Use commas when making a tuple of one element
        4. Use spaces (and not tabs) for indentation
        5. Use 4 spaces per indentation level


+ How to test if an exception was raised? +

    ```
    try:
        raise Exception('This is an exception')
    except Exception as e:
        print(e)
    ```

+ What ```assert``` does in Python? +

    ```assert``` is a built-in function in Python that checks if a condition is true. If it's not, it raises an exception.
    
    Syntax:
    ```
    assert expression, message
    ```

+ Explain mocks +

    ```
    import unittest
    from unittest.mock import Mock

    class TestClass(unittest.TestCase):
        def test_method(self):
            mock_method = Mock()
            mock_method.return_value = 'hello'
            assert mock_method() == 'hello'
    ```
    Here the mock_method is a mock object. It's a mock object because it doesn't have a real implementation.

+ How do you measure execution time of small code snippets? +

    ```
    import time
    start = time.time()
    # do something
    end = time.time()
    print(end - start)
    ```


+ Why one shouldn't use ```assert``` in non-test/production code? +

    ```assert``` is a built-in function in Python that checks if a condition is true. If it's not, it raises an exception.
    In non-test/production code, we should not use ```assert``` because it's a bad practice where we can't debug the code.

+ Can you describe what is Django/Flask and how you have used it? Why Flask and not Django? (or vice versa) +

    
    - Django and Flask are both web frameworks which are used to build web applications.
    - Prefer Flask because it's more lightweight and easier to maintain.
    - Prefer Django because it's more powerful and easier to maintain.
    
+ What is a route? +
  
    As every web framework, Flask provides a route functionality that lets you serve a content of a given URL.

    There are multiple ways to map a URL with a function in Python.

    - Decorator: you can use python decorators. In this case we're using `app`. This `app` decorator is the instance of the `Flask` class. And route it's a method of this class.

    ```
    @app.route('/')
    def home():
    return 'main website'
    ```

    - `add_url_rule` method: This is a method of the Flask class. We can also use it for map the URL with a function.

    ```
    def home():
      return 'main website'

    app.add_url_rule('/', view_func=home)
    ```

+ What is a blueprint in Flask? +

    A blueprint is a way to organize your application. It's a way to group your views and templates.

    ```
    from flask import Blueprint

    main = Blueprint('main', __name__)
    ```

    - `main` is the name of the blueprint.
    - `__name__` is the name of the module.


+ What is a template? +

    A template is a file that contains HTML code.

    ```
    <html>
      <head>
        <title>My title</title>
      </head>
      <body>
        <h1>My title</h1>
      </body>
    </html>
    ```

    - `<html>` is the root tag.
    - `<head>` is the head tag.
    - `<title>` is the title tag.
    - `<body>` is the body tag.
    - `<h1>` is the h1 tag.


+ Given ```x = [1, 2, 3]```, what is the result of list(zip(x))? +

    ```
    [(1,), (2,), (3,)]
    ```

<!-- tabs:start -->
#### **Question**

What is the result of each of the following:
    
1. list(zip(range(5), range(50), range(50)))
2. list(zip(range(5), range(50), range(-2)))

#### **Answers**
    
1. [(0, 0, 0), (1, 1, 1), (2, 2, 2), (3, 3, 3), (4, 4, 4)]
2. []

<!-- tabs:end -->


+ Explain Descriptors +

    Descriptors let objects customize attribute lookup, storage, and deletion.

    Example:
    ```
    class MyClass:
        def __init__(self):
            self.x = 'x'
            self.y = 'y'
            self.z = 'z'

        def __getattr__(self, name):
            if name == 'a':
                return 'a'
            else:
                raise AttributeError(name)

        def __setattr__(self, name, value):
            if name == 'a':
                raise AttributeError(name)
            else:
                super().__setattr__(name, value)

        def __delattr__(self, name):
            if name == 'a':
                raise AttributeError(name)
            else:
                super().__delattr__(name)
    ```

    - `__getattr__` is a method that is called when an attribute is not found.
    - `__setattr__` is a method that is called when an attribute is set.
    - `__delattr__` is a method that is called when an attribute is deleted.

    To use the desciptor given above, we can use the following code:
    ```
    >>>my_class = MyClass()
    >>>my_class.x
    'x'
    >>>my_class.y
    'y'
    ```


<!-- tabs:start -->

#### **Question**

What would be the result of running ```a.num2``` assuming the following code
```
class B:
    def __get__(self, obj, objtype=None):
        reuturn 10

class A:
    num1 = 2
    num2 = Five()
```
#### **Answers**
```10```
<!-- tabs:end -->


<!-- tabs:start -->

#### **Question**

What would be the result of running ```some_car = Car("Red", 4)``` assuming the following code 
```
class Print:

    def __get__(self, obj, objtype=None):
        value = obj._color
        print("Color was set to {}".format(valie))
        return value

    def __set__(self, obj, value):
        print("The color of the car is {}".format(value))
        obj._color = value

class Car:

    color = Print()

    def __ini__(self, color, age):
        self.color = color
        self.age = age
```

#### **Answer**
An instance of Car class will be created and the following will be printed: "The color of the car is Red"

<!-- tabs:end -->


+ How can you spawn multiple processes with Python? +

    ```
    import multiprocessing
    p = multiprocessing.Process(target=function, args=(args,))
    p.start()
    ```

+ Implement simple calculator for two numbers +

    ```
    def add(num1, num2):
        return num1 + num2

    def sub(num1, num2):
        return num1 - num2

    def mul(num1, num2):
        return num1*num2

    def div(num1, num2):
        return num1 / num2

    operators = {
        '+': add,
        '-': sub,
        '*': mul,
        '/': div
    }

    if __name__ == '__main__':
        operator = str(input("Operator: "))
        num1 = int(input("1st number: "))
        num2 = int(input("2nd number: "))
        print(operators[operator](num1, num2))

    ```



+ What data types are you familiar with that are not Python built-in types but still provided by modules which are part of the standard library? +

    Take a Peek - https://docs.python.org/3/library/datatypes.html

+ Explain what is a decorator +

    In python, everything is an object, even functions themselves. Therefore you could pass functions as arguments
    for another function eg;

    ```
    def wee(word):
        return word

    def oh(f):
        return f + "Ohh"

    >>> oh(wee("Wee"))
    <<< Wee Ohh
    ```

    This allows us to control the before execution of any given function and if we added another function as wrapper,
    (a function receiving another function that receives a function as parameter) we could also control the after execution.

    Sometimes we want to control the before-after execution of many functions and it would get tedious to write

    ``` f = function(function_1())```
    ``` f = function(function_1(function_2(*args)))```

    every time, that's what decorators do, they introduce syntax to write all of this on the go, using the keyword '@'.




+ Can you show how to write and use decorators? +

    ```
    These two decorators (ntimes and timer) are usually used to display decorators functionalities, you can find them in lots of
    tutorials/reviews. I first saw these examples two years ago in pyData 2017. https://www.youtube.com/watch?v=7lmCu8wz8ro&t=3731s```

    ```
    Simple decorator:

    def deco(f):
        print(f"Hi I am the {f.__name__}() function!")
        return f

    @deco
    def hello_world():
        return "Hi, I'm in!"

    a = hello_world()
    print(a)

    >>> Hi I am the hello_world() function!
        Hi, I'm in!
    ```

    This is the simplest decorator version, it basically saves us from writting ```a = deco(hello_world())```.
    But at this point we can only control the before execution, let's take on the after:

    ```
    def deco(f):
        def wrapper(*args, **kwargs):
            print("Rick Sanchez!")
            func = f(*args, **kwargs)
            print("I'm in!")
            return func
        return wrapper

    @deco
    def f(word):
        print(word)

    a = f("************")
    >>> Rick Sanchez!
        ************
        I'm in!
    ```

    deco receives a function -> f
    wrapper receives the arguments -> *args, **kwargs

    wrapper returns the function plus the arguments -> f(*args, **kwargs)
    deco returns wrapper.

    As you can see we conveniently do things before and after the execution of a given function.

    For example, we could write a decorator that calculates the execution time of a function.

    ```
    import time
    def deco(f):
        def wrapper(*args, **kwargs):
            before = time.time()
            func = f(*args, **kwargs)
            after = time.time()
            print(after-before)
            return func
        return wrapper

    @deco
    def f():
        time.sleep(2)
        print("************")

    a = f()
    >>> 2.0008859634399414
    ```

    Or create a decorator that executes a function n times.

    ```
    def n_times(n):
        def wrapper(f):
            def inner(*args, **kwargs):
                for _ in range(n):
                    func = f(*args, **kwargs)
                return func
            return inner
        return wrapper

    @n_times(4)
    def f():
        print("************")

    a = f()

    >>>************
    ************
    ************
    ************
    ```

+ Write a decorator that calculates the execution time of a function +

    ```
    import time
    def deco(f):
        def wrapper(*args, **kwargs):
            before = time.time()
            func = f(*args, **kwargs)
            after = time.time()
            print(after-before)
            return func
        return wrapper
    ```
   
+ Write a script which will determine if a given host is accessible on a given port +

    ```
    import socket
    import sys

    host = sys.argv[1]
    port = int(sys.argv[2])

    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.settimeout(1)
    try:
        s.connect((host, port))
        print("Port {} is open".format(port))
    except:
        print("Port {} is closed".format(port))
    s.close()
    ```


+ Are you familiar with Dataclasses? Can you explain what are they used for? +

    ```
    https://docs.python.org/3/library/dataclasses.html
    ```


+ You wrote a class to represent a car. How would you compare two cars instances if two cars are equal if they have the same model and color? +

    ```
    class Car:
        def __init__(self, model, color):
            self.model = model
            self.color = color

        def __eq__(self, other):
            if not isinstance(other, Car):
                return NotImplemented
            return self.model == other.model and self.color == other.color

    >> a = Car('model_1', 'red')
    >> b = Car('model_2', 'green')
    >> c = Car('model_1', 'red')
    >> a == b
    False
    >> a == c
    True
    ```

+ Explain Context Manager +

    - Context managers allow you to allocate and release resources precisely when you want to.
    - Context managers are used to wrap a block of code and ensure that it is properly cleaned up.
    - It consists of two parts:
        - A __enter__ method, which is called when the context is entered.
        - A __exit__ method, which is called when the context is exited.

    Example:
    ```
    class MyContextManager:
        def __enter__(self):
            print("Entering")
            return self

        def __exit__(self, exc_type, exc_val, exc_tb):
            print("Exiting")
    ```

+ Tell me everything you know about concurrency in Python +

    In Python, there are two main concurrency models:
    - Threads
    - Processes

    Threads are lightweight and fast where as processes are heavier and slower.

    Threads are used to execute a piece of code in parallel.
    Processes are used to execute a piece of code in parallel and are more powerful than threads.


+ Explain the Buffer Protocol +

    - The buffer protocol is a set of rules that must be followed by a class that implements the buffer protocol.
    - The buffer protocol defines the methods that a buffer must implement.
    - The buffer protocol is used to access the contents of a buffer as a sequence of bytes.
    - The buffer protocol is used to modify the contents of a buffer as a sequence of bytes.
    - The buffer protocol is used to create a view of a buffer.

    Example:
    ```
    class MyBuffer:
        def __init__(self, data):
            self.data = data

        def __len__(self):
            return len(self.data)

        def __getitem__(self, i):
            return self.data[i]

        def __setitem__(self, i, value):
            self.data[i] = value

        def __delitem__(self, i):
            del self.data[i]

        def __iter__(self):
            return iter(self.data)

        def __repr__(self):
            return repr(self.data)

        def __str__(self):
            return str(self.data)

        def __contains__(self, item):
            return item in self.data

        def __add__(self, other):
            return self.data + other

        def __iadd__(self, other):
            self.data += other
            return self

        def __mul__(self, other):
            return self.data * other

        def __imul__(self, other):
            self.data *= other
            return self

        def __rmul__(self, other):
            return self.data * other
    
    >> a = MyBuffer(b'Hello')
    >> len(a)
    5
    >> a[0]
    72
    >> a[0] = b'H'
    >> a
    b'Hello'
    >> del a[0]
    >> a
    b'ello'
    >> a + b' World'
    b'Hello World'


+ Do you have experience with web scraping? Can you describe what have you used and for what? +

    Yes, I have used web scraping for scraping data from websites.

    BeautifulSoup is a Python library that can be used to parse HTML and XML documents. Requests is a Python library that can be used to make HTTP requests.

    Example:
    ```
    import requests
    import bs4

    url = 'https://www.python.org/'
    response = requests.get(url)
    html = response.text
    soup = bs4.BeautifulSoup(html, 'html.parser')
    print(soup.title)
    print(soup.title.text)

    >> <title>The Python Programming Language</title>
    >> The Python Programming Language

    ```


+ Can you implement Linux's ```tail``` command in Python? Bonus: implement ```head``` as well +

    ```
    import os
    import sys

    def tail(f, n):
        with open(f) as f:
            f.seek(0, 2)
            lines = f.readlines()
            return lines[-n:]
    
    def head(f, n):
        with open(f) as f:
            f.seek(0)
            lines = f.readlines()
            return lines[:n]
    
    if __name__ == '__main__':
        if len(sys.argv) != 3:
            print('Usage: tail.py <file> <lines>')
            sys.exit(1)
        f = sys.argv[1]
        n = int(sys.argv[2])
        print(tail(f, n))
    ```

+ You have created a web page where a user can upload a document. But the function which reads the uploaded files, runs for a long time, based on the document size and user has to wait for the read operation to complete before he/she can continue using the web site. How can you overcome this? +

    - Use multiprocessing.Process to run the function in a separate process.
    - Otherwise, use threading.Thread to run the function in a separate thread.
    - We can also use the context manager with the multiprocessing.Pool to run the function in a separate process.

+ How yield works exactly? +

    Yield works by returning a generator object where the execution of the function is paused and resumed at a later time.