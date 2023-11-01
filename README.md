# EventDelegation

Now there is only: a single event listener, a single listener function.
Now the browser doesn't have to store in memory two hundred different event listeners and two hundred different listener functions. That's a great for performance`! However, if you test the code above, you'll notice that we've lost access to the individual paragraphs. There's no way for us to target a specific paragraph element.So how do we combine this efficient code with the access to the individual paragraph items that we did before? We use a process called event delegation.
The event object has a .target property. This property references the target of the event. Remember the capturing, at target, and bubbling phases?...these are coming back into play here, too!
Let's say that you click on a paragraph element. Here's roughly the process that happens:

a paragraph element is clicked
the event goes through the capturing phase
it reaches the target
it switches to the bubbling phase and starts going up the DOM tree
when it hits the div element, it runs the listener function
inside the listener function, event.target is the element that was clicked
So event.target gives us direct access to the paragraph element that was clicked. Because we have access to the element directly, we can access its .textContent, modify its styles, update the classes it has - we can do anything we want to it!



