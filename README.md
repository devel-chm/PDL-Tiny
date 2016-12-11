PDL-Tiny
========

A minimal version of Perl Data Language and a test bench to develop a new PDL::NG core

========

NOTE: I had envisioned a PDL::Tiny module which encompassed a minimalist
core of PDL::NG (Next Gen) capability.  However, on reading more about 
other Tiny modules, it appears that this usage is not consistent with the
[Tiny manifesto](http://search.cpan.org/~dmuey/Acme-Tiny-0.6/lib/Acme/Tiny.pod).

Consequently, the actual module naming is still TBD but the project is
still PDL-Tiny.

========

The PDL-Tiny project has a number of goals:

1. To provide KISS capability for perl computation with PDL compatibility
2. To architect and implement a new new PDL::NG ("next generation") core
3. To support rapid updates and releases to speed developement
4. To refine the definition of PDL::Tiny and PDL:NG requirements


Some general directions for PDL-Tiny (and PDL:NG) implementation:

1. Use "modern" perl5 OO support with Moo
  * Maintain interoperability with new p5 OO development
  * Smooth compatibility with perl6
2. Decompose PDL functionality into Roles
  * Roles would allow expression of PDL::NG features
  * Cross-cutting concerns could be implemented separately
  * Using roles means you could load just the features you need saving memory and reducing complexity
  * Maybe use Roles applied to objects as basis for JIT computation and performance optimization
3. Should interoperate with PDL-2.x
  * Could we use 'handles' to delegate to PDL-2.x?
  * That would allow gradual development for the new features
  * Allow for interoperability, test ability, maybe regression and verification
4. We could start with a perl-only implementation
  * This gives the outline of the implementation
  * Features first and then performance
  * Using PDL-2.x delegation to get performance
  * Migrate to new C/XS performance as available
5. Unify Perl OO layer with C/XS computation layer
  * Provide symmetric operation from C or Perl (similar to Prima)
  * Provide a C FFI for PDL::NG to enable use from multiple languages/libraries
  * Propose using the [C Object System (COS)](https://github.com/CObjectSystem/COS).
6. Improved types support
  * All standard atomic types (NumPy and Python set as a start)
  * All [OenGL data types](https://www.opengl.org/wiki/OpenGL_Type)
  * Support N-D arrays of structures
  * Support more flexible indexing (e.g. strings, field names,...)
  * Support metadata for objects, and dimensions/axes:
    * Units
    * Axis types (row, col, x, y) or labels for improved threading control/syntax
    * Model after [HDF5](https://support.hdfgroup.org/HDF5/doc1.6/UG/13_Attributes.html)

