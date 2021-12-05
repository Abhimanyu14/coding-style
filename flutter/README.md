# Table of contents

- Philosophy
- Getting Started
  - Installation
  - Testing
- Documentation
  - Writing prompts for good documentation
  - Canonical terminology
- Coding Conventions
  - Getters
  - Avoid interleaving multiple concepts together
  - Avoid secret (or global) state
- Coding Patterns
- Formatting
  - Methods and properties ordering
  - Attribute ordering
  - Trailing comma
  - Arrow functions
  - Brackets
  - Strig quotes
  - Prefer += over ++
  - Use double literals for double constants
  - Features expected every widget to implement
- Git
  - Commands
  - Convention

# Philosophy

- We try to avoid reliance on "oral tradition".
- It should be possible for anyone to begin contributing without having had to learn all the secrets from existing team members.
- To that end, all processes should be documented (typically on the wiki), code should be self-explanatory or commented, and conventions should be written down, e.g. in our style guide.

# Getting Started

## Installation

- **To install app**

```
flutter run lib/main.dart
```

## Testing

- **To run all unit tests**

```
flutter test
```

- **To run a selected unit test**

```
flutter test test_file_directory/test_file_name.dart
```

- **To run widget test**

```
flutter test test_file_directory/test_file_name.dart
```

- **To run widget test in device**

```
flutter run test_file_directory/test_file_name.dart
```

- **To run integration tests**

```
flutter drive --driver integration_test/driver.dart --target integration_test/app_test.dart --profile
```

# Documentation

- Reference - https://dart.dev/guides/language/effective-dart/documentation#doc-comments

- DO NOT use block comments
- Capitalize the first word unless it’s a case-sensitive identifier.
- End it with a period (or '!' or '?').
- Use dartdoc comments wherever applicable.
- Separate the first sentence of a doc comment into its own paragraph.
- Reference - https://dart.dev/guides/language/effective-dart/documentation#do-separate-the-first-sentence-of-a-doc-comment-into-its-own-paragraph
- Avoid redundancy with the surrounding context.
- Start function or method comments with third-person verbs.
- Start variable, getter, or setter comments with noun phrases.
- Consider including code samples in doc comments.
- Use square brackets in doc comments to refer to in-scope identifiers.
- Markdown is allowed in doc comments
- Use backtick fences for code blocks.
- Write good comments.

### Writing prompts for good documentation

- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#writing-prompts-for-good-documentation

### Canonical terminology

- The documentation should use consistent terminology:
  - method - a member of a class that is a non-anonymous closure
  - function - a callable non-anonymous closure that isn’t a member of a class
  - parameter - a variable defined in a closure signature and possibly used in the closure body.
  - argument - the value passed to a closure when calling it.
- Prefer the term "call" to the term "invoke" when talking about jumping to a closure.
- Prefer the term "member variable" to the term "instance variable" when talking about variables associated with a specific object.
- Typedef dartdocs should usually start with the phrase "Signature for…​".
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#canonical-terminology

# Coding Conventions

Follow https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo as general convention unless anything mentioned belows conflicts it.  
Follow the below mentioned in case of any conflicts.

### Getters

- Property getters should be efficient. If not, it should be a method instead.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#getters-feel-faster-than-methods

### Avoid interleaving multiple concepts together

- Many Widgets take a child. Widgets should be entirely agnostic about the type of that child. Don’t use is or similar checks to act differently based on the type of the child.
- In general, prefer immutable objects over mutable data.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#avoid-interleaving-multiple-concepts-together

### Avoid secret (or global) state

- A function should operate only on its arguments and, if it is an instance method, data stored on its object.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#avoid-secret-or-global-state

## Coding Patterns

### Use asserts liberally to detect contract violations and verify invariants

- Reference -

### Prefer specialized functions, methods and constructors

### Minimize the visibility scope of constants

- Reference -

### Avoid using if chains or ?: or == with enum values

- Use switch with no default case if you are examining an enum, since the analyzer will warn you if you missed any of the values when you use switch.

