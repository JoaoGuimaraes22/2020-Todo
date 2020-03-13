## Namespaces

**Overview:**

- Designed for providing a way to keep one set of names separate from another;

**Defining a namespace:**

- Syntax:

```
namespace namespace_name {
   // code declarations
}
```

- Example:

```
using System;

namespace first_space {
   class namespace_cl {
      public void func() {
         Console.WriteLine("Inside first_space");
      }
   }
}
namespace second_space {
   class namespace_cl {
      public void func() {
         Console.WriteLine("Inside second_space");
      }
   }
}
class TestClass {
   static void Main(string[] args) {
      first_space.namespace_cl fc = new first_space.namespace_cl();
      second_space.namespace_cl sc = new second_space.namespace_cl();
      fc.func();
      sc.func();
      Console.ReadKey();
   }
}
```

- Returns:

```
Inside first_space
Inside second_space
```

**The `using` keyword:**

- States that the program is using the names in the given namespace;
- For example, we are using the System namespace in our programs;
- The class Console is defined there;
- We write:
  - `Console.WriteLine ("Hello there");`;
- But we can write:
  - `System.Console.WriteLine("Hello there");`;
- For example, let us rewrite our preceding example, with using directive:

```
using System;
using first_space;
using second_space;

namespace first_space {
   class abc {
      public void func() {
         Console.WriteLine("Inside first_space");
      }
   }
}
namespace second_space {
   class efg {
      public void func() {
         Console.WriteLine("Inside second_space");
      }
   }
}
class TestClass {
   static void Main(string[] args) {
      abc fc = new abc();
      efg sc = new efg();
      fc.func();
      sc.func();
      Console.ReadKey();
   }
}
```

- Returns:

```
Inside first_space
Inside second_space
```

**Nested Namespaces:**

- Syntax:

```
namespace namespace_name1 {

   // code declarations
   namespace namespace_name2 {
      // code declarations
   }
}
```

- Accessing these member can be done like:

```
using System;
using first_space;
using first_space.second_space;

namespace first_space {
   class abc {
      public void func() {
         Console.WriteLine("Inside first_space");
      }
   }
   namespace second_space {
      class efg {
         public void func() {
            Console.WriteLine("Inside second_space");
         }
      }
   }
}
class TestClass {
   static void Main(string[] args) {
      abc fc = new abc();
      efg sc = new efg();
      fc.func();
      sc.func();
      Console.ReadKey();
   }
}
```

- Returns:

```
Inside first_space
Inside second_space
```

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_namespaces.htm ;
