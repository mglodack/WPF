## WPF LostMouseCapture Event vs LostFocus Event

#### Why is there a head to head battle?
Well, my goal was to have an event/action fire whenever my mouse clicked outside the UIElement that currently holds focus. 
I initially assumed that adding the `LostFocus Event` would do the job, but I was wrong. Instead there exists another event know
as [`LostMouseCapture`](https://msdn.microsoft.com/en-us/library/system.windows.input.mouse.lostmousecapture%28v=vs.110%29.aspx)

####Let's look at the method.

```LostMouseCapture(object sender, MouseEventArgs e)```

Using `e` from the method above we can use the method `GetPosition(IInputElement relativeTo)`

Most likely your code with look something like this ```var position = GetPosition(this);```

`GetPosition` returns a `Point` with relation to where the current Mouse is, but now what?

Well, we have the ability to compare that `Point` with the dimensions of the UIElement as shown below.
		![](/Images/LostMouseCapture Position View.png)

