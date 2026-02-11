# Release Notes - v2.0.0: Pack Collections & Unique Features

## 🎉 Major Update: Pack Collections and OOP Enhancements

Nervestack v2.0.0 introduces powerful new features that make the language even more expressive and unique!

### ✨ What's New

**Pack Collections** 🎒
- New `pack(items)` syntax for creating data collections
- Support for mixed-type collections: `pack(1, "hello", On)`
- Clean string representation
- Runtime interpretation for flexible data handling

**Traverse Loops** 🔁
- New `traverse i from start to end` syntax
- Replaces legacy `each` and `..` conventions
- Cleaner, more English-like iteration

**Blueprint/Spawn OOP Improvements** 🏗️
- Added `spec` keyword for method declarations
- Added `prep` keyword for constructors (alongside `make`)
- Enhanced parser support for complex OOP structures

**Accurate Documentation** 📚
- Created comprehensive `comparison.md` comparing Nervestack vs Java/C/Python
- Updated website with honest runtime description (C-powered JSON AST interpreter)
- Fixed all misleading dual-mode claims

### 🔧 Pack Collections Usage

```Nervestack
< Basic pack >
firm nums = pack(1, 2, 3)
show "Numbers: |nums|"

< Mixed types >
firm data = pack("hello", 42, On)

< Empty pack >
firm empty = pack()

< Pack with expressions >
firm calculated = pack(10 + 5, 20 * 2)
```

### 🔁 Traverse Loops

```Nervestack
traverse i from 1 to 5:
    show "Count: |i|"
done
```

### 📝 Blueprint/Spawn Enhancements

```Nervestack
blueprint Animal:
    has name
    has age
    
    prep (n, age_val):
        own~>name = n
        own~>age = age_val
    done
    
    spec speak:
        show "Animal speaks"
    done
done

firm dog = spawn Animal("Rex", 3)
```

### 🔨 Implementation Details

**Frontend Changes:**
- Added `pack` and `unpack` keywords to lexer
- Updated parser to handle `pack(items)` as expression
- Enhanced blueprint parsing for `spec`/`prep` syntax

**Backend Changes:**
- Implemented `PackNode` JSON parsing in `main.c`
- Added pack interpretation with string representation
- Fixed `TriggerNode` JSON serialization

**Website & Documentation:**
- Updated website to v2.0.0 with accurate content
- Removed false "dual execution modes" claims
- Added pack collections feature showcase
- Fixed syntax examples (removed parentheses from `show`/`ask`)
- Updated VS Code extension to v2.0.0

### 📦 Downloads

**Latest Release:** [v2.0.0](https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE/releases/tag/v2.0.0)

- **NSL.exe** - C runtime interpreter (near-native performance)
- **Nervestack-2.0.0.vsix** - VS Code extension with pack/unpack support

### 🐛 Bug Fixes
- Fixed `TriggerNode` serialization in JSON AST
- Resolved parser issues with constructor parameters
- Fixed string interpolation in method bodies

### 📚 Documentation
- [comparison.md](https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE/blob/master/comparison.md) - Language comparison guide
- [Website](https://adividan1012.github.io/Nervestack-Labs/) - Updated with v2.0 features

---

**Full Changelog**: [v1.0.0...v2.0.0](https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE/compare/v1.0.0...v2.0.0)

**Execution**: 
```bash
# Compile .NSL to JSON AST
python -m src.frontend.parser program.NSL

# Execute with C runtime
NSL.exe program.NSL.json
```
