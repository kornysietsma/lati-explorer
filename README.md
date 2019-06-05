# LATI Toxicity Explorer

For visualising Language-agnostic Toxicity indicators

This is intended to be used in conjunction with the [lati-scanner](http://github.com/kornysietsma/lati-scanner) tool 
which produces the data used for visualisation.  See that repo for instructions for installing and running both tools.

Click [here](https://kornysietsma.github.io/lati-explorer/) to see a live demo with simple data.

A fairly simple treemap to view simple language-agnostic indicators of where you might have toxic code:

- Lines of code
- Age since last change
- Number of authors

These are fairly simple indicators that just point you in the general direction
of toxic code.  They should not be mistaken for code quality metrics!

However, they have the huge advantage that they can be determined in an almost
language-agnostic way, and quite quickly.

## About the code

This code is originally based on some thrown-together work several years ago - produced using sample
d3 code and some very simple glue scripts in 2 or 3 days of frantic work.

It is far from perfect - it's been cleaned up but has some ugly warts around
state management, still needs a fair bit of lovin'

My D3 approach is covered in more detail at https://github.com/kornysietsma/d3-modern-demo :

- native es6, this won't work on any browser more than a few months old!
Specifically, it needs es6 module support - https://caniuse.com/#feat=es6-module - so no IE support for a start.
- it uses css grids in a fairly basic way, similarly needing a new browser
- it tries to prefer immutable data structures using immutable.js - actually I gave up
and used mutating state in several areas, as d3 mutates things all over the place.

Run 'simple_server.sh' to view the demo on your local machine - or run the [lati-scanner](http://github.com/kornysietsma/lati-scanner) tool in "server" mode to view data from a real project.  See the readme of that project for instructions.

## About the npm package stuff

This is purely so I can run `eslint` as I develop - there's no NPM in this codebase at the moment, everything is downloaded locally to keep things simple.  One day it should be npm-ized, but that day is not today.
