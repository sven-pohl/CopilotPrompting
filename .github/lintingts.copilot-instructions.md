---
applyTo: "**/*.ts"
---

# Copilot Instructions for Styling and Linting

## General Code Style and Formatting

### File Structure and Organization
- Use kebab-case for filenames (enforced by `unicorn/filename-case`)
- Always include a copyright header in block comment format with the pattern: "Restricted - Copyright (C) Siemens Healthcare GmbH/Siemens Medical Solutions USA, Inc., [YEAR]. All rights reserved."
- Use Windows line endings
- Always end files with a newline (`eol-last`)

### Code Formatting
- Use single quotes for strings, allow template literals when needed (`quotes`)
- Always use semicolons (`@stylistic/ts/semi`)
- Remove trailing spaces (`no-trailing-spaces`)
- Avoid multiple consecutive empty lines (`no-multiple-empty-lines`)
- Use consistent type annotation spacing (`@stylistic/ts/type-annotation-spacing`)

### TypeScript and JavaScript Best Practices

#### Variable Declarations
- Use `const` for variables that are never reassigned (`prefer-const`)
- Avoid `var` declarations, use `let` or `const` instead (`no-var`)
- Don't initialize variables to `undefined` explicitly (`no-undef-init`)
- Remove unused variables, but allow unused function parameters (`@typescript-eslint/no-unused-vars`)

#### Functions and Arrow Functions
- Use arrow function syntax when the body can be a single expression (`arrow-body-style`)
- Use camelCase for function names, allow leading/trailing underscores (`@typescript-eslint/naming-convention`)
- Prefer function types over interfaces with only call signatures (`@typescript-eslint/prefer-function-type`)
- Unify signatures where possible (`@typescript-eslint/unified-signatures`)

#### Types and Interfaces
- Use PascalCase for type-like constructs (classes, interfaces, types, enums) (`@typescript-eslint/naming-convention`)
- Use consistent type definitions (`@typescript-eslint/consistent-type-definitions`)
- Avoid inferrable types on parameters where the type is obvious (`@typescript-eslint/no-inferrable-types`)
- Avoid empty interfaces (`@typescript-eslint/no-empty-interface`)
- Avoid non-null assertions (`@typescript-eslint/no-non-null-assertion`)
- Avoid misusing `new` with interfaces (`@typescript-eslint/no-misused-new`)

#### Control Flow and Logic
- Always use curly braces for control statements (`curly`)
- Use smart equality (`eqeqeq` - `===` and `!==` except where `==` is clearly safer)
- Always specify radix parameter for `parseInt()` (`radix`)
- Use guard clauses in for-in loops (`guard-for-in`)
- Avoid fallthrough in switch cases (`no-fallthrough`)
- Avoid unused expressions (`no-unused-expressions`)
- Don't use variables before they're defined, except for functions (`@typescript-eslint/no-use-before-define`)

#### Error Handling and Debugging
- Don't use `console` statements in production code (`no-console`)
- Don't use `debugger` statements (`no-debugger`)
- Only throw Error objects, not literals (`@typescript-eslint/only-throw-error`)

#### Deprecated and Restricted Patterns
- Avoid deprecated APIs and mark warnings for deprecated usage (`@typescript-eslint/no-deprecated`, `import/no-deprecated`)
- Don't use `eval()` (`no-eval`)
- Avoid `new` wrappers for primitives (`no-new-wrappers`)
- Don't use `caller` or `callee` (`no-caller`)
- Avoid bitwise operators unless specifically needed (`no-bitwise`)
- Don't import the entire RxJS library (`no-restricted-imports` for "rxjs/Rx")
- Don't shadow variables (`@typescript-eslint/no-shadow`)
- Remove unused labels (`no-unused-labels`)

### Angular-Specific Rules

#### Component and Directive Best Practices
- Implement lifecycle interfaces when using lifecycle methods (`@angular-eslint/use-lifecycle-interface`)
- Use contextual lifecycle methods appropriately (`@angular-eslint/contextual-lifecycle`)
- Don't leave lifecycle methods empty (warning level) (`@angular-eslint/no-empty-lifecycle-method`)
- Implement `PipeTransform` interface for pipes (`@angular-eslint/use-pipe-transform-interface`)

#### Input/Output Best Practices
- Avoid renaming inputs and outputs (warning level for inputs, error for outputs) (`@angular-eslint/no-input-rename`, `@angular-eslint/no-output-rename`)
- Don't use native event names for outputs (`@angular-eslint/no-output-native`)
- Don't prefix outputs with "on" (`@angular-eslint/no-output-on-prefix`)
- Don't use metadata properties for inputs/outputs in component decorators (`@angular-eslint/no-inputs-metadata-property`, `@angular-eslint/no-outputs-metadata-property`)

#### Modern Angular Practices
- Prefer dependency injection over constructor parameters (warning level) (`@angular-eslint/prefer-inject`)
- Consider using standalone components (warning level) (`@angular-eslint/prefer-standalone`)

#### Class and Member Organization
- Follow consistent member ordering in classes (`@typescript-eslint/member-ordering`)
- Use proper constructor calls for inheritance (`constructor-super`)

### Documentation
- Ensure JSDoc comments are properly aligned (`jsdoc/check-alignment`)

### Import Management
- Avoid internal imports outside of designated boundaries (`@syngo/restrict-internal-import`)
- Avoid cross-package relative imports (`@syngo/restrict-cross-package-relative-imports`)

## Severity Levels
- **Error (2)**: Must be fixed - these are critical issues that will break the build
- **Warning (1)**: Should be fixed - these are code quality issues that should be addressed
- **Off (0)**: Disabled - these rules are not enforced but may have specific configuration

## Special Considerations
- Report unused ESLint disable directives to keep the codebase clean
- Use TypeScript project configuration for enhanced type checking
- Target ECMAScript 2026 with module sourceType
- Process inline HTML in templates when applicable

When writing code, always follow these guidelines to maintain consistency with the project's linting configuration and ensure high code quality.