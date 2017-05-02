---
layout: post
title: "Unmessing Python packages with virtual environments"
date: 2017-04-30
---

When I teach programming to beginners, I often recommend Anaconda or Canopy as
the default environment for coding in Python. Such programs offer a convenient
solution for someone who is just starting to learn how to code, simplifying the
process of installing and managing Python packages. Also, such
programs alleviate cognitive overload of trying to understand what's happening
"under the hood", which might be desirable for someone who just learned what
a variable or a for loop is.
However, once a user starts to manage their own packages and once the understanding of
things "under the hood" becomes relevant, things can easily get tricky.
This post explains a simple and consistent way to manage Python packages.


### 50 shades of headaches
Python package management can be a mess if some advanced functionality is
needed.
For example, if you are a grad student and you just joined a lab that
speaks Python instead of Matlab/R/something else you've been used to.
Here are a few examples of situations which you might encounter:

- Package is not available in a Anaconda/Canopy/pip/OS-specific package repository
- A version of a package is needed that is different from the version currently
  installed on a computer
- Two different versions of the same package are needed (e.g., version 1.1 and version 1.2) for two different projects
- Two versions of the same package are needed, but one for Python 2.X and one
  for Python 3.X
- You do not have `sudo` privileges on the machine you are using
- You spent a whole night (or two) trying to understand why some import does not
  work while there is a package installed and it really should be working. You
  are reconsidering your choice to go to a grad school and wonder what is the meaning of life.

One way to deal with these kinds of issues is by using Python virtual
environments. A virtual environment (VE) is a program that isolates a group of Python packages and
keeps them separate from all other Python packages.
Then, when a group of packages is needed, the virtual environment containing that packages can
be <i>activated</i> and packages can be imported as usual with `import
package`.
The activation of a VE happens in a terminal, so there are no changes to the Python code.
The nice thing about this system is that there can be many VEs, and one VE can be activated in one shell prompt while another one can be activated in a different shell prompt.
On my computer, I have one general VE with Python 2.X installation that
I use frequently, then I keep a separate one for Python 3.X installation, and
sometimes I have other VEs for individual research projects.
Also, packages installed within a VE are kept separate from system-wide,
global Python packages that needed to run the operating system.
And messing with global Python packages that are used to run the OS is exactly what it sounds like --
not a great idea.
This kind of mess with global packages can happen when `sudo pip install` is used to install Python packages
(which, unfortunately, often shows up as a "solution" when googling for problems
related to installing Python packages). 


### Setting up Python Virtual Environments

In the next few paragraphs I will explain how to get VEs up and running. I will
assume a \*nix system and some basic familiarity with shell commands (e.g., navigation,
creating and removing directories). A tool used to create Python VEs is called
<a href="https://pypi.python.org/pypi/virtualenv" target="_blank">virtualenv</a>, and another tool called <a href="https://virtualenvwrapper.readthedocs.io/en/latest/index.html" target="_blank">virtenvwrapper</a> is a set of extensions
to virtualenv that provide shortcuts that allow setting up a VE more quickly.
Together, they make the management of Python packages convenient and fairly
simple.

Both of these packages can be installed with `pip`:
```
$ pip install --user virtualenv virtualenvwrapper
```

The `--user` flag ensures installation to a local user folder, so no sudo
privileges are required for that. `virtualenv` and `virtualenvwrapper` should be now
installed somewhere in a local folder, in my case they can be found in:
```
/home/ivana/.local/lib/python2.7/site-packages
```

but different versions of pip might put them in a different place. I use
`locate virtualenv.py` or `locate virtualenvwrapper` to double-check whey there
are.
Before we can create a new VE, we need to do two things: (1) specify a directory
where different virtual environments will be stored and (2) tell bash about new
commands we want to use (commands for maintaining VEs). 
We can do this by adding a few lines in `.bashrc`.
At this point, it is good to check where `virtualenvwrapper.sh` is located, as we will need to add that path in our `.bashrc`. For me, it is in `/home/ivana/.local/bin/virtualenvwrapper.sh`.
Then, we can append following lines to the
`.bashrc`:

```
# Python VE stuff
export WORKON_HOME=~/.virtualenvs
source /home/ivana/.local/bin/virtualenvwrapper.sh
```

`virtualenv` will create the directory specified in `WORKON_HOME` the first time we create a new VE (explained next) and it will also take care of managing the content in the directory.


In theory, this should be the end of the setup. You can test if it works by
opening a new terminal and creating a new environment:
```
$ mkvirtualenv first_env
```

The output should look similar to this one:
```
ivana@cassiopeia:~$ mkvirtualenv first_env
New python executable in /home/ivana/.virtualenvs/first_env/bin/python
Installing setuptools, pip, wheel...done.
virtualenvwrapper.user_scripts creating /home/ivana/.virtualenvs/first_env/bin/predeactivate
virtualenvwrapper.user_scripts creating /home/ivana/.virtualenvs/first_env/bin/postdeactivate
virtualenvwrapper.user_scripts creating /home/ivana/.virtualenvs/first_env/bin/preactivate
virtualenvwrapper.user_scripts creating /home/ivana/.virtualenvs/first_env/bin/postactivate
virtualenvwrapper.user_scripts creating /home/ivana/.virtualenvs/first_env/bin/get_env_details
(first_env) ivana@cassiopeia:~$ 
```
The name of the virtual environment has been prepended in front of a user
name and everything has been set up successfully.
In practice, something might go wrong here. A little troubleshooting section
below gives some guidelines (feel free to e-mail me if you get different errors).

##### Troubleshooting
When I first tried creating an environment, I had an issue with paths:

```
ivana@cassiopeia:~$ mkvirtualenv first_env
ERROR: virtualenvwrapper could not find virtualenv in your path
```
the sudo-less way to resolve this is to add `/home/ivana/.local/bin` to the
PATH in `.bashrc`:

```
export PATH=$PATH:/home/ivana/.local/bin
```

### Using Virtual Environments
Within a virtual environment packages can be installed as usual:
```
(first_env) ivana@cassiopeia:~$ pip install xkcd
Collecting xkcd
Installing collected packages: xkcd
Successfully installed xkcd-2.4.2
```

To get a list of installed packages use `pip freeze`:
```
(first_env) ivana@cassiopeia:~$ pip freeze
appdirs==1.4.3
packaging==16.8
pyparsing==2.2.0
six==1.10.0
xkcd==2.4.2
```
`deactivate` deactivates the current environment, and an environment can be activated again with
`workon first_env`. Use `rmvirtualenv` to remove a virtual environment (this
can be done only if that environment is not currently active).
If there is an environment that is used frequently, it can be useful to add it to
`.bashrc` so that every time a new terminal is opened, this environment is
activated by default. To do so, just add `workon first_env` (or whatever name of that
environment is) in `.bashrc` after `source /home/ivana/.local/bin/virtualenvwrapper.sh`.

This was a light-weight introduction into the world of virtual environments,
and there are plenty of other features which I have not mentioned here.
<a href="http://docs.python-guide.org/en/latest/dev/virtualenvs/#virtualenv" target="_blank">This nice tutorial</a> provides more information on commands that exists and related useful tools.

