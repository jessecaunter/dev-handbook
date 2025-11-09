# JavaScript Debugging Workflow with Firefox Debugger

## Problem

Using `console.log()` for debugging is convenient but has limitations:

- Tedious for catching issues as they happen
- Requires adding/removing console statements
- Can't easily inspect execution flow or trace through function calls
- Difficult to debug specific conditions (e.g., only when a variable has a certain value)

## Solution

Use Firefox Debugger (or browser DevTools) for interactive debugging with breakpoints, stepping through code, and inspecting variables in real-time.

## Basic Debugging Workflow

### 1. Set a Breakpoint

Click the line number in the debugger source pane to set a breakpoint. Code execution will pause at this line.

### 2. Trigger the Breakpoint

Execute the code path that contains the breakpoint (e.g., submit a form, click a button).

### 3. Inspect Variable Values

When paused at a breakpoint, inspect variables using three methods:

**Method 1: Console** Type the variable name in the console while paused to see its value.

**Method 2: Hover** Hover over variables in the source pane to see their values and properties.

**Method 3: Scopes Section** View all variables in the current scope in the right sidebar.

**Method 4: Watch Expressions** Add expressions to the Watch Expressions section to monitor them as you step through code.

### 4. Step Through Code

Use the debugger toolbar buttons:

- **Step Over** - Execute the current line and move to the next line (executes functions without stepping into them)

- **Step In** - Enter into the function on the current line to debug it

- **Step Out** - Execute the rest of the current function and return to the caller

- **Play/Resume** - Continue execution until the next breakpoint

## Advanced Techniques

### Conditional Breakpoints

Only pause execution when a specific condition is true.

**How to set:**

1. Right-click on a line number
2. Select "Add Conditional Breakpoint"
3. Enter a JavaScript expression (breakpoint triggers only when expression evaluates to `true`)

**Example:**

```javascript
title.indexOf("turtle") != -1; // Only pause if "turtle" is in the title
```

**Console.log Trick:** Use console.log() in a conditional breakpoint to log without pausing:

```javascript
console.log(items[index].title); // Returns undefined (falsy), so won't pause
```

This provides logging without cluttering source code with temporary console statements.

### Call Stack Navigation

The Call Stack section shows the chain of function calls that led to the current breakpoint.

**Use case:** When you discover a bug in a function, click through the call stack to trace backwards and find where bad data originated.

**Example workflow:**

1. Pause in a function with unexpected data
2. Click on parent functions in the call stack
3. Inspect variables at each level to find where the problem started

### The debugger Statement

Add `debugger;` directly in your source code to create an inline breakpoint:

```javascript
const addTodo = (e) => {
  debugger; // Execution pauses here when DevTools is open
  e.preventDefault();
  // ...
};
```

**When to use:**

- Temporary debugging during development
- Collaborative debugging (sharing code with breakpoints)
- When you can't easily set breakpoints in DevTools (e.g., minified code)

**Remember:** Remove `debugger` statements before committing code.

## Benefits

- **Faster debugging** - Inspect state without modifying source code
- **Better understanding** - See execution flow through call stack
- **Precise control** - Conditional breakpoints for specific scenarios
- **Cleaner code** - No temporary console.log statements to remove

## Browser Support

- **Firefox:** Built-in debugger (recommended for development)
- **Chrome/Edge:** DevTools Debugger (similar interface and features - found in 'Sources' tab)

## References

- [Firefox Debugger Playground](https://mozilladevelopers.github.io/playground/debugger/)

---

_Configuration tested on Firefox 144.0.2 (64-bit), Chrome 141.0.7390.125 (Official Build) (64-bit), and Edge 142.0.3595.53 (Official build) (64-bit)_
_Last updated: November 2025_
