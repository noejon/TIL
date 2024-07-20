# Functions VS Arrow functions

This is something that I once knew and forgot about, the big difference between functions and arrow functions.

When declaring a `function` that function has it's own `this` context:

An arrow function (`() => {}`) does not have their own `this` context, they use that of their parent context instead:
