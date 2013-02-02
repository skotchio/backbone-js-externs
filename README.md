backbone-js-externs
===================

Externs file for backbone for use with Google closure compiler.

This is very much a work in progress.

Starting point is this gist, https://gist.github.com/1847810,
which was auto-generated by DotNetWise's externs extractor tool,
http://www.dotnetwise.com/Code/Externs/index.html.

## Testing the externs

The quick and dirty approach that is currently taken to "testing" the
externs (i.e. ensuring that all necessary Backbone methods are
defined, that they specify the right parameters and return types, etc.)
is to just grab the qunit test code from the Backbone library, specify
some additional externs for qunit, underscore, jquery, and json, and run
the qunit underscore tests through Closure Compiler with advanced
optimizations on.

You can do this for yourself thus.

- install closure compiler
- make sure ruby is installed
- `export CC_PATH={path/to/compiler.jar}`
- from this directory: `cd test && ruby test_externs.rb`

This will spit out a bunch of errors. Many of them are irrelevant,
related to missing jQuery externs, etc., while others indicate genuine
shortcommings (to be rectified) in the Backbone externs file.

## TODO

- get to a stable place with externs for 0.9.2
- externs for 1.0. when it comes out
