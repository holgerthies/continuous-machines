This webpage contains some information on how to access the Coq development for our paper " Continuous and monotone machines".
The formal development has been made part of incone, a Coq library for computable analysis.

## Installation instructions
You should have coq (8.9.0) running with the [Coquelicot](http://coquelicot.saclay.inria.fr/) library (3.0) and from [math-comp](https://math-comp.github.io/math-comp/) (1.9.0) the packages ssreflect and algebra. 

The following libraries have to be installed in this order:
- [mf](https://github.com/FlorianSteinberg/mf/tree/v1.1) 
- [rlzrs](https://github.com/FlorianSteinberg/rlzrs/tree/v1.1)
- [metric](https://github.com/FlorianSteinberg/metric/tree/v1.1)
- [incone](https://github.com/FlorianSteinberg/incone/tree/v1.1)

You can just clone [this](https://github.com/holgerthies/continuous-machines) github repository using `git clone --recurse-submodules` to download all the libraries and then go into the respective folder and run
`make && make install`.

Alternatively if you are using [opam](https://coq.inria.fr/opam-using.html) you can also run 
`opam install . --working-dir` to install all necessary libraries.

## The contents of the paper
Formal proofs of statements in the paper have been made part of the library and are scattered across several files and folders.
Basic definitions and results about multifunctions and realizability as outlined in Sections 2 and 3 of the paper are contained in the [mf](https://github.com/FlorianSteinberg/mf/tree/v1.1)  and [rlzrs](https://github.com/FlorianSteinberg/rlzrs/tree/v1.1) sublibraries, respectively.
The remaining development is mostly part of the [incone](https://github.com/FlorianSteinberg/incone/tree/v1.1) main library.

The results and examples of the paper can be roughly related to the formal results as follows:

Most of Section 2 is contained in the continutiy folder of the incone library.
In particular, Example 2.1 is contained in the file [continuity_spaces/discr.v](), the definition and properties of a modulus function is defined in the file [continuity_spaces/cont.v]() and the Kleeneans as defined in Example 2.3 are introduced in the file [continuity_spaces/hyperspaces.v]().
The representation of the reals using rational approximations from Example 2.2 is contained in the file [examples/Q_reals.v]().

The results in Sections 3 and 4 concerning continuous and monotone machines are mostly contained in the `computability` subfolder.
The F operator from Section 3.2 is defined in [continuity/FMop.v]().
The xtensive example in Section 3.3 (Inversion in the rational representation) is contained in the file [examples/reals/division_for_Q_reals.v]().
Continuous machines (Section 4) are defined in [computabiliy/continuous_machines.v]() and the main results in this chapter are formalized in [computability/classical_mach.v]().
