# Handy c++ extensions

* Clang
* CommandlineArguments or Smart Commandline Arguments
* IncludeToolbox
* CustomizeVSWindowTitle

# Handy C# Extensions

# Debugging

To be able to see the memory windows whilst debugging ensure `Enable address-level debugging` is checked. See `Tools->Options->Debugging->General`.

# Toolchain

The toolchain specifies which version of the compiler tools will be used when building projects, e.g. x86 or x64.

How to use the 64-bit toolchain, set up a property sheet with the following setting:

```
<PropertyGroup Label="Configuration">
<PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

You can use the process explorer to determine if it is the 32-bit or 64-bit toolchain that is being run.

cl is the c++ compiler for Visual Studio.

# Toolset

To change which toolset the Visual Studio compiler is using

1. Goto `C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\VC\Auxiliary\Build`
2. Modify the following files:
    1. Microsoft.VCToolsVersion.default.props
    2. Microsoft.VCToolsVersion.default.txt

The toolset version can also be determined by opening a standard C++ header file, e.g. &lt;functional> and looking at the toolset version contained in its path, e.g.

```
C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\VC\Tools\MSVC\<toolset version>\include\functional
```