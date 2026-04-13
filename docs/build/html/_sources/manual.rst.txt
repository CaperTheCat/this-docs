[This] Manual
==============================

[This] isn't *fully* complete yet, but that doesn't mean you can't make cool stuff with it.
(It's Turing complete, at least.)

Anyways, this manual should explain basically everything for you.

The Standard Library
-----------------------------
[This] features a small Standard Library, containing modules that can be imported from anywhere via ``import``. 
There is also a collection of functions which do not need to be imported and are available from anywhere.

std
^^^^^^^^^
Functions that are always avaialable and do not have to be imported.

assert()
~~~~~~~~~~~~~~~

.. code-block:: none

    assert(expression: bool) -> void

It will raise an error if the expression given evaluates to false, or nothing at all if it is true.

Here is it used in practice:

.. code-block:: none

    assert(1 == 0) // 1 is never equal to 0, so this will raise an error.


From here are modules in the Standard Library that must be imported via ``import`` for their functions to be used:

io
^^^^
Used for input/output.

io.print(...)
~~~~~~~~~~~~~~~~~
Fully defined as:

.. code-block:: none

    io.print(... : any) -> void

``io.print()`` will print all of its arguments to stdout.
It will print its arguments exactly as they appear and won't add a newline at the end.
If you are looking for a function that does that reliably, refer to ``io.println()``.

Here is it used in practice:

.. code-block:: none

    import io

    io.print("Hello, ", "World! I can handle many types; check out this ", 5, ".")

io.println(...)
~~~~~~~~~~~~~~~~~
Fully defined as:

.. code-block:: none

    io.println(... : any) -> void

``io.print()`` will print all of its arguments to stdout, then apply a newline at the end.
It will print its arguments exactly as they appear.
If you're looking for a function that won't apply that newline, refer to ``io.print()`` instead.

Here is it used in practice:

.. code-block:: none

    import io

    io.println("Hello, ", "World! I can handle many types; check out this ", 5, ".")
    io.println("I didn't need a newline up there. Thanks println!")

io.input()
~~~~~~~~~~~~~~~~~
Fully defined as:

.. code-block:: none

    io.input() -> string

``io.input()`` will open up for input, returning everything inputted until the newline (when the user clicks enter).

Here is it used in practice:

.. code-block:: none

    import io

    io.print("Enter your name: ")
    name = io.input()
    io.println("Hi, ", name, "! :-)")

math
^^^^^^^^^
A module used for complex math functions.


Operators
----------------
Operators can be used for a variety of often common operations.

Conditional operators
^^^^^^^^^^^^^^^^^^^^^^^^
These are used for comparing values. They include:

.. code-block:: none

   ==  // equals
   !=  // not equals
   >   // greater than
   <   // less than
   >=  // greater than or equal to
   <=  // less than or equal to

.. note::

    Don't accidentally confuse the assignment operator (=) with the equality operator (==). The former is used for assigning values to variables, while the latter is used for comparing values.

Atomic operators
^^^^^^^^^^^^^^^^^
These are used for performing operations on values. They include:

.. code-block:: none

   +   // addition
   -   // subtraction
   *   // multiplication
   /   // division

Keywords
----------------
[This] has a lot of keywords, and they all have their own special meaning. Here they are in alphabetical order:

def
^^^^^^^^^^^^
Defines a function. You can define a function with:

.. code-block:: none

   def function_name(parameters) {
       // function body
   }

Now, calling that function will execute the code in the function body.

.. code-block:: none

   function_name(arguments)

Calling a function with arguments will mean that you can use those arguments as variables in the function body. For example:

.. code-block:: none

   def greet(name) {
       print("Hello, " + name + "!")
   }

   greet("Alice") // prints "Hello, Alice!"

Functions as a variable don't mean anything usually, but some functions can return a value like the standard module functions.

.. code-block:: none

    import io
    name = io.input() // will return a string, being the input

You can't do this yourself yet.

Proposed
~~~~~~~~~~~~~~~~~
.. important::

    The below is a drafted list of features to be added. They do not reflect the current state of the language.
    They're subject to change and may not be added at all.

You can specify types for almost everything related to a function.

.. code-block:: none

   def function_name(parameter: type) -> return_type {
       // function body
   }

So, for example:

.. code-block:: none

   def add(x: int, y: int) -> int {
       return x + y
   }

This is extremely helpful for: 
    1. The compiler. The compiler now knows exactly what you want, can handle errors correctly, and can optimize the code much better. 
    2. The programmer. Now they can tell much better what the function actually does, especially if they have the language's VS Code extension.

if, else, elif
^^^^^^^^^^^^^^^^^^^^^^
Used for conditional statements. You can use them like this:

.. code-block:: none

   if (condition) {
       // code to execute if condition is true
   } 
   elif (another_condition) {
       // code to execute if another_condition is true
   } 
   else {
       // code to execute if all conditions are false
   }

Note that you don't need to have parentheses for if or elif, so this is legal:

.. code-block:: none

   if condition {
       // code to execute if condition is true
   } 
   elif another_condition {
       // code to execute if condition is false
   }

import
^^^^^^^^^^^^
Imports a module. You can import a module with:

.. code-block:: none

   import module_name

That file is meant to be one of the standard modules. Now, that module can be accessed from wherever in the file:

.. code-block:: none

   module_name.[function_or_variable]

Proposed
~~~~~~~~~~~~~~~~
.. important::

    The below is a drafted list of features to be added. They do not reflect the current state of the language.
    They're subject to change and may not be added at all.


Importing a module by file will make public whatever that file returns. Here's an example of a module:

.. code-block:: none
    :caption: my_cool_thing.this

    my_cool_thing = [] // Modules should be stored in an array and returned at the end with all their stuff.
    def my_cool_thing.foo() {
        print("Hello, world!")
    }
    // Now return that module/array.
    return my_cool_thing

Now, in the same directory, a seperate file:

.. code-block:: none
    :caption: main.this

    import my_cool_thing // don't put the extension

    my_cool_thing.foo() // prints "Hello, world!"