### Avoid using var and dynamic

- **DO NOT** use var and dynamic unless no other option is there.
- If the type is unknown, prefer using Object (or Object?) and casting, as using dynamic disables all static checking.

### Extension methods

- Use extension methods appropriately.

### Avoid mysterious and magical numbers that lack a clear derivation

- Use 60 \* 60 for seconds in an hour instead of 3600.

### Common boilerplates for operator == and hashCode

- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#common-boilerplates-for-operator--and-hashcode

# Parameters

- **Always use named parameters**

# Naming

### Global constants

- **DO NOT** begin global constant names with prefix "k"
- This should not be used in this project

### Avoid abbreviations

- Unless the abbreviation is more recognizable than the expansion (e.g. XML, HTTP, JSON), expand abbrevations when selecting a name for an identifier.
- In general, avoid one-character names unless one character is idiomatic (for example, prefer index over i, but prefer x over horizontalPosition).

### Avoid anonymous parameter names

- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#avoid-anonymous-parameter-names

### Typedefs and function variables

- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#naming-rules-for-typedefs-and-function-variables

### Spell words in identifiers and comments correctly

- Use UK english words in case of any difference with US english words.
- Referce - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#spell-words-in-identifiers-and-comments-correctly

### Capitalize identifiers consistent with their spelling

- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#capitalize-identifiers-consistent-with-their-spelling

### Avoid double negatives in APIs

- Refernce - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#avoid-double-negatives-in-apis

### Setter

- Prefer naming the argument to a setter value
- Refernce - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#prefer-naming-the-argument-to-a-setter-value

### Qualify variables and methods used only for debugging

- Remove debug code unless absolutely necessary.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#qualify-variables-and-methods-used-only-for-debugging

# Comments

- Add appropriate comments when implementing any workarounds.
- Add necessary TODOs. So that they are checked and handled later.
- No commented code is allowed
- Use of ignore comments must be valid.

# Formatting

### Methods and properties ordering

- Order methods based on lifecycle in chronological order.

1. Constructors, with the default constructor first.
2. Constants of the same type as the class.
3. Static methods that return the same type as the class.
4. Final fields that are set from the constructor.
5. Other static methods.
6. Static properties and constants.
7. Mutable properties, each in the order getter, private field, setter, without newlines separating them.
8. Read-only properties (other than hashCode).
9. Operators (other than ==).
10. Methods (other than toString and build).
11. The build method, for Widget and State classes.
12. operator ==, hashCode, toString, and diagnostics-related methods, in that order.

- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#order-other-class-members-in-a-way-that-makes-sense

### Attribute ordering

- Order attributes possibly in the same order in which they are defined in parent widget.

### Trailing comma

- Always use a trailing comma for arguments, parameters, and list items.

### Arrow functions

- Always use a trailing comma for arguments, parameters, and list items.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#consider-using--for-short-functions-and-methods

### Brackets

- Use brackets for all conditionals and loops.

### String quotes

- Use single quotes for strings.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#prefer-single-quotes-for-strings

### Prefer += over ++

- Use += instead of ++.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#prefer--over-

### Use double literals for double constants

- Always use double literals for double constants
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#use-double-literals-for-double-constants

### Features expected every widget to implement

- full accessibility, so that on both Android and iOS the widget works with the native accessibility tools.
- full localisation with default translations for all our default languages.
- full support for both right-to-left and left-to-right layouts, driven by the ambient Directionality.
- full support for text scaling up to at least 3.0x.
- documentation for every member; see the section above for writing prompts to write documentation.
- good performance even when used with large amounts of user data.
- a complete lifecycle contract with no resource leaks (documented, if it differs from usual widgets).
- tests for all the above as well as all the unique functionality of the widget itself.
- Reference - https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#features-we-expect-every-widget-to-implement

# Git

### Commands

- **To clone repo**

```
git clone https://github.com/Abhimanyu14/expense-tracker.git
```

### Convention

- **Branch naming**

```
<contributor_name>/<logical_branch_name>
```
