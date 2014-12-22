PDL-Tiny
========

A minimal version of Perl Data Language and a test bench to develop a new PDL3 core

========

The PDL-Tiny project has a number of goals:

1. To provide KISS capability for perl computation with PDL compatibility
2. To architect and implement a new new PDL3 core
3. To support rapid updates and releases to speed developement
4. To rapidly refine the definition of PDL::Tiny and PDL3 requirements


Some general directions for PDL-Tiny (and PDL3) implementation:

1. Use "modern" perl5 OO support with Moo
2. Decompose PDL functionality into Roles
3. Should interoperate with PDL-2.x
4. Maybe it could support a perl-only implementation
