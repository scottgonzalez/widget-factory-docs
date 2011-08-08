# How jQuery UI Works

All jQuery UI widgets have a common API.
We'll walk through the common functionality using a progressbar widget for specific examples.

## Initialization

To initialize a widget, we simply call the plugin on one or more elements.

	$( "#elem" ).progressbar();

This will initialize each element in the jQuery object, in this case the element with an id of "elem".
Because we called the `progressbar()` method with no parameters, the widget is initialized with its default options.
We can pass a set of options during initialization in order to override the default options.

	$( "#elem" ).progressbar({ value: 20 });

We can pass as many or as few options as we want during initialization.
Any options that we don't pass will just use their default values.

## Options

In addition to changing the defaults on initialization, we can change any option at any time.
For example, we can change the progressbar's value to 30 by calling the option method.

	$( "#elem" ).progressbar( "option", "value", 30 );

We can also get the current value for an option.

	$( "#elem" ).progressbar( "option", "value" );

Finally, we can update multiple options at once by passing an object to the option method.

	$( "#elem" ).progressbar( "option", {
		value: 30,
		max: 200
	});

You may have noticed that the option method has the same signature as getters and setters in jQuery core, such as `.css()` and `.attr()`.
The only difference is that you have to pass the string "option" as the first parameter.
This is covered in more detail below.

## Methods

As shown above with the option method, we can call methods on a widget after it has been initialized.
To call a method on a widget, we pass the name of the method to the jQuery plugin.
For example, to call the `value` method on our progressbar widget, we would use:

	$( "#elem" ).progressbar( "value" );

If the method accepts parameters, we can pass them after the method name.
For example, to pass the parameter `40` to the `value` method, we can use:

	$( "#elem" ).progressbar( "value", 40 );

Just like other methods in jQuery, most widget methods return the jQuery object for chaining.

	$( "#elem" )
		.progressbar( "value", 90 )
		.addClass( "almost-done" );

### Common Methods

TODO

## Events

TODO