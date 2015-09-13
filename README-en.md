#Erhuo fontend design language

[简体中文版](/README.md)

Erhuo is a fonted design language which compiles to html, depending on [boson](https://github.com/ictxiangxin/boson).
We will continue develop this nice software and open the source on Github.

* The source code is simple
* Erhuo is easy to use

You can consult the example at "./example"

##Table of content：

* [Compiling](#compiling)
* [Syntax](#syntax)
* [TODO](#todo)
* [Example](#example)


##Compiling
Building the documentation requires building the compiler, excute a script:

>`boson.py erhuo.g -l erhuo.l -a lalr -o erhuo.py`

Once you have the compiler built, you can compile a script:

>`erhuo.py example.txt example.html`

`example.html`  is the generated documentation.

##Syntax

* tag-description 
* user-defined function

###tag-description

>`tag { attributes-list ; child-nodes }`

* `attributes-list` and `child-nodes` are divided by `';'`.
* `attributes-list` and `child-nodes` can be NULL.
*  attribute in `attributes-list` are divided by `','`: attribute1, attribute2...
*  attribute can be expressed as : `attribute-name : attribute-value`.
* element in `child-nodes` are divided by `','`.
* element in `child-nodes` can be a new tag-description, function or a string.

For example:

```
div {id: "1", class: "container";
    h4 {; "Hello World"},
}
```

###user-defined function

'let function_name(arguments) = tag-description'

Information may be passed to tag-description via the argument list.

For example:

>`let button(text) = button {class: "btn btn-primary; text"}`

##TODO
* Add variables.
* Add expressions.
* Header file import.

##Example

This is a simple page written by erhuo.

###beform compiling

![Source](http://raw.github.com/ictxiangxin/erhuo/master/example/source.png)

###after compiling

![Source](http://raw.github.com/ictxiangxin/erhuo/master/example/result.png)