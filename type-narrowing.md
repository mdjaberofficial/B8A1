# TypeScript Type Narrowing: Safe Handling of Union Types
Type narrowing prevents errors by letting us safely work with flexible (union) types, using runtime checks like `typeof` so TypeScript can understand exactly what kind of data it's dealing with inside each branch of our code. 

The `typeof`operator is the most common tool for narrowing primitive types such as
strings, numbers, and booleans. Inside a conditional check, TypeScript restricts the
variable type to the matched primitive. For class instances, the `instanceof` operator
verifies prototype chains seamlessly.

When working with complex object union types, the `in` operator helps check for the
existence of specific property keys. This enables safe property access without runtime
errors.

```markdown
function printInfo(value: string | number): void {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
  } else {
    console.log(value * 10);
  }
}

```

```markdown
const processInput = (input: string | number | boolean): string | number => {
  if (typeof input === "string") {
    return input.trim().toLowerCase();
  } else if (typeof input === "number") {
    return input * 10;
  } else {
    return input ? "Active" : "Inactive";
  }
};
```

## Conclusion

Type narrowing bridges the gap between JavaScript's dynamic runtime behavior and TypeScript's static type system. By mastering tools like `typeof`, `instanceof`, and the `in` operator, you can write expressive union types while maintaining absolute confidence that your code will execute safely without unexpected runtime crashes.