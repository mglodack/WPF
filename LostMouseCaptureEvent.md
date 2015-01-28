### LostMouseCapture Event

This event is really cool because it adds a lot more functionality than LostFocus Event.
Partically looking at losing focus on a WPF UIElement we can use the position of the current UIElement and the position of the mouse.

Let's look at the method.

```LostMouseCapture(object sender, MouseEventArgs e)```

Using `e` from the method above we can use the method `GetPosition(IInputElement relativeTo)`
Most likely your code with look something like this ```var position = GetPosition(this);```

`GetPosition` returns a `Point` with relation to where the current Mouse is, but now what?

Well, we have the ability to compare that `Point` with the dimensions of the UIElement as shown below.
![](/Images/LostMouseCapture Position View.png)

