# Unit Test Runners

Unit test runners that are available for python:
* pytest
* unittest
* nose2 (extends unit tests)

# pytest
Pytest will run functions with the "test_" prefix in modules named with the "test_" prefix.

# unittest
To execute tests via unittest:

```python -m unittest```
* will run all the unit test files in the current and child directories

```python -m unittest -v``` 
* gives a more verbose output (i like this as it lists each test/result)

```python -m unittest <python module>```
* to run the unit tests in a specific module (doesn't require the .py extension)

```python -m unittest <python module>.<class>```
* to run the unit tests for a specific class in a module

```python -m unittest <python module>.<class>.<method>```
* to run an individual unit test within a class

To execute tests as a simple module, add the following code
```
if __name__ == '__main__':
    unittest.main(verbosity=2)
```

The order in which the test methods are run is not defined, hence do not have one test method relying on the execution of another.

To test for an exception being raised:
```self.assertRaises(<exception name>, <function>, <param1>,..,<param n>)```


alternatively using a context manager the function can be called normally:
```
with self.assertRaises(<exception name>)
    <function>(param1,.., param n)
```

# nose
To execute tests via nose
