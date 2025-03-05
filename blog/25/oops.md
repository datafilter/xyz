<!-- md.1
draft true
# published @
# updated @
oop/patterns
practices/paradigm
—-->

# Is OOP _(that)_ bad ?

> TLDR: It's not good, but it's better nothing.

## Why is it so popular

because it is so popular. it reached critical mass and now places that have it, want it.

we know better today, a lot of languages are leaning towards fp, or claim to be 'multiple paradigm'

but what made it popular? Oracle? timing during internet boom?

## What it was

smalltalk, erlang-like agents

## What is it (common defenition)

4 pillars (aka 3 pillars)

## What it is as opposed to FP ?

marries state & behavior

## What so bad about that?

complects state & time

## Ok so whats _good_ about OOP ?

puppeteer, stateful

leads to many **emerging** patterns wrongly interpreted as recommended patterns.

GoF was about observation, to classify, not to recommend.

Design patterns, a common language, the same in multiple languages 

 --> link write OOP design patterns vs FP design patterns
 --> irony that monad is almost excatly what FP is not, but being abstract & uncomplected with time, its a useful pattern

## Is fp better ?
Typically but not always, exceptions being:
100% purity
over-abstraction

## fp sometimes equally unfit as OOPs
size/efficiency - won't fit on a pacemaker, guided payload, etc
performance - strides has been made eg immutable datastructures etc, but will never out perform c/zig. 
  you don't usually need performace if a human is in the loop, but for trading / firmware, even milliseconds can matter drastically .

## Conclusion

Really depending on the context, it can be fine.
OOPs is typically requires more work to compose/reuse, debug, test/mock & is more boilerplatey than fp.

? Most business computing is linear (data in -> process -> data out). Stateless microservices with stateful DBs.
? Where _does_ OOP fit in well ?
? OOP fits in well with stateful context like a in-memory-db, or simulation (ie games) ?
