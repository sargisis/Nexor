# MSV Language for VS Code

MSV is an interpreted programming language with support for object-oriented, functional, and procedural paradigms. It features a clean syntax with actions, classes, protocols, hooks, computed properties, pattern matching, and a built-in test system.

## Installation

### From VS Code Marketplace
1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X`)
3. Search for "MSV Language"
4. Click Install

### From VSIX
1. Download the `.vsix` file from [releases](https://github.com/msv-lang/msv-vscode/releases)
2. Open VS Code
3. Go to Extensions (`Ctrl+Shift+X`)
4. Click `...` → `Install from VSIX...`
5. Select the downloaded file

### Manual Installation
1. Clone this repository
2. Copy the `msv-vscode` folder to `~/.vscode/extensions/`
3. Restart VS Code

## Features

### Syntax Highlighting
Full TextMate grammar with semantic scopes for:
- Keywords (control flow, declarations, operators)
- Built-in types (`int`, `float`, `bool`, `string`, `array`, `dict`)
- Strings with escape sequence support
- Numbers (integer and float)
- Comments (`#` single-line)
- Function definitions and calls
- Class, protocol, and computed property declarations

### Snippets
| Prefix | Description |
|---|---|
| `action` | Define a new action (function) |
| `actionr` | Define an action with return type |
| `class` | Define a new class |
| `class-adopt` | Define a class adopting a protocol |
| `protocol` | Define a new protocol |
| `when` | Conditional when/otherwise block |
| `when-only` | Conditional when without otherwise |
| `switch` | Switch/case block with multiple cases |
| `switch-min` | Minimal switch/case block |
| `try` | Try/catch error handling |
| `test` | Define a test block |
| `test-assert` | Test with assertion |
| `assert` | Assert a condition |
| `hook-before` | Hook that runs before an event |
| `hook-after` | Hook that runs after an event |
| `extend` | Extend an existing class |
| `computed` | Define a computed property |
| `wloop` | While loop |
| `floop` | For-each loop |
| `floop-range` | For loop with range |
| `map` | Map over a collection |
| `filter` | Filter a collection |
| `reduce` | Reduce a collection |
| `adopt` | Adopt a protocol |
| `action` | Define a new action |

### Language Configuration
- Auto-closing brackets: `{}`, `[]`, `()`
- Auto-closing quotes: `""`, `''`
- Bracket matching and surrounding pairs
- Comment toggling with `Ctrl+/` (`#` comments)
- Smart indentation for blocks

## Example Code

```
# Hello World
action greet(name) {
    paint "Hello, " + name + "!"
}

# Class with protocol
protocol Speakable {
    action speak()
}

class Dog adopt Speakable {
    action speak() {
        paint "Woof!"
    }
}

# Conditional
when x > 10 {
    paint "Large"
} otherwise {
    paint "Small"
}

# Switch
switch value {
    case 1 {
        paint "One"
    }
    default {
        paint "Other"
    }
}

# Loop
floop item in items {
    paint item
}

# Error handling
try {
    result = riskyOperation()
} catch error {
    paint "Error: " + error
}

# Test
test "addition works" {
    assert add(2, 3) == 5
}

# Functional
squared = numbers.map(action(x) { x * x })
evens = numbers.filter(action(x) { x % 2 == 0 })
sum = numbers.reduce(action(acc, x) { acc + x }, 0)

# Hook
hook before render {
    paint "Preparing..."
}

# Computed property
computed fullName {
    return firstName + " " + lastName
}
```

## Snippets Documentation

All snippets are triggered by typing the prefix and pressing `Tab` or `Enter`. Placeholders (`$1`, `$2`, etc.) can be cycled through with `Tab`. See the table above for available snippets.

## Requirements

- VS Code 1.70.0 or higher

## Extension Settings

This extension contributes the following settings:

* `msv.language`: Language identifier (`msv`) registered for `.msv` files

## Known Issues

- No LSP support yet (syntax highlighting only)
- No autocompletion or error checking
- No debugger integration

## Release Notes

### 0.1.0
Initial release:
- Syntax highlighting for all MSV constructs
- 23 practical snippets
- Language configuration with auto-closing and indentation
- Comment toggling support

## Future Plans

- **Language Server Protocol (LSP)**: Go-to-definition, hover info, autocomplete, diagnostics
- **Debugger**: Step-through debugging for MSV scripts
- **Code Actions**: Refactoring and quick fixes
- **Formatter**: MSV code formatter
- **Test Explorer**: Integration with VS Code's test UI

## Contributing

Contributions are welcome! Please open an issue or pull request on [GitHub](https://github.com/msv-lang/msv-vscode).

## License

MIT
