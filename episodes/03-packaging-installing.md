---
title: "Packaging Python projects"
teaching: 0
exercises: 0
questions:
- "How do I use my own functions?"
- "How can I make my functions most usable for my collaborators?"
objectives:
- "Identify the components of a python package"
- "Apply a template for packaging existing code"
- "Update the packaged project after adding to the code"
- "Install and update a local or GitHub-hosted package"
keypoints:
- "Packaged python code is resuable within and across systems"
- "A python package consists of modules"
- "Projects can be distributed in many ways and installed with a package manager"
---

## Recall: Functions

We learned how to make functions before

FIXME: Example on writing functions to motivate packaging

## Pip

Pip is used to install packages from FIXME.

## Python Packages

A module is a piece of code that serves a paticular functionalty. In python moduls ecd with a **.py** extension and the name of the module is the name of the file. A module can contain classes, functions or a combination of both. Packages are namespaces which contain multiple packages and modules.


Working with Python packages and modules is simple. We need to:

* Create a directory and give it package's name.
* Put modules in it.
* Create a __init__.py file in the directory

The __init__.py file tells python that the directory is supposed to be read as a package.

e.g.

Let us create a package called **Vehicles** with two modules **Land** and **Water**.

### Step 1: Creating a directory
Create a directory called **Vehicles**

### Step 2: Adding Modules

```
class Land:
    def __init__(self):
        ''' Constructor for this class. '''
        # Create some vehicles 
        self.members = ['Cars', 'Trucks']
 
    def printMembers(self):
        print('Printing members of the Land  class')
        for member in self.members:
            print('\t%s ' % member)
```
The class has a property named members – which is a list of some vehicles we might be interested in. It also has a method named printMembers which simply prints the list of vehicles of this class.Note: all classes defined must be capable of being imported, and won't be executed directly. this will be saved in a file called **Land.py**

Next we create another module named **Water**. Create a file named **Water.py** inside the **Vehicles** directory and add the code below:
```	
class Water:
    def __init__(self):
        ''' Constructor for this class. '''
        # Create some member vehicles
        self.members = ['Boat', 'Yacht']
 
    def printMembers(self):
        print('Printing members of the Water class')
        for member in self.members:
           print('\t%s ' % member)
```

Note the code is similar to the **Land** module.

### Step 3 Adding the init file

Finally, we create a file named __init__.py inside the **Vehilces** directory and add the following code:
```
from Land import Land
from Water import Water
```
and that's all. Now we can import the package **Vehicles** 

e.g

```
from Vehicles import Land, Water

v1 =Land()
v1.printMembers()
```

## SetupTools

FIXME: how to setup the setup.py file

## Installing locally


FIXME

~~~
cd
pip install .
~~~
{; .language-pythons}

## Getting a Package from A Colleague

Many projects are distributed via GitHub as open source projects, we can use pip to install those as well.

Using git clone

Download and unzip their folder

Direct download?


~~~
cd project_dir
pip install .
~~~
{: language-bash}



{% include links.md %}
