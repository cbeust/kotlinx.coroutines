[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineDispatcher](index.md) / [&lt;init&gt;](.)

# &lt;init&gt;

`CoroutineDispatcher()`

Base class that shall be extended by all coroutine dispatcher implementations.

The following standard implementations are provided by `kotlinx.coroutines`:

* [Unconfined](../-unconfined/index.md) -- starts coroutine execution in the current call-frame until the first suspension.
On first  suspension the coroutine builder function returns.
The coroutine will resume in whatever thread that is used by the
corresponding suspending function, without confining it to any specific thread or pool.
This in an appropriate choice for IO-intensive coroutines that do not consume CPU resources.
* [CommonPool](../-common-pool/index.md) -- immediately returns from the coroutine builder and schedules coroutine execution to
a common pool of shared background threads.
This is an appropriate choice for compute-intensive coroutines that consume a lot of CPU resources.
* Private thread pools can be created with [newSingleThreadContext](../new-single-thread-context.md) and [newFixedThreadPoolContext](../new-fixed-thread-pool-context.md).
* An arbitrary [Executor](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/Executor.html) can be converted to dispatcher with [toCoroutineDispatcher](../java.util.concurrent.-executor/to-coroutine-dispatcher.md) extension function.

This class ensures that debugging facilities in [newCoroutineContext](../new-coroutine-context.md) function work properly.

