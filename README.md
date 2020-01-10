This webpage contains some information on how to access the Coq development for our paper " Continuous and monotone machines".
The formal development has been made part of incone, a Coq library for computable analysis.

## Installation instructions
You should have coq (8.9.0) running with the [Coquelicot](http://coquelicot.saclay.inria.fr/) library (3.0) and from [math-comp](https://math-comp.github.io/math-comp/) (1.9.0) the packages ssreflect and algebra. 

The following libraries have to be installed in this order:
- [mf](https://github.com/FlorianSteinberg/mf/tree/v1.1) 
- [rlzrs](https://github.com/FlorianSteinberg/rlzrs/tree/v1.1)
- [metric](https://github.com/FlorianSteinberg/metric/tree/v1.1)
- [incone](https://github.com/FlorianSteinberg/incone/tree/v1.1)

You can just clone [this](https://github.com/holgerthies/continuous-machines) github repository using `git clone --recurse-submodules`, change into the top directory and run `make` to install all four libraries.

Alternatively if you are using [opam](https://coq.inria.fr/opam-using.html) you can also run 
`opam install . --working-dir` to install all necessary libraries.

## The contents of the paper
Formal proofs of statements in the paper have been made part of the library and are scattered across several files and folders.

A good overview over how many of the main concepts from the paper are formalized can be ganed by looking at the example of representing real numbers using rational approximations (Example 2.2 in the paper) contained in [examples/Q_reals.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/examples/Q_reals.v) in the incone library.

Further results and examples of the paper can be roughly related to the formalization as follows:
- Represented spaces as introduced in Section 2 are called *continuity spaces* in incone. Results on continuity spaces are contained in the `continuity_spaces` folder of the incone library. 
  - The notion of representation and other basic definitions are contained in the file [continuity_spaces/representation.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/continuity_spaces/representation.v)
  -  The representation for discrete spaces (Example 2.1) is contained in the file [continuity_spaces/discr.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/continuity_spaces/discr.v)
  - Continuity is defined in  [continuity_spaces/cont.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/continuity_spaces/cont.v). 
  - the Kleeneans as defined in Example 2.3 are introduced in the file [continuity_spaces/hyperspaces.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/continuity_spaces/hyperspaces.v) in the Section `Kleeneans`. This file also contains Example 2.4.
  - The second part of Example 2.3 (the sign function) is defined in the beginning of the [examples/Q_reals.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/examples/Q_reals.v) file.
  - Isomorphy (Section 2.2) is defined in  [continuity_spaces/iso.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/continuity_spaces/iso.v)
- Statements and Definitions about multifunctions described in the first part of Section 3 are contained in the [mf](https://github.com/FlorianSteinberg/mf/tree/v1.1) sublibrary.
- Realizability (Section 3.1) is contained in the [rlzrs](https://github.com/FlorianSteinberg/rlzrs/tree/v1.1) sublibrary.
- The definition of the modulus function from Section 4 can be found in  [continuity_spaces/cont.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/continuity_spaces/cont.v).
- The results in Sections 3 and 4 concerning continuous and monotone machines are mostly contained in the `computability` subfolder of incone.
  - The F operator from Section 3.2 is defined in [computability/FMop.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/continuity/FMop.v).
  - The extensive example in Section 3.3 (Inversion in the rational representation) is contained in the file [examples/reals/division_for_Q_reals.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/examples/reals/division_for_Q_reals.v).
  - Continuous machines (Section 4) are defined in [computabiliy/continuous_machines.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/computabiliy/continuous_machines.v)
  - The main results in this chapter are formalized in [computability/classical_mach.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/computability/classical_mach.v).
  - Montone machines and their composition (Chapter 4.2) are treated in [computability/monotone_machines.v](https://github.com/FlorianSteinberg/incone/tree/v1.1/computability/monotone_machines.v).
