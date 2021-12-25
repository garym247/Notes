# Sconstruct vs Sconscript

These files are both python scripts

# Command-line Arguments
<table>
  <tr>
   <td><code>-Q</code>
   </td>
   <td>Suppresses output from the build. It’s a good way of debugging scons as it de-clutters the the output.
   </td>
  </tr>
  <tr>
   <td><code>-c (or --clean)</code>
   </td>
   <td>
   </td>
  </tr>
</table>


# Builder Methods
```Program(<source file>)```
```Program(<target name>, <source file>)```
```Program(<list of source files>)```


* the list of source files is python list
* the target name is the base name of first source file


```Program(target=<target name>, source= <list of source files>)```



* can also use named arguments


```
Object(...)

StaticLibrary(...) (or Library(....))

```



* 


```
SharedLibrary(...)

Java(...)
```


# How Scons Works

Scons decides the order in which the functions are called. The order in which they appear in the python script is irrelevant.

