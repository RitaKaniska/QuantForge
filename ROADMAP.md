# Standard Library From Scratch — 24-Week Roadmap

This project is a guided journey through implementing core C++ standard-library ideas from scratch. The goal is not to replace the standard library, but to understand its data structures, ownership models, generic programming techniques, correctness guarantees, and performance tradeoffs by building small, focused versions.

Use each week's section as a checklist. For every component, also work through the reusable implementation checklist at the end of this guide.

## Week 1 — Raw memory and object lifetime

**Detailed guide:** [Week 1 — Raw Memory & Object Lifetime](guides/week-01-raw-memory-and-object-lifetime.md)

- [ ] Learn allocation vs. construction
- [ ] Practice placement construction
- [ ] Practice `std::construct_at` / `std::destroy_at`
- [ ] Build `Tracked`, `MoveOnly`, and `ThrowOnCopy` test types
- [ ] Understand the Rule of Five
- [ ] Test with sanitizers

## Week 2 — `vector<T>`: storage

**Detailed guide:** [Week 2 — `vector<T>`: Storage](guides/week-02-vector-storage.md)

- [ ] Implement raw storage management
- [ ] Implement size / capacity
- [ ] Implement constructors / destructor
- [ ] Implement copy constructor
- [ ] Implement move constructor
- [ ] Implement copy assignment
- [ ] Implement move assignment
- [ ] Implement `reserve`
- [ ] Implement `emplace_back`
- [ ] Understand vector growth strategy

## Week 3 — `vector<T>`: complete version

**Detailed guide:** [Week 3 — `vector<T>`: Complete Version](guides/week-03-vector-complete.md)

- [ ] Implement `begin` / `end`
- [ ] Implement `const_iterator`
- [ ] Implement `operator[]`
- [ ] Implement `front` / `back`
- [ ] Implement `push_back`
- [ ] Implement `pop_back`
- [ ] Implement `insert`
- [ ] Implement `erase`
- [ ] Implement `clear`
- [ ] Implement `swap`
- [ ] Study iterator invalidation
- [ ] Study exception safety during reallocation
- [ ] Benchmark against `std::vector`

## Week 4 — `unique_ptr<T>` and RAII

**Detailed guide:** [Week 4 — `unique_ptr<T>` and RAII](guides/week-04-unique-ptr-raii.md)

- [ ] Implement `unique_ptr<T>`
- [ ] Make it move-only
- [ ] Implement `operator*`
- [ ] Implement `operator->`
- [ ] Implement `get`
- [ ] Implement `release`
- [ ] Implement `reset`
- [ ] Implement `swap`
- [ ] Support custom deleters
- [ ] Learn EBO / `[[no_unique_address]]`
- [ ] Implement a small scope guard

## Week 5 — `list<T>`

**Detailed guide:** [Week 5 — `list<T>`](guides/week-05-list.md)

- [ ] Design sentinel-node representation
- [ ] Implement node allocation
- [ ] Implement bidirectional iterator
- [ ] Implement `const_iterator`
- [ ] Implement `begin` / `end`
- [ ] Implement `push_front` / `push_back`
- [ ] Implement `emplace`
- [ ] Implement `insert`
- [ ] Implement `erase`
- [ ] Implement `clear`
- [ ] Implement `splice`
- [ ] Study iterator stability

## Week 6 — `deque<T>`: segmented storage

- [ ] Understand `std::deque`-style segmented memory
- [ ] Design block layout
- [ ] Design block-pointer map
- [ ] Implement allocation of blocks
- [ ] Implement `push_back`
- [ ] Implement `push_front`
- [ ] Implement `pop_back`
- [ ] Implement `pop_front`
- [ ] Implement `operator[]`

## Week 7 — `deque<T>`: iterators and API

- [ ] Implement random-access iterator
- [ ] Implement iterator arithmetic across blocks
- [ ] Implement `begin` / `end`
- [ ] Implement `const_iterator`
- [ ] Implement `insert`
- [ ] Implement `erase`
- [ ] Implement `resize`
- [ ] Study deque iterator invalidation
- [ ] Benchmark against `std::deque`

