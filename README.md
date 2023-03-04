(This extension is archived so Ren-C can focus on other issues.)

## GOB! EXTENSION

The purpose of a GOB! was to be a more efficient data structure for
manipulating a DOM-like heirarchy of items than trying to maintain a
linked structure of Rebol values--e.g. with a parent and owner link
done by object reference, and with lists of children having to be
maintained as BLOCK!s.  They have a fixed set of fields (including
those related to coordinates, styles, and effects) but one of those 
fields provides for storing arbitrary data.

In order to export the data type, it was switched to a compromise of
using arrays for the list of children, while using compact structures
for coordinates and flags.  Tradeoffs were made to keep GOB!s on
the same order of magnitude as R3-Alpha, but able to build on more
generally vetted code paths in the system.

For a long time, Ren-C kept the type around, while moving its implementation
out of the core...to serve as an example of how one might define a new 
datatype in an extension:

  https://forum.rebol.info/t/user-defined-datatype-discussion/1203

Proposals for a more generic NODE! type have been put forth, which would
make more sense than having so many flags hardcoded for GUI purposes:

  https://forum.rebol.info/t/multiply-linked-lists/1441
  https://github.com/red/red/wiki/%5BPROP%5D-Node!-datatype
