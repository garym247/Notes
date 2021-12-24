# General

It's better to ask for forgiveness than permission (BAFP)

```print (<text>, end='')```
* to print without a new line at the end of the line


```
if __name__ == '__main__':
    try:
        main()
    except:
        print("Exiting program: Unhandled exception")
        for exceptionInfo in sys.exc_info():
            print("\t{0}".format(exceptionInfo))
```

```dir(<module name>)```
* prints all the functions/variables contained in a module
* Note: the module must have been imported

```help("modules")```
* displays the list of available modules. (need to check if that means installed?)

```type(<variable>)```
* returns the type of the object, i.e. the name of the class

```id(<variable>)```
* returns id of the object.
* Hint: this is a good way of determining if an object is immutable.

```pass```			is a null operation statement

# Modules

To determine what paths Python will search for import modules look at ```sys.path```.

```sys.path``` is a list object.

Extra search paths can be added to this by creating a PYTHONPATH environment variable.

Running a Python with the `-m` option will make Python search for your module in paths Python usually searches modules in, i.e. `sys.path`

Running ```python <file>.py``` does not use those Python search paths.

# Strings

Use the "+" operator to concatenate strings.

replace(&lt;sub-string to find>, &lt;replacement sub-string>)

strip

Use format(...) to format strings

"this is a {} string".format(&lt;var>)            # remember a string literal behaves just like a string object

