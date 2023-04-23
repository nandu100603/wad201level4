# NAMESPACES:
- Namespaces are used to group related classes, functions, and other types of data under a common name.
- This helps to avoid naming conflicts and makes the code more modular and easier to manage.
- Namespace is a declarative region that provides a scope for identifiers (names) in order to avoid naming conflicts.
- Namespaces are defined using the `namespace` keyword, followed by the name of the namespace and its body enclosed in braces.
- To access an identifier inside a namespace, use the scope resolution operator (::).
```cpp
namespace MyNamespace {
    int myVar = 10;
    void myFunction() {
        // Code here
    }
}

int main() {
    MyNamespace::myFunction();
    int localVar = MyNamespace::myVar;
    return 0;
}
```
### Nested Namespaces IN C++
- Namespaces can be nested inside other namespaces, creating a hierarchical organization of code.
- To define a nested namespace, use the ` namespace ` keyword inside another namespace.
```cpp
namespace Outer {
    namespace Inner {
        int myVar = 5;
    }
}

int main() {
    int localVar = Outer::Inner::myVar;
    return 0;
}
```
### Using the ‘using’ directive and ‘using’ declaration in C++
The ‘using’ directive allows you to bring an entire namespace into the current scope, while the ‘using’ declaration brings a specific identifier from a namespace into the current scope.
```cpp
// using directive
using namespace MyNamespace;

// using declaration
using MyNamespace::myFunction;

int main() {
    myFunction(); // No need to use scope resolution operator
    return 0;
}
```
### Anonymous Namespaces IN C++
- Anonymous namespaces are unnamed namespaces that have a unique identifier and are local to a single translation unit.
- They are implicitly ‘inline’ and their members have internal linkage, making them invisible outside of the translation unit they are defined in.
```cpp
namespace {
    int localVar = 42;
}

int main() {
    std::cout << localVar << std::endl; // localVar is accessible
    return 0;
}
```
### Inline Namespaces in C++
- C++11 introduced inline namespaces, which allow the compiler to treat the members of an inline namespace as if they belong to the enclosing namespace.
- This is useful for versioning or managing backward compatibility.
```cpp
namespace MyLibrary {
    inline namespace v1 {
        void myFunction() {
            // Version 1 implementation
        }
    }

    namespace v2 {
        void myFunction() {
            // Version 2 implementation
        }
    }
}
```
