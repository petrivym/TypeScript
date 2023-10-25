# TypeScript short about Type`  ` 
----------
__Everyday Types__
  * String
  * Number
  * Boolean
  * Arrays
    ```
    Array<number>
    number[]
    ```
  * Any
    ```
    Special type that you can use whenever you don’t want a particular
    value to cause typechecking errors.
    "Don't  use this type, if you need  typeScript"
    ```
  * Type Annotations on Variables
    ```
    You can optionally add a type annotation to explicitly specify the type
     of the variable:

     let myName: string = "Alice";
     In most cases, though, this isn't needed.
     TS is smart
    ```
  * Functions
    ```
      - Parameter Type Annotations
        foo(x: number) {
          return n;
        }
      - Return Type Annotations
        foo(): number {
          return 99;
        }
      - Functions Which Return Promise
        async function getFavoriteNumber(): Promise<number> {
          return 26;
        }
      - Anonymous Functions
        When a function appears in a place where TypeScript can determine how it’s going
        to be called, the parameters of that function are automatically given types.

        const names = ["Alice", "Bob", "Eve"];

        names.forEach(function (s) {
          console.log(s.toUpperCase());
        });
    ```
  * Object Types
    ```
    - The type part of each property is also optional.
      If you don’t specify a type, it will be assumed to be any.

    - Object types can also specify that some or all of their properties are optional. 
      To do this, add a ? after the property name

      function printName(obj: { first: string; last?: string }) {
      // ...
      }
    ```
  * Union Types
    ```
    Defining a Union Type

    function printId(id: number | string) {
      console.log("Your ID is: " + id);
    }

    there you can connect few types in one and your param will be like number string 
    !BUT you must use narrow  with union
    ```
  * Type Aliases
    ```
    Aliases - is a name for any type.
      The syntax for a type alias is:
        type Point = {
          x: number;
          y: number;
        };

        type ID = number | string;
    ```
  * Interfaces 
    ```
    An interface declaration is another way to name an object type:

    interface Point {
      x: number;
      y: number;
    }
    ```
  * Differences Between Type Aliases and Interfaces
    ```
    Almost all features of an interface are available in type,
    the key distinction is that a type cannot be re-opened to add
    new properties vs an interface which is always extendable.

    interface

    interface Window {
      title: string;
    }

    interface Window {
      ts: TypeScriptAPI;
    }

    const src = 'const a = "Hello World"';
    window.ts.transpileModule(src, {});

    type

    type Window = {
      title: string;
    }

    type Window = {
      ts: TypeScriptAPI;
    }

    // Error: Duplicate identifier 'Window'.
    ----------
    Extending an interface:

    interface Animal {
      name: string;
    }

    interface Dog extend Animal {
      bark: () => void
    }

    const dog: Dog = {
      name: "Reks"
      bark: () => console.log(this.name)
    }

    but we can Extending a type via intersections

    type Animal = {
      name: string;
    }

    type Bear = Animal & { 
      honey: boolean;
    }

    and Interface use like implements some class.We can't use type for that
    ``` 
  - Type Assertions

    Sometimes you will have information about the type of a value that TypeScript can’t know about.
    For example, if you’re using document.getElementById, TypeScript only knows that this will return some kind of HTMLElement,
    but you might know that your page will always have an HTMLCanvasElement with a given ID.
    ```
    const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement;
    ```
  - Literal Types

----------