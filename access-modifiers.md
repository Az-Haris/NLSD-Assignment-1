# Understanding Access Modifiers in TypeScript OOP

### Introduction

Object-Oriented Programming (OOP) is not just about creating classes and objects. It is also about controlling how data and methods are accessed. TypeScript provides access modifiers like `public`, `private`, and `protected` to manage visibility. It also provides `readonly` to prevent properties from being reassigned.

### Understanding Access Modifiers

By default, class members are `public`, meaning they can be accessed from anywhere.

```ts
class User {
  public name: string = "Haris";
}

const user = new User();
console.log(user.name); // Haris
```

The `private` modifier restricts access to the declaring class. Neither external code nor subclasses can access it.

```ts
class Account {
  private balance = 5000;

  getBalance() {
    return this.balance;
  }
}
```

The `protected` modifier allows access inside the declaring class and its subclasses, but not from external objects.

```ts
class Person {
  protected age = 25;
}

class Developer extends Person {
  showAge() {
    return this.age;
  }
}
```

The `readonly` modifier allows a property to be assigned during declaration or inside the constructor. After initialization, it cannot be reassigned.

```ts
class Product {
  readonly id: number;

  constructor(id: number) {
    this.id = id;
  }
}
```

One important detail: TypeScript's `private` is primarily a compile-time restriction. JavaScript's native `#private` fields provide runtime privacy.

### Conclusion

Access modifiers help us build secure, predictable, and maintainable class structures. Using them properly keeps internal implementation details hidden while exposing only what other parts of the application actually need.
