
This is a way to track mouse position.     You decide how to use it.




1. The mousemove handler function receives an event as parameter that contains the mouse coordinates as clientX and clientY properties. You can provide a position update by calling the state setter setMousePosition with the new values.


2. The MousePosition component receives a render prop, which is the special prop name designed by convention to specify a function that returns some JSX. Since the MousePosition component does not take care of any visualization logic, but rather encapsulates cross-cutting concerns, it should return the result of calling the render function with the mousePosition as an argument. In other words, it’s up to the components that consume MousePosition to specify what sort of UI they want to display when they receive a new value of the mouse position on the screen. 

3. The PanelMouseLogger component should not receive any props. Hence, the early return from the previous implementation if no props were provided is no longer needed.

Instead, the mousePosition is now injected as the first argument of the render function prop that MousePosition uses. It’s in this render function body where the previous JSX should be extracted and returned. 


