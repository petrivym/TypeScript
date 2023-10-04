# TypeScript for the interview `Clean And Short` 
----------
- __Primitives__ (Everyday Types)
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
    "Doesn't use this type"
    ```
  * Type Annotations on Variables
    ```
    You can optionally add a type annotation to explicitly specify the type
     of the variable:

     let myName: string = "Alice";
     In most cases, though, this isn’t needed 
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

    ```
----------