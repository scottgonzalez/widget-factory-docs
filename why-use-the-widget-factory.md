# Why Use the Widget Factory

Writing jQuery plugins is as simple as adding a method to `jQuery.prototype`
(more commonly seen as `$.fn`) and following some simple conventions like returning `this` for chainability.
So why does the widget factory exist? And why is it hundreds of lines of code?

In this document, we'll walk through the benefits of the widget factory and find out
when and why it makes sense to use it.

## Stateless vs. Stateful Plugins

Most jQuery plugins are stateless; they perform some action and their job is done.
For example, if you set the text of an element using `.text( "hello" )`,
there is no setup phase and the result is always the same.
For these types of plugins, it makes sense to just extend jQuery's prototype.

However, some plugins are stateful; they have full life cycles, maintain state, and react to changes.
These plugins require a lot of code dedicated to initialization and state management (and sometimes destruction).
This results in a lot of boilerplate for building stateful plugins.
Even worse, each plugin author may manage life cycles and state differently,
resulting in different API styles for differnet plugins.
The widget factory aims to solve both problems,
removing the boilerplate and creating a consistent API across plugins.

## Consistent API

The widget factory defines how to create and destroy widgets,
how to get and set options, how to invoke methods,
and how to listen to events triggered by the widget.
By using the widget factory to build your stateful plugins,
you're automatically conforming to a defined standard,
making it easier for new users to start using your plugins.
In addition to defining the interface,
the widget factory also implements much of this functionality for you.
If you're not familiar with the API provided by the widget factory,
you should read [How jQuery UI Works](how-jquery-ui-works.md).
