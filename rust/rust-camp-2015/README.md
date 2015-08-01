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

  
## Rust in Production

### Rust + Infrastructure Services
  + Networking firewall
  + Container and snapshot ancestry traking
  + Cluster job and container scheduler
  
### Thrift
  + Thrift for RPC
  + Uses traits and macros
  + Generated code takes time to build
  
### Postgres
  + postgres on creates.io (driver)
  + Use cargo to setup and teardown db, server
  + Interaction with db is type driven, only strings are strings
  + FromSql/ToSql function as a super-thin "ORM"
  
### Reliable Rust
  + Use type system to your advantage
  + String-typing causes an excessive number of bugs
  + Factor code using generics, not macros (when possible)
  + Keep 'unsafe' contained and tested
  + User RAII/borrowing for all resource management
    + Used for access to database
  + Avoid trait objects
    + Inflexible, bad interactions with OIBITs
  + Be very careful with panics
  + Unify concepts using traits as much as possible
  + Design interfaces conservatively
    + Take inspiration from std
    + Private fields with accessors > public fields
    + Use From/AsRef/Into to extend APIs
    + Result often > Option
    + Errors as types with typed metadata, not strings
  + Use Cargo
    + Many crates break on 0.x releases, pin versions
    + Use [[bin]]s for utility tasks
    + Use build.rs to build assets, templates, thrift codegen.
    + Split code into crates + path deps for faster builds


## Graphite-Rust: A Fast Time Series Database Implementation

### Graphite
  + Long-lived time series (one server over 2 years)
  + Regular update intervals
  + Can use '*' to query against multiple names
  + Doesn't store < 1s
  + Graphite-Web
    + Read-only access to database
    + HTML interface for rendering queries
    + REST-y services
  + Carbon
    + Daemon for recording datapoints
  + Whipser
    + bytes on disk
    + Downsamples on write (sec -> minute -> hour etc...)


## Navigating the Open Seas

  + Developing in the open is becoming more common
    + Like Go
  + Not all open source languages are developed in the open
    + Like .NET
  
### Exploring Rust history
  + Mailing list
    + Tag became Enum
  + Git history
    + Lifetime Elision
    + use `git grep` 
      + `git grep -i "lifetime elision"`
      + `git log [file]` -- Too much information
      + `git blame [file]` -- Still too much information
      + `git blame -L [range] [file]`
      + `git blame [SHA] [file]`
      + `git blame -L [regex] [SHA] [file]`
  + Git Pickaxe
    + `git log -Siface` ("`-S` Does not look like an axe")
  + Air Mozilla
  + Old GitHub wiki is now `rust-lang/rust-wiki-backup`
  + What happens when GitHub goes away?
  + Lost IRC logs because irclog.gr went away
  