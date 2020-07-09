# python-prefix_compression
Why not explicitly be weak on naming?

# what does it accomplish or support?

Provide a memory neutral and fast implementation that is clear to understand and works for the use case of extracting a common prefix of a sequence of strings and yielding that prefix and a generator for the compressed strings of the original sequence.

The latter is not yet clear. One simple implementation path is to receive a reference to a sequence, determine min-max, compare min to max by character and break with first index of enumaeration not matching. Finally yield first the prefix, subsequently all strings of the sequence each shortened by the prefix.

Another still open question is, if a composition of functions can be construed, such that the prefix finding algorithm respects a caller provided policy representing the inner structure of the strings.
 An example for an inner structure is a sequence of paths as strings. A path policy would provide a separator that modifies the prefix finding algorithm to backtrack to the previous such separator token.

why? well, imagine the sequence ˋ'bar/baz', 'bar/bazaar'ˋ and a path policy providing the boolean predicate ˋlambda x: x == '/'ˋ should not yield ˋ'bar/baz', '', 'aar'ˋ but instead ˋ'bar/', 'baz', 'bazaar'ˋ.

Note: the name of the default branch (with special meaning for github and gitlab users) is ˋdefaultˋ :wink:.
