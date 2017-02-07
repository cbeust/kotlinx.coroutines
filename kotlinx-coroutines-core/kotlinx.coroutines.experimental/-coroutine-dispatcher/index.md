[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineDispatcher](.)

# CoroutineDispatcher

`abstract class CoroutineDispatcher : AbstractCoroutineContextElement, ContinuationInterceptor` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineDispatcher.kt#L41)

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

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `CoroutineDispatcher()`<br>Base class that shall be extended by all coroutine dispatcher implementations. |

### Functions

| Name | Summary |
|---|---|
| [dispatch](dispatch.md) | `abstract fun dispatch(context: CoroutineContext, block: `[`Runnable`](http://docs.oracle.com/javase/6/docs/api/java/lang/Runnable.html)`): Unit`<br>Dispatches execution of a runnable [block](dispatch.md#kotlinx.coroutines.experimental.CoroutineDispatcher$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/block) onto another thread in the given [context](dispatch.md#kotlinx.coroutines.experimental.CoroutineDispatcher$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/context). |
| [interceptContinuation](intercept-continuation.md) | `open fun <T> interceptContinuation(continuation: Continuation<T>): Continuation<T>` |
| [isDispatchNeeded](is-dispatch-needed.md) | `open fun isDispatchNeeded(context: CoroutineContext): Boolean`<br>Return `true` if execution shall be dispatched onto another thread.
The default behaviour for most dispatchers is to return `true`. |
| [plus](plus.md) | `operator fun ~~plus~~(other: CoroutineDispatcher): CoroutineDispatcher` |

### Inheritors

| Name | Summary |
|---|---|
| [CommonPool](../-common-pool/index.md) | `object CommonPool : CoroutineDispatcher`<br>Represents common pool of shared threads as coroutine dispatcher for compute-intensive tasks.
It uses [java.util.concurrent.ForkJoinPool](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/ForkJoinPool.html) when available, which implements efficient work-stealing algorithm for its queues, so every
coroutine resumption is dispatched as a separate task even when it already executes inside the pool.
When available, it wraps `ForkJoinPool.commonPool` and provides a similar shared pool where not. |
| [Unconfined](../-unconfined/index.md) | `object Unconfined : CoroutineDispatcher`<br>A coroutine dispatcher that is not confined to any specific thread.
It executes initial continuation of the coroutine *right here* in the current call-frame
and let the coroutine resume in whatever thread that is used by the corresponding suspending function, without
mandating any specific threading policy. |
