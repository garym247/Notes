**Transform Adapter**

The lambda used by a transformed adapter should be simple function that
returns an object for each object piped into it.

IMPORTANT: The lambda should not do anything else, e.g. adding to a
list. Otherwise this unwanted side effect will happen each time the
transform is used.

```
const auto multiplyBy2= []( int num ) { return num * 2; };

for ( const auto number : numbers \| boost::adaptors::transformed( multiplyBy2 ) )
{
    std::cout \<\< \"number = \" \<\< number \<\< std::endl;
}
```


A lambda which does not return a value (i.e. void), will not compile.

There is also a boost::adaptors::transform(\...) function.
