# Intersection Types (&) vs Union Types (|) in TypeScript

## Introduction

TypeScript provides Intersection (`&`) and Union (`|`) types to combine multiple types. The main difference is that Intersection means **AND**, while Union means **OR**. They help developers define flexible and reusable types.

## 1. Intersection Type (&) – AND

An Intersection Type combines multiple types into one. A value must contain all required properties from the combined types.

**Example:**

```typescript
type Admin = {
    name: string;
    role: "admin";
};

type User = {
    name: string;
    email: string;
};

// Must satisfy BOTH types
type AdminUser = Admin & User;

const admin: AdminUser = {
    name: "Tushar",
    role: "admin",
    email: "tushar@gmail.com"
};
```

**Explanation:**
- `Admin` requires `name` and `role`.
- `User` requires `name` and `email`.
- `Admin & User` requires all three properties: `name`, `role`, and `email`.

Therefore, Intersection means **Admin AND User**.

## 2. Union Type (|) – OR

A Union Type allows a value to be one of multiple specified types. It must satisfy at least one type, not necessarily all of them.

**Example:**

```typescript
type Admin = {
    name: string;
    role: "admin";
};

type User = {
    name: string;
    email: string;
};

// Can satisfy either type
type Account = Admin | User;

const account1: Account = {
    name: "Tushar",
    email: "tushar@gmail.com"
};

const account2: Account = {
    name: "Rahim",
    role: "admin"
};
```

**Explanation:**
- `Account` can be an `Admin` OR a `User`.
- `account1` satisfies the `User` type.
- `account2` satisfies the `Admin` type.
- Both are valid because either type is acceptable.

## Conclusion

Intersection (`&`) requires a value to satisfy all combined types, whereas Union (`|`) allows a value to satisfy at least one of the specified types.