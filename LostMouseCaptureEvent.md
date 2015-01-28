### LostMouseCapture Event

This event is really cool because it adds a lot more functionality than LostFocus Event.
Partically looking at losing focus on a WPF UIElement we can use the position of the current UIElement and the position of the mouse.

Let's look at the method.
```LostMouseCapture(object sender, MouseEventArgs e)```
MouseEventArgs provides us with a useful method `GetPosition(IInputElement relativeTo)` that returns a Point of where the current Mouse is.

This is extremely useful information because we can compare the point against the dimensions of the UIElement. 
![](/Images/LostMouseCapture Position View.png)

