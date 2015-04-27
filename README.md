# Draggable View

Create a draggable view that is similar to Tinder's in Xamarin.iOS.

## Installation

1. Copy the DraggableView folder to your project.
2. Code away.

## Example

#####Create a DraggableImageView and add a view:
``` 
var draggableImageView = new DraggableImageView (UIImage.FromFile ("jondavis.jpg"), new CGRect (5, 20, 300, 354));
``` 
#####Wire up the swipe event:
``` 
DraggableImageView.OnSwipe += HandleOnSwipe;
``` 
#####Handle the swipe event:

```
private void HandleOnSwipe (object sender, DraggableEventArgs evt)
{
	if (!evt.Dragged.Equals (DraggableDirection.None)) {
		var message = evt.Dragged.Equals (DraggableDirection.Left) ? "You Chose Poorly" : "You Swiped Right";
		new UIAlertView ("Swiped", message, null, "OK", "OK").Show ();
	}
}
```


