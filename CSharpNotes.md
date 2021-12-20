Parameter Attributes

By using the params keyword, you can specify a method parameter that
takes a variable number of arguments. The parameter type must be a
single-dimensional array.

# Strings

Strings are immutable.

*\<Use of Span>*

byte[] bytes = Convert.FromBase64String(base64string);

string value = Encoding.UTF8.GetString(bytes).Replace(\'1\', \'a\');

return Convert.ToBase64String(Encoding.UTF8.GetBytes(value));
