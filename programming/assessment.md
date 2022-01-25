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