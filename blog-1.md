If you don't know why any is risky, it is safer.

TypeScript is helpful because our types are checked before running our code. Any checks that but remove. With any, we can perform virtually anything with that value, even if it is incorrect.

For example:
let value: any = “Hello”;
value.toUpperCase();
value.push("test");
value();

The first line after the value is okay, while a string is required to use the toUpperCase function. However, push and calling value as a function are incorrect. With TypeScript it doesn't stop us either, since the type is any. That's why it is called any is a type safety hole.

unknown is better when we do not know what type of data we will get. It is not suitable for direct use of the value. First, we need to determine what kind of type.

For example:
let value: unknown = "Hello";

if (typeof value === "string") {
  value.toUpperCase();
}

This is safer as TypeScript will only allow toUpperCase once it knows that the value is string.

The checking is referred to as type narrowing. Type narrowing: it's checking a broader type.

For example:
Declare a variable of type StringOrNumber: string | number;

The checkValue function takes a value and returns a string:
  if (typeof value === "string") {
    return "String value";
  }

  return "Number value";
}

Within the if statement block, TypeScript is aware that the value is a string. Then, TypeScript is able to infer what the rest of the value could be: it has to be a number.

Therefore any should be avoided unless it is necessary, as it will conceal the error, whereas unknown will require checking of the data before using it. This helps us write cleaner and safer TypeScript code.