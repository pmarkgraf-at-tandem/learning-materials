# Test Driven Development (TDD)

## Approach

* Never write code without a failing test
* Only write enough test to create a failure
* Only write enough code to make the test pass

## Details

* Make the smallest possible change
  * This is often code you know you will replace
  * Working in small increments helps you focus on the requirements and design
* Think of the tests as an examination of the requirements
* As the tests become more specific, code should become more generic
* Tests are as important as the code
  * Test should be clean and well-factored (just like the code!)

## Refactoring

* Refactoring is a disciplined technique for restructuring an existing body of code, altering its internal structure without changing its external behavior.
  * (Martin Fowler, from [refactoring.com](http://www.refactoring.com))
* Intersperse test creation with refactoring to keep the code clean

    ```mermaid
    flowchart LR
    green(Green <br> tests pass)
    red(Red <br> tests fail)

    green -- create a failing test --> red
    red -- make the failing test pass --> green
    green -- improve the code structure --> green
    ```

* Keep the code working throughout the refactoring
  * Do not delete code that will be replaced first
  * One approach is to:
    * duplicate the code to change,
    * make changes in the duplicated code
    * cut the usage from old version to new version
    * delete the old version
    * rename the new version to its ideal name
* Refactoring generally optimizes for readability
  * Readability can be improved by great names
  * Readability can be improved by small functions
  * Readability can be improved by maintaining a common level of abstraction within a given function

## end
