# pylintCheckerTask

## What is Pylint?
Pylint is a static code analyser for Python 2 or 3. The latest version supports Python 3.8.0 and above.

Pylint analyses your code without actually running it. It checks for errors, enforces a coding standard, looks for code smells, and can make suggestions about how the code could be refactored.

Here's the link to the official documentation: https://pylint.pycqa.org/en/latest/index.html

This project implements custom checkers for Pylint to enhance code quality analysis. It includes two checkers, each serving a specific purpose.

## 1. Too Long Function Name Checker
### Overview
The **Too Long Function Name Checker** is a straightforward checker designed to ensure function names do not exceed a specified length, which is set at 20 characters by default. Longer function names can be inconvenient for code maintainability. This checker will issue a warning when a function name exceeds this limit.

### Usage
Here's an example of how the checker works.
For a code like this:
```
def testing():
    test1=1
    return test1 

def testingtoolongnamefunction():
    test2=2
    return test2 
```
Here's the result:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/too_long_function_name_test.png)

The first function does not trigger a warning since its name is under 20 characters, while the second one triggers a warning due to its name exceeding 20 characters.

Feel free to adjust the maximum function name length parameter as needed.

## 2. Names To Avoid Checker
### Overview
The **Names To Avoid Checker** is a more complex checker that enforces a coding style rule outlined in PEP 8. This rule recommends avoiding single-character variable names that can be easily confused with certain characters in some fonts, such as 'l' (lowercase 'el'), 'O' (uppercase 'oh'), and 'I' (uppercase 'eye'). The checker helps ensure adherence to this rule.

### Usage
The rule from PEP 8 is as follows:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/PEP8_rule.png)

### Names to Avoid:
> Never use the characters ‘l’ (lowercase letter el), ‘O’ (uppercase letter oh), or ‘I’ (uppercase letter eye) as single-character variable names. In some fonts, these characters are indistinguishable from the numerals one and zero. When tempted to use ‘l’, use ‘L’ instead.

The **Names To Avoid Checker** is capable of checking variables in various contexts:

- Top-level variables
- Variables inside functions
- Variables inside classes
- Variables inside class methods

### Example
Here are some examples of how the checker operates:

- Checks variables inside a function:
```
def testing():
    I=4
    l=5
    O=6
    print(I)
    print(l)
    print(O)
    return True
```
Here's the result:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_inside_function.png)

- Checks variables at the top level and inside a function:
```
I=1

def testing():
   
    l=5
    print(l)
    O=6
    print(O)
    
    return True 
```
Here's the result:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_top_level_and_inside_function.png)

- Checks variables inside a class:
```
class MyClass:
    l = 42 
    O = 123  
    I = "example"  
```
Here's the result:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_inside_class.png)

- Checks variables inside a function in a class:
```
class MyClass:

    def __init__(self):
        self.l = 'l' 

    def method_with_assignment(self):
        self.O = 1 
```
Here's the result:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_inside_function_in_class.png)

- Checks all these variables together.
```
# Top-level variables
l = 1
O = 'hello'
I = 3.14

def test_function():
    # Variables within a function
    l = 'local_l'
    O = 42
    I = [1, 2, 3]

    class TestClass:
        # Variables within a class
        l = 'class_l'
        O = 3.0
        I = (4, 5, 6)

        def __init__(self):
            # Variables within a class method
            self.l = 'method_l'
            self.O = True
            self.I = {'key': 'value'}

    # Function body
    local_l = 123
    local_O = 'world'
    local_I = 2.71

test_instance = test_function()
```
Here's the result:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_all.png)


## Getting Started
To run Pylint with these custom checkers, export the PYTHONPATH to include the current project path:
```
export PYTHONPATH=../pylintCheckerTask/
echo $PYTHONPATH
```
You can find useful commands in the commands.txt file. Feel free to run the provided tests to verify the checker's functionality.
