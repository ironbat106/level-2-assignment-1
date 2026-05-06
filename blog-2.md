Why use generics and how they can help us write reusable TypeScript code.

Using generics we can write code that can work with many types and yet retain type safety. This means that when we want to do the same thing with a different data type, we don't have to code it again.

If we do not have generics, we can write individual functions such as this:
CreateStringArray(value: string): string[] {
  return [value];
}

function createNumberArray(value: number): number[] {
  return [value];
}

Both these functions are performing the same task. It is only in type that it differs. This results in repeated code and difficulty to manage.

With generics, it is possible to write one function and have the type inferred from the value we pass.

For example:
function createArray<T>(value: T): T[] {
  return [value];
}

const result1 = createArray("TypeScript");
const result2 = createArray(100);
Let result3 be an array created with the property name Alice.

In this case T is a dummy variable. When passed a string, T becomes a string. If an number is passed, then T is number. If an object is passed, T is defined as the type of the object.

Generics are also useful if we want to retain the exact type of an object.

For example:
function addCourse<T>(student: T) {
  return {
    course: "Next Level",
    ...student,
  };
}

const student = addCourse({ id: 1, name: "Alice", grade: "A" });

In this example, the types for id, name and grade are retained in TypeScript. It also adds the course property. Thus we have the ability to obtain reusable code without sacrificing type information.

We find generics helpful because they help prevent duplicate code, provide flexibility for functions, and preserve strongly-typed code. In actual projects they assist us in constructing functions, interfaces, and classes that are safe and can operate on various data.