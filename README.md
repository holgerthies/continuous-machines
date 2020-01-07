This webpage contains some information on how to access the Coq development for our paper " Continuous and monotone machines".
The formal development has been made part of incone, a Coq library for computable analysis.

## Installation instructions
You should have coq (8.9.0) running with the [Coquelicot](http://coquelicot.saclay.inria.fr/) library (3.0) and from [math-comp](https://math-comp.github.io/math-comp/) (1.9.0) the packages ssreflect and algebra. 

The following libraries have to be installed in this order:
- [mf](https://github.com/FlorianSteinberg/mf/tree/v1.0) 
- [rlzrs](https://github.com/FlorianSteinberg/rlzrs/tree/v1.0)
- [metric](https://github.com/FlorianSteinberg/metric/tree/v1.0)
- [incone](https://github.com/FlorianSteinberg/incone/tree/v1.0)

You can just clone [this](https://github.com/holgerthies/continuous-machines) github repository using `git clone --recurse-submodules` to download all the libraries and then go into the respective folder and run
`make && make install`.

Alternatively if you are using [opam](https://coq.inria.fr/opam-using.html) you can also run 
`opam install . --working-dir` to install all necessary libraries.

## The contents of the paper
Formal proofs of statements in the paper have been made part of the incone library.
The development concerning continuous machines is contained in the `computability` subfolder of the library.


## Scopes and notations.

A general rule of the library is to use natural language to make the theorems as readable as possible.
For concepts where the order of arguments is not clear in prefix notation there is usually an infix notation.
To avoid blocking too many keywords by use of natural language in infix notation the words are connected by underscores and the first one is preceded by a backslash.
The libraries provide scopes for toggling the notations:
`mf_scope`, `baire_scope`, `met_scope` and `cs_scope`, where `mf` is for multi-function, `met` is for metric spaces and `cs` is for continuity spaces, that is represented spaces.
Each scope is delimited by a `%` followed by the phrase before the underscore.
Many of the notations in the different scopes overlap, for instance three of them have a notation `_ \is_continuous` and in some cases the notations are renamed with change of the scope:
For instance the notation `_ \is_continuous` from `baire_scope` is renamed to `_ \is_continuous_operator` in the `cs_scope`.


