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

We can change options after initialization as well, which we'll see later.

## Methods

After we have initialized our widget, we can call methods on the widget.
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

While each widget will have its own set of unique methods available, there are several methods that exist on all widgets.

#### disable

As you might guess, the `disable` method disabled the widget.
In the case of progressbar, this changes the styling to make the progressbar look disabled.

	$( "#elem" ).progressbar( "disable" );

Calling the disable method is equivalent to setting the `disabled` option to `true`.

#### enable

The `enable` method is the opposite of the `disable` method.

	$( "#elem" ).progressbar( "enable" );

Calling teh enable method is equivalent to setting the `disabled` option to `false`.

#### option

Any option can be changed after initialization through the `option` method.
For example, we can change the progressbar's value to 30 by calling the option method.

	$( "#elem" ).progressbar( "option", "value", 30 );

We can also get the current value for an option.

	$( "#elem" ).progressbar( "option", "value" );

In addition, we can update multiple options at once by passing an object to the option method.

	$( "#elem" ).progressbar( "option", {
		value: 100,
		disabled: true
	});

You may have noticed that the `option` method has the same signature as getters and setters in jQuery core, such as `.css()` and `.attr()`.
The only difference is that you have to pass the string "option" as the first parameter.

#### destroy

If you no longer need the widget, you can destroy it and return back to the original markup.

	$( "#elem" ).progressbar( "destroy" );

Once you destroy a widget, you can no longer call any methods on it unless you initialize the widget again.
If you're removing the element, either directly via `.remove()` or by modifying an ancestor with `.html()` or `.empty()`, the widget will automatically destroy itself.

#### widget

TODO

## Events

TODO
