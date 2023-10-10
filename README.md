# pylintCheckerTask

This project implements custom checkers for Pylint to enhance code quality analysis. It includes two checkers, each serving a specific purpose.

## 1. Too Long Function Name Checker
### Overview
The **Too Long Function Name Checker** is a straightforward checker designed to ensure function names do not exceed a specified length, which is set at 20 characters by default. Longer function names can be inconvenient for code maintainability. This checker will issue a warning when a function name exceeds this limit.

### Usage
Here's an example of how the checker works:

![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/too_long_function_name_test.png)

Feel free to adjust the maximum function name length parameter as needed.

## 2. Names To Avoid Checker
### Overview
The **Names To Avoid Checker** is a more complex checker that enforces a coding style rule outlined in PEP 8. This rule recommends avoiding single-character variable names that can be easily confused with certain characters in some fonts, such as 'l' (lowercase 'el'), 'O' (uppercase 'oh'), and 'I' (uppercase 'eye'). The checker helps ensure adherence to this rule.

### Usage
The rule from PEP 8 is as follows:

### Names to Avoid:
Never use the characters ‘l’ (lowercase letter el), ‘O’ (uppercase letter oh), or ‘I’ (uppercase letter eye) as single-character variable names. In some fonts, these characters are indistinguishable from the numerals one and zero. When tempted to use ‘l’, use ‘L’ instead.

![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/PEP8_rule.png)

The **Names To Avoid Checker** is capable of checking variables in various contexts:

- Top-level variables
- Variables inside functions
- Variables inside classes
- Variables inside class methods
- 
### Example
Here are some examples of how the checker operates:

- Checks variables inside a function:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_inside_function.png)

- Checks variables at the top level and inside a function:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_top_level_and_inside_function.png)

- Checks variables inside a class:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_inside_class.png)

- Checks variables inside a function in a class:
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_inside_function_in_class.png)

- Checks all these variables together.
![alt text](https://github.com/putongyong/pylintCheckerTask/blob/main/media/names_to_avoid_test_all.png)

Remember to configure the maximum length for function names in the "Too Long Function Name Checker" and ensure your code adheres to the PEP 8 rule for variable names.

## Getting Started
To run Pylint with these custom checkers, export the PYTHONPATH to include the current project path. You can find useful commands in the commands.txt file. Feel free to run the provided tests to verify the checker's functionality.

For any questions or issues, please don't hesitate to contact the project maintainers. We appreciate your contributions and feedback!
