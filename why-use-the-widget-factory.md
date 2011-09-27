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
removing the boilerplate and creating and creating a consistent API across plugins.
