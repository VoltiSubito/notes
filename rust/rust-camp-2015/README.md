# [RustCamp 2015](http://rustcamp.com/schedule.html)

## Keynote

### Crater: Tool that detects regressions.
  + Can also be used to investigate which ways the language is being used.

### Plans for better IDE integration
  + Visual Studio
  + Something Else

### Plugins
  
### Other new stuff
  + Cross-compile on cargo build
    + `cargo build --target=arm-linux-androideabi`
  + Cargo install
    + "Like make install, but it works"


## Who Owns this Stream of Data?

#### [Slides](http://cglab.ca/~abeinges/talks/iter/#0)

### Types of iterators
  + IntoIter
    + Moves the data out of the collection
    + You get total ownership
    + Can do anything with data, including destroy it
  + Iter
    + Shares the data in the collection
    + Read-only access
    + Can have many readers at once
  + IterMut 
    + Locans the data in the collection
    + Read-Write access
    + Only one loan at once
  + Drain (I drink your milkshake)
    + Partially moves the data
    + Full access to the elements
    + Doesn't destroy the container

  + StreamingIterator
    + Prevents you from calling next
    + Enables prev, insert, remove


## Learning Systems Programming With Rust

  + Large amount of new Rustaceans are 
    + C/C++ programmers who have been burnt
    + High-level language users who simply haven't had to think about it (me)

#### The Stack
  + Each function call gets a stack frame on the stack
  
  + Can't use the stack for everything
    + stack has limited size
    + memory on the stack only lives as long as the function.
    + memory on the stack requires us to know the needed size
  
#### The Heap
  + All memory is addressed
  + Easy to think of as a giant array
  + Allocate on the heap using Box<T>
  + Dereferencing a pointer is looking up it's location in memory
  + Pointers are signified with '&'
  + Takes a lot of work.
    + figure out size of data and find a spot to store it

#### Reference counting (RC) and Garbage Collection (GC)
  + Rust is stack allocated by default
  + Ruby and Python are heap allocated by default
  + Rust does not have garbage collection
  
  

  