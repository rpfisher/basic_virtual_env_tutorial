# basic_virtual_env_tutorial
Basic tutorial for git workflow practice and setting up python virtual environments and what they do

    Linux Walk through:
    Start ubuntu vm
    Quick switch to terminal view (fn + ctrl + alt + f1)
    Login
    Show root directory (/) [describe directories - contain files, other directories]
    ls - al
    pwd
    later on, anytime when we reference a file, if we start with a /, we start referencing from root (absolute path)
    Navigate directories (pwd, cd, ls)
    Show home directory (~)
    pwd (notice the full path, the ~ is a shortcut)
    create a directory
    Use an editor to create a file (nano - hello world example)
    Copy files, move files, delete files
    Viewing files (cat, less) [explain]
    Understanding Programs
    what is cat, less, etc?
    Show the âwhichâ command
    How does the operating system know what file to run?
    Show the path echo $PATH
    Our shell/environment has 
    Present working directory
    Variables/information it carries with it
    Show how to create a new shell variable
    TEST=âHELLO WORLDâ
    ECHO $TEST
    Use env to show the variable is now in the âenvironmentsâ variables
    Show how the variable is local to the current shell
    echo $TEST
    show the PID of the current shell (echo $$)
    Open another shell (/bin/bash)
    Show the PID of the new shell (echo $$)
    Echo $TEST (notice, it shows nothing)
    Exit the second shell
    Show how we can set variables to export
    Export TEST
    Repeat second shell example above
    
    Case and Point - linux environments can be customized with important information relevant to whatever you happen to be working on.  It can either be for a specific environment you are in right now (e.g. current shell), or can be set to be passed on to other programs as well (exported)
    
    
    
    A basic git workflow example:
    First, we're going to walk through the basic github tutorial
    https://guides.github.com/activities/forking/
    
    
    Next tutorial, based on this one:
    https://realpython.com/python-virtual-environments-a-primer/
    #We're going to install a package on your account, but in a way that you can turn it off and back on again, note how this is different than installing a program "normally", where it is available on a common path
    # Side note: What is a python package and what are we going to do?  It is a set of codes and a set of instructions where to put those codes in the Linux directories such that the code is on your path, then you can call those python codes once you install and "import" the package
    pip install --user virtualenv
    mkdir virtenv_test1
    cd virtenv_test1
    export MY_WORKING_PATH=${PWD} # Explain this command
    mkdir python-virtual-environments && cd python-virtual-environments
    virtualenv env
    source env/bin/activate
    cd env
    export MY_ENVIRONMENT_PATH=${PWD} # Explain this command
    cd $MY_WORKING_PATH # move back to our working directory,
    pwd # to see where you are
    #Now:
    #Fork this on github website: https://github.com/rpfisher/gwosc
    Click "Clone or Download" in green once you see your fork pop up, then copy the URL
    In terminal:  
    mkdir gwosc_test
    git clone https://github.com/rpfisher/gwosc.git
    cd gwosc
    pip install .  #Installs all dependencies needed as specified by the packaging code in setup.py
    cd ..
    python
    >>> import gwosc
    >>> print "IT WORKS!"
    >>> exit
    deactivate
    python
    >>> import gwosc
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ImportError: No module named gwosc
    >>> print ":("
    source python-virtual-environments/env/bin/activate
    #and you're back to the working environment with all necessary packages installed for the gwosc package to work!!
    #last comment
