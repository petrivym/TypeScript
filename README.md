# TypeScript short about Type
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
    "Don't  use this type, if you need typeScript"
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
    !BUT you must use narrow with union
      In TypeScript, "narrowing" refers to the process where the type of a variable is refined based on certain conditions or checks.
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

  * Type Assertions

    Sometimes you will have information about the type of a value that TypeScript can’t know about.
    For example, if you’re using document.getElementById, TypeScript only knows that this will return some kind of HTMLElement,
    but you might know that your page will always have an HTMLCanvasElement with a given ID.
    ```
    const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement;
    ```

  * Differences Between Type Aliases and Interfaces

    1. Interface is used for objects, while Type is used for different types.

      If we consider the use of these entities for objects, in some cases they are interchangeable.
      However, when it comes to other entities, it's not so straightforward. In such cases, we should use Type.
      ```
      interface Dog extends Animal {
        bark: () => void;
      }

      const dog: Dog = {
        name: 'Rex',
        bark: () => console.log('gaf')
      }
      ```

    2. Interface has the ability to create new interfaces based on previous ones.
      ```
        interface Animal {
          name = string;
        }

        interface Dog extends Animal {
          bark: () => void;
        }

        const dog: Dog = {
            name: 'Rex',
            bark: () => console.log('gaf')
        }
      ```

      Type has a different mechanism: the & (intersection) operator.
      ```
        type Person = {
          name: string;
          age: number;
        };

        type Employee = {
          id: number;
          department: string;
        };

        type PersonWithEmployeeInfo = Person & Employee;

        const employeeInfo: PersonWithEmployeeInfo = {
          name: "John Doe",
          age: 30,
          id: 123,
          department: "IT"
        };
      ```

    3.We can use an interface with the purpose of implementation, as an interface is an OOP concept.
      In the case of Type, such capability is not available.
      ```
      interface Printable {
        print(): void;
      }

      class Printer implements Printable {
        print(): void {
          console.log("print...");
        }
      }
      ```

  * Literal Types
    - const has has a literal type representation
      ```
        const constantString = "Hello World";
  
        constantString -> const constantString: "Hello World"
  
      ```
      - Also, we can do the same with let.
  
      ```
        let x: "hello" = "hello";
      ``` 
      - But they provide greater value when used with Union types.
      ```
        function printText(s: string, alignment: "left" | "right" | "center") {
          // ...
        }
  
        function compare(a: string, b: string): -1 | 0 | 1 {
           return a === b ? 0 : a > b ? 1 : -1;
        }
      ```
    - you can combine these with non-literal types
      ```
      interface Options {
        width: number;
      }

      function configure(x: Options | "auto") {
        // ...
      }
      ```
    - You can also use it for objects.
      Literal Inference
      ```
      const obj = { counter: 0 };

      if (someCondition) {
        obj.counter = 1;
      }
      ```
    - "as" const is a very useful feature in TypeScript. It allows you to convert the entire object to have literal types:
      ```
        const req = { url: "https://example.com", method: "GET" } as const;
      ```

  * Enums
    - Enums in TypeScript allow you to create a type that defines named values for constants.
    ```
    enum Direction {
      Up = "UP",
      Down = "DOWN",
      Left = "LEFT",
      Right = "RIGHT",
    }

    let userDirection: Direction = Direction.Up;

    if (userDirection === Direction.Up) {
      console.log("User chose the 'Up' direction.");
    }
    ```
  * null and undefined
  * Less Common Primitives
    - bigint
    - symbol
    