## Week 8 — `string` and `string_view`

- [ ] Implement owning string storage
- [ ] Maintain null terminator correctly
- [ ] Implement size / capacity
- [ ] Implement `append`
- [ ] Implement `insert`
- [ ] Implement `erase`
- [ ] Implement `find`
- [ ] Implement comparisons
- [ ] Implement `string_view`
- [ ] Understand owning vs. non-owning types
- [ ] Implement Small String Optimization as a stretch goal

## Week 9 — Heap and container adaptors

- [ ] Implement `make_heap`
- [ ] Implement `push_heap`
- [ ] Implement `pop_heap`
- [ ] Implement heap-based `priority_queue`
- [ ] Support custom comparator
- [ ] Implement `stack` adaptor
- [ ] Implement `queue` adaptor
- [ ] Understand container adaptor design

## Week 10 — Red-Black Tree engine

- [ ] Design reusable tree node
- [ ] Implement BST search
- [ ] Implement successor / predecessor
- [ ] Implement tree iterator
- [ ] Implement rotations
- [ ] Implement insertion balancing
- [ ] Implement deletion
- [ ] Implement deletion balancing
- [ ] Verify Red-Black Tree invariants

## Week 11 — `set` / `map`

- [ ] Build `set` on top of tree engine
- [ ] Build `map` on top of tree engine
- [ ] Implement `lower_bound`
- [ ] Implement `upper_bound`
- [ ] Implement `find`
- [ ] Implement `insert`
- [ ] Implement `erase`
- [ ] Support custom comparator
- [ ] Understand comparator equivalence
- [ ] Study iterator guarantees

## Week 12 — Robin Hood hash table

- [ ] Design flat bucket representation
- [ ] Choose metadata representation
- [ ] Implement hashing
- [ ] Implement probing
- [ ] Track probe distance
- [ ] Implement Robin Hood insertion
- [ ] Implement lookup
- [ ] Implement rehashing
- [ ] Understand load factor

## Week 13 — Production-ish hash map

- [ ] Implement deletion
- [ ] Compare tombstones vs. backward-shift deletion
- [ ] Implement iterators
- [ ] Implement `reserve` / `rehash`
- [ ] Test bad hash functions
- [ ] Test high load factors
- [ ] Benchmark successful lookup
- [ ] Benchmark failed lookup
- [ ] Benchmark insertion
- [ ] Compare against `std::unordered_map`
- [ ] Analyze cache locality

## Week 14 — `optional<T>` and `expected<T, E>`

- [ ] Implement manual storage for `optional`
- [ ] Track engaged / disengaged state
- [ ] Implement construction / destruction
- [ ] Implement copy / move semantics
- [ ] Implement value access
- [ ] Implement `emplace`
- [ ] Implement `reset`
- [ ] Implement simplified `expected<T, E>`
- [ ] Understand discriminated storage

## Week 15 — `variant<Ts...>`

- [ ] Compute maximum storage size
- [ ] Compute maximum alignment
- [ ] Store active type index
- [ ] Implement construction
- [ ] Implement destruction
- [ ] Implement copy
- [ ] Implement move
- [ ] Implement `get<I>`
- [ ] Implement `get<T>`
- [ ] Implement `visit`
- [ ] Practice variadic templates

## Week 16 — `pair`, `tuple`, and type traits

- [ ] Implement `pair`
- [ ] Implement small `tuple`
- [ ] Implement `get<I>`
- [ ] Implement `get<T>`
- [ ] Learn `index_sequence`
- [ ] Practice parameter packs
- [ ] Implement several simple type traits
- [ ] Practice SFINAE / `requires`
- [ ] Review perfect forwarding

## Week 17 — `function<R(Args...)>`

**Detailed guide:** [Week 17 — `function<R(Args...)>`](guides/week-17-function.md)

- [ ] Understand type erasure
- [ ] Store arbitrary callable objects
- [ ] Implement callable dispatch
- [ ] Implement destruction dispatch
- [ ] Implement copy dispatch
- [ ] Implement move dispatch
- [ ] Implement `operator()`
- [ ] Support function pointers
- [ ] Support lambdas
- [ ] Add Small Buffer Optimization
- [ ] Benchmark heap vs. SBO cases