can specify the placeholders :

 - via position

   "num = {2} num = {0} num = {1}".format(0, 1, 2)   # outputs "num = 2 num = 0 num = 1"

 - via name

   "person1 = {bob} person2 = {fred}".format(bob = "robert", fred = "freddy")

 - via a map

    d={"name1:"fred", "name2":"harry"}

    "person1 = {name1}, person2 = {name2}".format(**d)   # outputs "person1 = fred, person2 = harry"

# Conditional Expressions


```
if a < b:
    print("a is less than b")
else
    print("a is not less than b")
```

Similar to the ternary operator in 'C'


```
print("foo" if a < b else "bar")
```

# Loops

```
while <condition>:
    <statement 1>
    <statement 2>
    ...
    <statement n>
```

To read all the lines in a text file


```
f = open(<filename>)

for line in f.readlines():
    print(line)
```    

TODO: need to check the type of "line"; is it an iterator or a string?

Everything in Python is an object

```id(<var>)``` returns the id of an object

```type(<var>)```     	returns the type of an object

Use ```id(<var>)``` to determine what is a mutable or immutable object.

    

# Operators

 

 // integer division, e.g. 5 // 3 = 1

 ```divmod(<num1>, <num2>)```

 

 To format a number as binary

 

 {:08b}.format(&lt;number>), will print it as an 8 digit binary number.

 

 is        to test that the ids of two objects are the same

 is not    to test that the ids of two objects are different

 

 and        specific to bool operators (similar to && in c++)

 or         specific to bool operators (similar to || in c++)

 

# Containers (i.e. lists/tuples/dictionaries)

Container indices are 0-based.

len(&lt;list/tuple/dictionary>) returns the number of elements in the container

## Lists

A list is mutable.

`mylist[&lt;index1>:&lt;index2>]`    is called a slice.

 

`for i in range(0, 10):`         is similar to for( i = 0; i &lt; 10;i++ ) 

    `&lt;do something>`                            { &lt;do something>; }

`l1 = []`    // we need to define l1 first

`l1[:] = range(100)`   # create a 100 element list, initialised as [0, 1, 2, 3, ... 98, 99]

 

`l1[-1]` returns the last element

`list[&lt;index1>:&lt;index2>:&lt;step>]`, 

e.g. `list[27:42:3]` will return every 3rd element between index 27 and index 42

To test for the presence of an element, use the `in` operator


```
if value in ["one", "two", "three", "four"]:
    # do something

if value not in ["one", "two", "three", "four"]:
    # do something
```

## Tuples

A tuple is just a immutable list.

Tuples are specified by the "," operator, e.g.  t = 1, 4, 9

You don't need to put it in parenthesis like this  t = (1, 4, 9)

The problem is when you have a tuple with one element, e.g. 

t = (1)  # defines an integer not a tuple.

t = (1,) # defines a tuple.

t = tuple(range(10))  # creates a 10 element tuple initialised (0, 1, ..., 8, 9)

t[0] = 20     will generate an error since they are immutable

# Dictionaries/Maps


```
d={<key1>:<val1>, <key2>:<val2>, <key3>:<val4> }
```


To print out all the key/value pairs in a dictionary


```
for key in d:
    print(key, d[key])
```


or 


```
for key, value in d.items()
    print(key, value)
```


To add a new key/value pair to a dictionary, simply

    `d[&lt;key>] = value`

To access a dictionary element prefer to use the get(...) method

`d.get(&lt;key>)`    # returns None of the key does not exist

`d[&lt;key>]`        # will throw an exception if the key does not exist

The `get(...)` method also allows you to define a default value if the key is not found.


```
d.get(<key>, <returned default value if the key is not found>)
```


# Functions

yield can be used create generator functions

**<span style="text-decoration:underline;">Regular Expressions</span>**

import re   to import the regular expressions module

`re.search`       searches for a pattern throughout a string

`re.match`        similar to re.search but the pattern is anchored at the beginning of the string.

                i.e. it is like adding an ^ at the start of pattern

`re.sub`          to replace, i.e. to substitute

match = re.search(&lt;regular expression>, &lt;line to search>)

if match:

    &lt;regular expression has been found in the line>

    

match.group()   returns the actual pattern that has been matched

re.sub(&lt;regular expression>, &lt;replacement string>, &lt;line to search>)

 

# Exceptions


```
try:
    <code>
except <exception class> as e:
    <exception code>
else:
    <code to execute when no exception is raised>
```


try:

    &lt;code>

except:

    &lt;this will catch all exceptions>

    &lt;code to handle the exception>

To determine what exception currently being handled use   

e = sys.exc_info()

    

http://docs.python.org/library/exceptions.html

# Character Encoding

print(sys.stdout.encoding)    prints the code page used by stdout

by default sys.stdout uses "cp850"

To insert a unicode character into a string

str.encode(&lt;encoding>)    converts a string to a series of bytes according the encoding method

bytes.decode(&lt;decoding>)  converts a series of bytes to a string according the decoding method

Strings (i.e. the type str) in Python are always UNICODE.

Hence we have a statement like myString = myBytes.decode("UTF-8"), we are saying decode the

byte as UTF-8 and assign it to the UNICODE string.

Any unicode characters that appear in the cp850 codepage maybe written to stdout.

For example:

print("\u00e6")     # this fine as \u00e6 is in the cp850 code page

print("\u0087")     # will raise an UnicodeEncodeError as \u0087 is not in the cp850 code page

Best practice, is to use the "UNICODE" sandwich when working with external data, that is read it

in as bytes (via bytes.decode), manipulate it as UNICODE and then write it out as bytes (via str.encode).

# PIP

PIP may be run in three ways:

1. Via a command prompt (easiest), from the &lt;python dir>\Scripts directory, e.g. c:\Python\Scripts\pip.exe

Need to run in Administrator Mode for package to install.

2. Via a command prompt, from the python shell command, e.g. python -m pip [options]. 

   - Just use method 1 it is quicker.

   - The -m option runs a module as a script.

3. Programmatically by importing the pip module

`pip help` : will print the help for the pip tool

`pip help &lt;command>`: will print the help for a particular pip command

`pip list`  :  will list all the installed packages

`pip list -o`  :  will list all the installed packages that are now out of date

`pip install &lt;package name>`  : will install &lt;package name>

`pip install -U &lt;package name>`  : will update &lt;package name>


```
pip install g:\downloads\mutagen-1.31.tar.gz
```


`pip freeze` : similar to pip list, but outputs the installed packages in requirements file format, that can the be used by a `pip install -r &lt;requirements file>` command.

`pip freeze --local` : will only output the local packages

The following command will update all the locally installed packages:


```
pip freeze --local | grep -v '^\-e' | cut -d = -f 1  | xargs -n1 pip install -U
```


Note: the grep part of the command might not be necessary

To upgrade pip to the latest version:


```
python -m pip install --upgrade pip
```


To programatically get a list of the installed pip packages:


```
import pip
installed_packages = pip.get_installed_distributions()
print(installed_packages)
```


`pip search &lt;search string>`  :  Will search the available pip packages that match the search string.

When installing pip packages do this with Administrator privileges.

# Handy packages


```
pip install beautifulsoup4
pip install ddt      (data driven tests)
pip install mutagen
```


========================================================================

To read up on

========================================================================

vars - as used with command line options.
