# Tue_Async
THAT Conference 2023 Async Masterclass

## ValueTask
* high performance code that needs to reduce allocations
* try to use ValueTask wherever possible
* classic use case: Socket
* Modern ValueTask can also be an IValueTaskSoure, reusable tasks

### Rules for ValueTask
* only consume once
* Cannot block!
* Need to bend these rules?  AsTask()

### Implementing ValueTask
Produce ValueTask
* async ValueTask
* [AsyncMethodBuilder](typeof(PoolingAsyncValueTaskMethodBuilder<>))]: pooled ValueTask

## IAsyncDisposable
ValueTask DisposeAsync();
* Just liek Dispose(), just asynchronous
* No official patterns for whether we should support both
* Not supported everywhere, use Nito.Disposables if you want helpers

### Why use IAsyncDisposable
was added for async streams
* IObservable<T> (or events)
* IAsyncEnumerable<T>

## AsyncLocal
implicit data with lexical scoping (TLDR, the code is scoped to that code block)
### Guidelines
* use using to make scopes explicit
* use immutable types (there is a difference in modifying and setting the value)