## Week 18 — `shared_ptr<T>`

- [ ] Design control block
- [ ] Implement strong reference count
- [ ] Implement shared ownership
- [ ] Implement copy
- [ ] Implement move
- [ ] Implement `reset`
- [ ] Implement custom deleter
- [ ] Understand aliasing concerns
- [ ] Test complex ownership graphs

## Week 19 — `weak_ptr<T>` and `make_shared`

- [ ] Add weak reference count
- [ ] Implement `weak_ptr`
- [ ] Implement `lock()`
- [ ] Handle object destruction separately from control-block destruction
- [ ] Implement `make_shared`
- [ ] Understand single-allocation optimization
- [ ] Study reference-counting costs

## Week 20 — Allocators and memory pools

- [ ] Implement bump / arena allocator
- [ ] Implement monotonic allocator
- [ ] Implement fixed-size pool allocator
- [ ] Understand allocate vs. construct
- [ ] Understand `allocator_traits`
- [ ] Add allocator support to vector
- [ ] Benchmark standard allocation vs. arena
- [ ] Study fragmentation
- [ ] Study alignment

## Week 21 — Generic algorithms

- [ ] Implement `copy`
- [ ] Implement `move`
- [ ] Implement `fill`
- [ ] Implement `find`
- [ ] Implement `lower_bound`
- [ ] Implement `reverse`
- [ ] Implement `rotate`
- [ ] Implement `partition`
- [ ] Implement heap algorithms generically
- [ ] Implement `sort`
- [ ] Implement `nth_element`
- [ ] Make algorithms work on iterators
- [ ] Study iterator-category-based optimization

## Week 22 — Concepts, ranges, and views

- [ ] Learn C++ concepts
- [ ] Constrain generic algorithms
- [ ] Understand iterator concepts
- [ ] Understand sentinels
- [ ] Implement `iota` view
- [ ] Implement `transform` view
- [ ] Implement `filter` view
- [ ] Implement `take` view
- [ ] Make views lazy
- [ ] Compose multiple views together

## Week 23 — Concurrency

- [ ] Review `mutex`
- [ ] Review `condition_variable`
- [ ] Review atomics
- [ ] Build `BlockingQueue<T>`
- [ ] Handle spurious wakeups correctly
- [ ] Build thread pool
- [ ] Implement `submit`
- [ ] Implement worker shutdown
- [ ] Avoid deadlocks
- [ ] Study basic memory ordering
- [ ] Study false sharing
- [ ] Run ThreadSanitizer

## Week 24 — Mini-STL capstone

- [ ] Organize everything into one library
- [ ] Clean public APIs
- [ ] Add unit tests
- [ ] Add randomized tests
- [ ] Add fuzz tests where useful
- [ ] Run AddressSanitizer
- [ ] Run UndefinedBehaviorSanitizer
- [ ] Run ThreadSanitizer
- [ ] Build benchmark suite
- [ ] Compare major components against `std`
- [ ] Profile CPU usage
- [ ] Profile allocations
- [ ] Document container invariants
- [ ] Document iterator invalidation rules
- [ ] Document exception guarantees
- [ ] Write a README explaining major design decisions
- [ ] Prepare 5–10 interview stories from the project

## Reusable checklist for every implementation

This is the most important checklist in the roadmap. Reuse it every week.

- [ ] Define invariants before coding
- [ ] Define ownership model
- [ ] Define memory layout
- [ ] Define complexity guarantees
- [ ] Define iterator/reference invalidation
- [ ] Implement copy semantics
- [ ] Implement move semantics
- [ ] Test empty state
- [ ] Test one-element state
- [ ] Test large state
- [ ] Test move-only types
- [ ] Test non-default-constructible types
- [ ] Test throwing constructors where relevant
- [ ] Run sanitizers
- [ ] Benchmark against `std`
- [ ] Explain why my implementation is faster/slower
- [ ] Write down what I learned
