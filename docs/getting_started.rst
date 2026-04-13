.. toctree::
   :maxdepth: -1

Getting Started
===================================

What is [This]?
----------------

[This] (/ðɪs/) is a dynamically-typed, multi-paradigm programming language.
We'll be going through how to obtain its source and how to build it.

Building
----------------

**[This]** is distributed only in source. It's meant to be built via CMake, so you are going to need both CMake itself and a C++ compiler.
There's plenty of good tutorials on how to do both of these online, so I won't be going into the details of how to do that. Just get CMake and maybe gcc installed.

Once you have those, you can firstly clone the repository:
.. code-block:: bash

   git clone https://github.com/CaperTheCat/this

Inside of it is a CMakeLists.txt file, so you can just run CMake in the root of the repository and it should be able to find it and build the project.

.. code-block:: bash

   cd path/to/this
   cmake -S . -B build
   cmake --build build

Now, you should have a built version of [This] in the build directory. You can run it with:

.. code-block:: bash

    ./build/this

I highly recommend putting this build directory or the executable in your system PATH, so you can just do:

.. code-block:: bash

    this 

to run the executable from anywhere in your terminal.

Think you have it installed and on your PATH? Try running:

.. code-block:: bash

    this --version

You should get "I'm on version 0.2.0b-alpha!" if you have it installed correctly.