#debugging #error #cSHARP #JavaScript 

 You might have a long list of possible assumptions! Here are a few questions to ask yourself to challenge your assumptions.

- Are you using the right API (that is, the right object, function, method, or property)? An API that you're using might not do what you think it does. (After you examine the API call in the debugger, fixing it can require a trip to the documentation to help identify the correct API.)

- Are you using an API correctly? Maybe you used the right API but didn't use it in the right way.

- Does your code contain any typos? Some typos, like a simple misspelling of a variable name, can be difficult to see, especially when working with languages that don’t require variables to be declared before they’re used.

- Did you make a change to your code and assume it's unrelated to the problem that you're seeing?

- Did you expect an object or variable to contain a certain value (or a certain type of value) that's different from what really happened?

- Do you know the intent of the code? It's often more difficult to debug someone else's code. If it's not your code, it's possible you might need to spend time learning exactly what the code does before you can debug it effectively.

- Use unit test to keep code healthy [[Unit testing with NUnit.Framework]]

[Debugging basics](https://learn.microsoft.com/en-us/visualstudio/debugger/debugging-absolute-beginners?view=vs-2022&tabs=csharp)
[Debugging techniques](https://learn.microsoft.com/en-us/visualstudio/debugger/write-better-code-with-visual-studio?view=vs-2022)
[Watch Window](https://learn.microsoft.com/en-us/visualstudio/debugger/watch-and-quickwatch-windows?view=vs-2022)
[Immediate Window](https://learn.microsoft.com/en-us/visualstudio/ide/reference/immediate-window?view=vs-2022)
