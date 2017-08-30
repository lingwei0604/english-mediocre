UIView
-----
An object that manages the content for a rectangular area on the screen.

OverView
-----
Views are the fundamental building blocks of your app's user interface,and the UIView class defines behaviors that are common to all views,A view object renders content within its bounds rectangle and handles nay interactions with that content, The UIView class is a concrete class that you can instantiate and use to display a fixed background color,You can also subclass it to draw more sophisticated content,To display labels,images,buttons,and other interface elements commonly found in apps,use the view subclass provided by the UIKit framework rather than trying to define your own.


Because view objects are the main way your application interacts with the user,they have a number of responiblilities,Here are just a few:
	Drawing and animation:
		View draw content in their rectangular area using UIKit or Core Graphics.
		Some view properties can be animated to new values.
	Layout and subview management
		Views may contain zero or more subviews.
		Views can adjust the size and positon of their subveiws.
		Use Auto Layout to define the ruels for resizing and repostioning your views in response to changes in the view hierarchy.
	Event handing
		A view is a subclass of UIResponder and can respond to touch an d other types of events.
		View can install gesture recognizers to handle common gestrues.


Views can be nested inside other views to create view hierarchies,which offer a convenient way to organize related content, Nesting a view creates a parent-child relationship between the child view being nested(know as the subview) and the parent(know as the superview),A parent view may contain any number of subviews but each subview has only one superview,By default,when a subveiws's visible area extends outside of the bounds of its superview,no chipping of the subviews'c content occurs,Use the clipToBounds protperty to change that behavior.

The geometry of each view is defined by its frame and bounds properties,The frame property defines the origin and dimensions of the view in the coordinate system of its superview,The almost exclusively in custom drawing code,The center property provides a convenietn way to repostion a view without changing its frame or bounds properties directly.

For detailed inforation about how to use the UIView class, see View Programming Guide for iOS.


Creating a View

Normally,you create views in your storyboards by dragging them from the library to your canvas,You can also create views programmatically. when creating a view,you typically specify its initial size and position realtive to its future superview,For example,the following example creates a view an places its top-left corner at the point(10,10) in the superview's coordinate system(once it is added to that superview).

To add a subview to aother view, call the addSubView(_:) method on the superview,You may add any number of subviews and sibing views may overlap each other without any issue on iOS, Each call to the addSubView(_:) method places the new view to top of all other siblings,You can specify the relative z-roder of subviews adding it using the insertSubview(_:aboveSubview:)and insertSubView(:_belowSubview:) methods,You can also exchange the postion of already added subviews using the exchangeSubview(at:withSubViewAt:) method.

After creating a view, create Auto Layout rules to govern how the size and postion of the view change in response to changes in the rest of the view hierarchy.For more information,see Auto Layout Guide.

			

























