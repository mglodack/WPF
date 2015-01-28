## WPF LostMouseCapture Event vs LostFocus Event

#### Why is there a head to head battle?
Well, my goal was to have an event/action fire whenever my mouse clicked outside the FrameworkElement that currently holds focus. 
I initially assumed that adding the `LostFocus Event` would do the job, but I was wrong. Instead there exists another event know
as [`LostMouseCapture`](https://msdn.microsoft.com/en-us/library/system.windows.input.mouse.lostmousecapture%28v=vs.110%29.aspx)

#### Let's look at the method.

```LostMouseCapture(object sender, MouseEventArgs e)```

This awesome event fires anytime a mouse clicks or attempts to capture focus of another space or element on the screen.
This is sweet because we can use `e` from the parameters along with a method `GetPosition(IInputElement relativeTo)` in order
to compare the position of the mouse with the locaiton of the [FrameworkElement](https://msdn.microsoft.com/en-us/library/system.windows.frameworkelement(v=vs.110).aspx).

Example:

	var position = e.GetPosition(this);
	
#### What does a FrameworkElement look like?

Well, we have the ability to compare that `Point` returned from the method `GetPositio` with the dimensions of the FrameworkElement.

![](/Images/LostMouseCapture Position View.png)

