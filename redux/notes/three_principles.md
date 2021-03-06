# Three principles of redux

Redux can be described with three fundamental principles.

### SINGLE SOURCE OF TRUTH
**The state of your whole application is stored in an object tree within a single store.**

- This makes it easy to create universal apps, as the state from your server can be serialized and hydrated into the client with no extra coding effort.
-  A single state tree also makes it easier to debug or inspect an application; it also enables you to persist your app's state in development, for a faster development cycle. 
-  Some functionality which has been traditionally difficult to implement - Undo/Redo, for example - can suddenly become trivial to implement, if all of your state is stored in a single tree.

### STATE IS READ ONLY
**The only way to change the state is to emit an action, an object describing what happened**.

>This ensures that neither the views nor the network callbacks will ever write directly to the state. Instead, they express an intent to transform the state. Because all changes are centralized and happen one by one in a strict order, there are no subtle race conditions to watch out for. As actions are just plain objects, they can be logged, serialized, stored, and later replayed for debugging or testing purposes.

### CHANGES ARE MADE WITH PURE FUNCTIONS
**To specify how the state tree is transformed by actions, you write pure reducers.**

>Reducers are just pure functions that take the previous state and an action, and return the next state. 

**Remember to return new state objects, instead of mutating the previous state. **

You can start with a single reducer, and as your app grows, split it off into smaller reducers that manage specific parts of the state tree.

 Because reducers are just functions, you can control the order in which they are called, pass additional data, or even make reusable reducers for common tasks such as pagination.