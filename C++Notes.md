# RAII - Resource Allocation Is Optimization

The best way to think about this, is any time a resource is
allocated/locked, then that resource should be contained within an
object that when destructed will free the resource.

This is not RAII

```
icon = LoadIcon(id); // allocates a resource

if( \<condition> )
{
    return; // when hit, this will cause a memory leak
}

FreeIcon(icon); // frees up the space allocated by the icon

```
Nice way to get objects (and an index) from a vector.

```
const auto indexedObjects = objects | boost::adaptors::indexed( 0 );

for ( const auto indexedObject : indexedObjects )
{
    std::cout << indexedObject.index() << std::endl;
}

cin.ignore();
cin.get();

```

# Return value optimisation

Notes:

Prefer lamdas to std::bind(\...) or boost::bind(), stack trace is so
much cleaner

Usually need to capture this

Other Stuff

```
std::map\< UINT, DockableViewPtr \> m_dockableViews;

BOOST_FOREACH(const auto& view, m_dockableViews | boost::adaptors::map_values)

boost::copy(input | filtered(is_even()),std::ostream_iterator<int>(std::cout, ","));

```

ADL: Argument dependent lookup
