Moltap
======
.. note:: This is a fork of the Moltap package with more detailed instrcutions on how to set-up the project

This does not belong to me! I fixed this up for a friend. It's Twan's roadshow (from 2008).
All I did was make it build with a modern stack (Stack + GHC 7.10.3)

Originally from: http://twan.home.fmf.nl/moltap/


Installing *Git* on a *Mac*
===========================

`Open a terminal window <http://www.youtube.com/watch?v=zw7Nd67_aFw>`_

Step 1 – Install `*Homebrew* <http://brew.sh/>`
===============================================

::

    *Homebrew* […] simplifies the installation of software on the Mac OS X operating system.

– `Homebrew – Wikipedia <http://en.wikipedia.org/wiki/Homebrew_%28package_management_software%29>`_

**Copy & paste the following** into the terminal window and **hit `Return`**::

    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    brew doctor

You will be offered to install the *Command Line Developer Tools* from *Apple*. **Confirm by clicking *Install***. After the installation finished, continue installing *Homebrew* by **hitting `Return`** again.

Step 2 – Install *Git*
======================

**Copy & paste the following** into the terminal window and **hit `Return`**::

    brew install git

**You can use *Git* now.**

Step 3 - Install *graphviz*
===========================
**Moltap depends on graphviz to generate the graphs of the models**::
    brew install graphviz

** *Graphviz* is now installed**

Step 4 - Install *Stack*
========================
Proceed with installing stack. This will install ghc (the haskell compiler) automatically::
    curl -sSL https://get.haskellstack.org/ | sh
If curl is not installed, please use::
    wget -qO- https://get.haskellstack.org/ | sh

Step 5 - Clone the Moltap repository
====================================
Clone the Moltap project from github::
    git clone https://github.com/bitemyapp/Moltap.gi://github.com/bitemyapp/Moltap.git 

**The repositroy is now cloned. There should be a repository called Moltap in your current directory.**

Step 6 - Compile the Moltap project
===================================

First, move into the directory. Then proceed with the following stack commands::
    cd Moltap
    stack setup
    stack build

.. note:: The stack setup will download the compiler if necessary in an isolated location (default ~/.stack) that won't interfere with any system-level installations. (For information on installation paths, please use the stack path command.).
.. note:: The stack build command will build the minimal project.

Step 7 - Running Moltap
=======================

After the three commands passed, the binary `moltap` will be located at::

    **./.stack-work/install/system/os/ghc_release/bin**

System and os  will differ for every system running the above commands. 
But there is only one subdirectory in *.stack-work/install*, so there should be no problem::

    cd ./.stack-work/install/system/os/release/bin

Once in the *bin* directory, exectute the *moltap* binary with::

    ./moltap -i

.. note:: This is the interactive mode

or type::
./moltap --help

for further information about the usage of the program.

.. hint:: Every command entered in moltap will generate an image-file called *model.png* that is in the same directory as the moltap binary and represents the model associated with the formula submitted.




# Moltap

Originally from: http://twan.home.fmf.nl/moltap/

# Building

Make sure you have [Stack installed](http://haskellstack.org), then in the project:

```
$ stack build
```
