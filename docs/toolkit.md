# Toolkits (Modules) in Nervestack

In Nervestack, a **toolkit** is a self-contained module that bundles reusable code, such as `spec`s, `blueprint`s, and `firm` constants. Toolkits are central to creating organized, maintainable, and shareable code. The modular system is built on three primary keywords: `toolkit`, `share`, and `plug`.

---

## 1. Defining a Toolkit

A `toolkit` is declared in its own file. The `toolkit` keyword is followed by the name of the module.

A toolkit can contain:
- Functions (`spec`s)
- Classes (`blueprint`s)
- Constants (`firm` variables)
- Interfaces (`bridge`s)

**Example: `math_utils.Nervestack`**
```Nervestack
toolkit MathUtils {
    firm PI = 3.14159

    spec add(a, b) {
        forward a + b
    }

    spec subtract(a, b) {
        forward a - b
    }
}
```

---

## 2. Exporting with `share`

By default, all code inside a `toolkit` is private. To make a `spec`, `blueprint`, or `firm` variable accessible from other files, you must explicitly export it using the `share` keyword.

**Example: `string_utils.Nervestack`**
```Nervestack
toolkit StringUtils {
    < This spec is private to the toolkit >
    spec internal_helper {
        ...
    }

    < This spec is public and can be imported >
    share spec capitalize(text) {
        < logic to capitalize text >
        forward ...
    }

    share firm GREETING = "Hello"
}
```

---

## 3. Importing with `plug`

To use a `toolkit` in another file, you import it with the `plug` keyword, followed by the toolkit's name and its file path.

**Syntax:**
```Nervestack
plug ToolkitName from "path/to/file.Nervestack"
```

You can also provide an alias for the toolkit using `as`.
```Nervestack
plug ToolkitName from "path/to/file.Nervestack" as Alias
```

**Example: `main.Nervestack`**
```Nervestack
plug MathUtils from "math_utils.Nervestack"
plug StringUtils from "string_utils.Nervestack" as Str

spec main {
    sum = MathUtils.add(10, 5)
    show("Sum: |sum|")

    greeting = Str.GREETING
    show(greeting)
}
```

---

## 4. A Complete Example

This example demonstrates how to define a `toolkit`, `share` its functionality, and `plug` it into a main program.

**File: `auth.Nervestack`**
```Nervestack
toolkit Auth {
    share spec verify_password(password) {
        check password == "Nervestack123" {
            forward On
        }
        forward Off
    }
}
```

**File: `app.Nervestack`**
```Nervestack
plug Auth from "auth.Nervestack"

inlet {
    password_input = ask("Enter your password: ")
    
    is_valid = Auth.verify_password(password_input)

    check is_valid {
        show("Access granted.")
    }
    altern {
        show("Access denied.")
    }
}
```

---

## Best Practices

- **Single Responsibility:** Each `toolkit` should focus on a single domain (e.g., math, authentication, file operations).
- **Explicit Exports:** Only `share` what is necessary to be used by other modules.
- **Clear Naming:** Use descriptive names for your `toolkit`s to make their purpose clear.
