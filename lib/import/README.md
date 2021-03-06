These are the header files that one can use to call C functions from the standard library. Some header files however (like `string.h`, for example), don't call C functions at all; instead, they have the implementation of the functions that we're calling written in Sasm itself.

While the value of a label can be assigned to the PC with `call`, macros can't be used with `call`. One has to just write the name of the label prefixed with a `%`.

For example, to expand the `std_io_puts` macro, do this: `%std_io_puts`.

The `%` expands the macro.

You'll also see that some header files have things like this:

````
$if SYM 42
/ ... /
$fi
````

those are there for conditional compilation.


As a side note: It doesn't matter if a marco and a label have the same name, since macros are deleted after the symbol replacement phase anyway.
