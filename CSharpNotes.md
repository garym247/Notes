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


# Streaming
You can stream from various sources/destinations:
1. files
1. sockets
1. memory

## System.IO.Stream  
Is an abstract class. The following classes are derived from ```Stream```: 
- ```FileStream```
- ```MemoryStream```
- ```BufferedStream```
- ```NetworkStream```
- ```PipeStream```
- ```CryptoStream```
- ```IsolatedStorageFileStream```



Helpers
- ```StreamReader```
- ```StreamWriter```
- ```BinaryReader```
- ```BinaryWriter```
  


# File Input/Output


Stream->FileStream


FileStream


IOReader

TextReader->StringReader
         |->StreamReader

# Json
Two packages are available for JSON reading and writing:
1. Newtonsoft.Json
2. System.Text.Json

