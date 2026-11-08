# How TypeScript Compilation Works and the Role of tsconfig.json

## Introduction

TypeScript is a programming language that adds static typing to JavaScript. However, browsers and Node.js cannot execute TypeScript directly. Therefore, we need to compile TypeScript into JavaScript using the TypeScript compiler (`tsc`).

## Compilation Process

When we compile TypeScript using `tsc`, the compiler performs the following steps:

1. **Parsing:** Reads TypeScript code and converts it into an Abstract Syntax Tree (AST), representing the code's structure.
2. **Type Checking:** Checks variable types, function parameters, and return types to identify type errors.
3. **Transpilation:** Transforms TypeScript code into JavaScript by removing type annotations and TypeScript-specific syntax.
4. **Output Generation:** Generates JavaScript (`.js`) files that browsers or Node.js can execute.

**Example:**

```typescript
// TypeScript code
function add(a: number, b: number): number {
    return a + b;
}

console.log(add(10, 20));
```

After compilation, the generated JavaScript looks like this:

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(10, 20));
```

Notice that TypeScript type annotations are removed during compilation.

## Role of tsconfig.json

`tsconfig.json` is the configuration file that tells the TypeScript compiler how to compile a project. It controls the compilation settings, such as:

- **target:** Specifies the JavaScript version to generate (ES5, ES2020, etc.).
- **module:** Defines the module system (CommonJS, ESNext, etc.).
- **strict:** Enables strict type-checking rules.
- **rootDir:** Specifies the source code directory.
- **outDir:** Specifies where compiled JavaScript files will be stored.

**Example:**

```json
{
    "compilerOptions": {
        "target": "ES2020",
        "module": "CommonJS",
        "strict": true,
        "rootDir": "./src",
        "outDir": "./dist"
    }
}
```

## Conclusion

TypeScript compilation converts TypeScript code into executable JavaScript while providing type checking during development. The `tsconfig.json` file helps developers customize and control the compilation process according to their project requirements.