# hara

Stateful data structures for clojure.

### Huh?

<i>Isn't the whole point of clojure to move to a more functional style of programming using immutable data structures?</i>

Yes. Exactly. Clojure has rid of alot of complexity on the jvm by requiring the programmer to think functionally. However, the issue of shared state is still a problem in multithreaded applications. Clojure has `ref`s and `atom`s to resolve this issue but they tend to be a little basic.

A typical use case of stored state is an atom with a array containing data:
 - Data can be added or removed from the array
 - The data itself can be also changed
 - The data has to be accessible by a number of threads

In the case above, the best option would be to construct an atom containing an array of atoms containing data. What hara offers is essentially functions that manipulate this structure (which is given the name 'ova').

### Installation:

In project.clj, add to dependencies:

     [hara "0.6.1"]


## Ova

There is `hara.ova`, the main data structure supporting state-based manipulation of records. Its a useful structure to have as a shared state. I use it as a transactional general purpose store that is the intermediary between the main application, the database and the web presentation layer when there is a need for data to be stored in memory and acted upon in some way by multiple threads.


## TODOS:

- Fix up the readme to include more examples:
  - load/save from korma
  - search - DONE
  - update based upon a predicate - DONE

- Do unit tests for hara.data.dyna-rec - DONE



## License

Copyright © 2012 Chris Zheng

Distributed under the Eclipse Public License, the same as Clojure.
