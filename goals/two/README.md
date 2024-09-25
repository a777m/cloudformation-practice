## Goal Two

This version is an attempt at making the stack more modular and reusable.
I've not bothered with parameters because they're kind of long to deal with.

Some of the examples here are quite contrived but it's solely for practice
purposes.

Notes:
- Parameters can be put in a json file (not sure if only json is allowed) and
passed directly into the CLI command rather than passing individual params in
the CLI.
- While useful, mappings have not made writing CF any less repetitive. They
function more as global `consts` and in lots of cases make the CF resources
section longer and more verbose.
- Unlike parameters, you cannot add type information to mappings.
- The intrinsic function are nice, also the pseudo params are useful.
- At its core, not having looping (over a while block ForEach is for single
variables) is one of the core pain points of dealing with CF.
