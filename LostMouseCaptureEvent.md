## WPF LostMouseCapture Event vs LostFocus Event

#### Why is there a head to head battle?
Well, my goal was to have an event/action fire whenever my mouse clicked outside the FrameworkElement that currently holds focus. 
I initially assumed that adding the [`LostFocus Event`](https://msdn.microsoft.com/en-us/library/system.windows.uielement.lostfocus(v=vs.110).aspx) would do the job, but I was wrong. Instead there exists another event know
as [`LostMouseCapture`](https://msdn.microsoft.com/en-us/library/system.windows.input.mouse.lostmousecapture%28v=vs.110%29.aspx)

#### Let's look at the method.

```LostMouseCapture(object sender, MouseEventArgs e)```

This awesome event fires anytime a mouse clicks or attempts to capture focus of another space or element on the screen.
This is sweet because we can use `e` from the parameters along with a method [`GetPosition(IInputElement relativeTo)`](https://msdn.microsoft.com/en-us/library/ms591423(v=vs.110).aspx) in order
to compare the position of the mouse with relation to the locaiton of the [FrameworkElement](https://msdn.microsoft.com/en-us/library/system.windows.frameworkelement(v=vs.110).aspx).

Example:

	var position = e.GetPosition(this);
	
#### What does a FrameworkElement look like?

Now that we have the value `position` which is of type `Point`, we can compare that with the dimensions of the FrameworkElement.

![](/Images/LostMouseCapture Position View.png)

