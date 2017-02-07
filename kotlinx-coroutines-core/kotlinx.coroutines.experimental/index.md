[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](.)

## Package kotlinx.coroutines.experimental

General-purpose coroutine builders and contexts.

* `launch(context) {...}` to start a coroutine in the given context and get reference to its `Job`.
* `run(context) {...}` to switch to a different context inside a coroutine.
* `runBlocking {...}` to use asynchronous Kotlin APIs from a thread-blocking code.
* `defer(context) {...}` and `lazyDefer(context) {...}` to get a deferred result of coroutine execution in a 
   non-blocking way via a light-weight future interface called `Deferred`.
* `delay(...)` for a non-blocking sleep in coroutines and 
  `yield()` to release a thread in single-threaded dispatchers.
* `withTimeout(timeout) {...}` scope function to easily set coroutine time-limit (deadline),
   and `NonCancellable` context to avoid it when needed.
* `CommonPool` and `Unconfined` contexts, access to `context` of a parent coroutine in its `CoroutineScope`.
* `newSingleThreadContext(...)` and `newFixedThreadPoolContext(...)` functions, 
  `Executor.toCoroutineDispatcher()` extension.
* Cancellation support with `Job` interface and `suspendCancellableCoroutine` helper function.
* Debugging facilities for coroutines (run JVM with `-ea` or `-Dkotlinx.coroutines.debug` options) and
  `newCoroutineContext(context)` function to write user-defined coroutine builders that work with these
   debugging facilities.

### Types

| Name | Summary |
|---|---|
| [CancellableContinuation](-cancellable-continuation/index.md) | `interface CancellableContinuation<in T> : Continuation<T>, `[`Job`](-job/index.md)<br>Cancellable continuation. Its job is completed when it is resumed or cancelled.
When [cancel](-job/cancel.md) function is explicitly invoked, this continuation resumes with [CancellationException](-cancellation-exception.md).
If the cancel reason was not a [CancellationException](-cancellation-exception.md), then the original exception is added as cause of the
[CancellationException](-cancellation-exception.md) that this continuation resumes with. |
| [CommonPool](-common-pool/index.md) | `object CommonPool : `[`CoroutineDispatcher`](-coroutine-dispatcher/index.md)<br>Represents common pool of shared threads as coroutine dispatcher for compute-intensive tasks.
It uses [java.util.concurrent.ForkJoinPool](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/ForkJoinPool.html) when available, which implements efficient work-stealing algorithm for its queues, so every
coroutine resumption is dispatched as a separate task even when it already executes inside the pool.
When available, it wraps `ForkJoinPool.commonPool` and provides a similar shared pool where not. |
| [CoroutineDispatcher](-coroutine-dispatcher/index.md) | `abstract class CoroutineDispatcher : AbstractCoroutineContextElement, ContinuationInterceptor`<br>Base class that shall be extended by all coroutine dispatcher implementations. |
| [CoroutineExceptionHandler](-coroutine-exception-handler/index.md) | `interface CoroutineExceptionHandler : Element`<br>An optional element on the coroutine context to handler uncaught exceptions.
See [handleCoroutineException](handle-coroutine-exception.md). |
| [CoroutineName](-coroutine-name/index.md) | `data class CoroutineName : AbstractCoroutineContextElement`<br>User-specified name of coroutine. This name is used in debugging mode.
See [newCoroutineContext](new-coroutine-context.md) for the description of coroutine debugging facilities. |
| [CoroutineScope](-coroutine-scope/index.md) | `interface CoroutineScope`<br>Receiver interface for generic coroutine builders, so that the code inside coroutine has a convenient access
to its [context](-coroutine-scope/context.md) and cancellation status via [isActive](-coroutine-scope/is-active.md). |
| [Deferred](-deferred/index.md) | `interface Deferred<out T> : `[`Job`](-job/index.md)<br>Deferred value is conceptually a non-blocking cancellable future.
It is created with [defer](defer.md) coroutine builder.
It is in [active](-job/is-active.md) state while the value is being computed. |
| [Delay](-delay/index.md) | `interface Delay`<br>This dispatcher *feature* is implemented by [CoroutineDispatcher](-coroutine-dispatcher/index.md) implementations that natively support
non-blocking [delay](-delay/delay.md) function. |
| [EventLoop](-event-loop/index.md) | `interface EventLoop`<br>Implemented by [CoroutineDispatcher](-coroutine-dispatcher/index.md) implementations that have event loop inside and can
be asked to process next event from their event queue. It is used by [runBlocking](run-blocking.md) to
continue processing events when invoked from the event dispatch thread. |
| [Job](-job/index.md) | `interface Job : Element`<br>A background job. It has two states: *active* (initial state) and *completed* (final state). |
| [LazyDeferred](-lazy-deferred/index.md) | `interface LazyDeferred<out T> : `[`Deferred`](-deferred/index.md)`<T>`<br>Lazy deferred value is conceptually a non-blocking cancellable future that is started on
the first [await](-deferred/await.md) or [start](-lazy-deferred/start.md) invocation.
It is created with [lazyDefer](lazy-defer.md) coroutine builder. |
| [NonCancellable](-non-cancellable/index.md) | `object NonCancellable : AbstractCoroutineContextElement, `[`Job`](-job/index.md)<br>A non-cancelable job that is always [active](-non-cancellable/is-active.md). It is designed to be used with [run](run.md) builder
to prevent cancellation of code blocks that need to run without cancellation, like this |
| [Unconfined](-unconfined/index.md) | `object Unconfined : `[`CoroutineDispatcher`](-coroutine-dispatcher/index.md)<br>A coroutine dispatcher that is not confined to any specific thread.
It executes initial continuation of the coroutine *right here* in the current call-frame
and let the coroutine resume in whatever thread that is used by the corresponding suspending function, without
mandating any specific threading policy. |

### Type Aliases

| Name | Summary |
|---|---|
| [CancellationException](-cancellation-exception.md) | `typealias CancellationException = `[`CancellationException`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CancellationException.html)<br>Thrown by cancellable suspending functions if the [Job](-job/index.md) of the coroutine is cancelled while it is suspending. |
| [CompletionHandler](-completion-handler.md) | `typealias CompletionHandler = (Throwable?) -> Unit` |
| [Here](-here.md) | `typealias ~~Here~~ = `[`Unconfined`](-unconfined/index.md) |

### Extensions for External Classes

| Name | Summary |
|---|---|
| [java.util.concurrent.Executor](java.util.concurrent.-executor/index.md) |  |

### Functions

| Name | Summary |
|---|---|
| [cancelFutureOnCompletion](cancel-future-on-completion.md) | `fun `[`Job`](-job/index.md)`.cancelFutureOnCompletion(future: `[`Future`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/Future.html)`<*>): `[`Registration`](-job/-registration/index.md)<br>Cancels a specified [future](cancel-future-on-completion.md#kotlinx.coroutines.experimental$cancelFutureOnCompletion(kotlinx.coroutines.experimental.Job, java.util.concurrent.Future((kotlin.Any)))/future) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
| [defer](defer.md) | `fun <T> defer(context: CoroutineContext, block: SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): `[`Deferred`](-deferred/index.md)`<T>`<br>Starts new coroutine and returns its result as an implementation of [Deferred](-deferred/index.md).
The running coroutine is cancelled when the resulting object is [cancelled](-job/cancel.md). |
| [delay](delay.md) | `suspend fun delay(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS): Unit`<br>Delays coroutine for a given time without blocking a thread and resumes it after a specified time.
This suspending function is cancellable.
If the [Job](-job/index.md) of the current coroutine is completed while this suspending function is suspended, this function
immediately resumes with [CancellationException](-cancellation-exception.md). |
| [handleCoroutineException](handle-coroutine-exception.md) | `fun handleCoroutineException(context: CoroutineContext, exception: Throwable): Unit`<br>Helper function for coroutine builder implementations to handle uncaught exception in coroutines.
It tries to handle uncaught exception in the following way: |
| [join](join.md) | `suspend fun `[`Job`](-job/index.md)`.join(): Unit`<br>Suspends coroutine until this job is complete. This invocation resumes normally (without exception)
when the job is complete for any reason. |
| [launch](launch.md) | `fun launch(context: CoroutineContext, block: SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, Unit>): `[`Job`](-job/index.md)<br>Launches new coroutine without blocking current thread and returns a reference to the coroutine as a [Job](-job/index.md).
The running coroutine is cancelled when the resulting job is [cancelled](-job/cancel.md). |
| [lazyDefer](lazy-defer.md) | `fun <T> lazyDefer(context: CoroutineContext, block: SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): `[`LazyDeferred`](-lazy-deferred/index.md)`<T>`<br>Lazily starts new coroutine on the first [await](-deferred/await.md) or [start](-lazy-deferred/start.md) invocation
on the resulting [LazyDeferred](-lazy-deferred/index.md).
The running coroutine is cancelled when the resulting value is [cancelled](-job/cancel.md). |
| [newCoroutineContext](new-coroutine-context.md) | `fun newCoroutineContext(context: CoroutineContext): CoroutineContext`<br>Creates context for the new coroutine with optional support for debugging facilities (when turned on). |
| [newFixedThreadPoolContext](new-fixed-thread-pool-context.md) | `fun newFixedThreadPoolContext(nThreads: Int, name: String, parent: `[`Job`](-job/index.md)`? = null): CoroutineContext`<br>Creates new coroutine execution context with the fixed-size thread-pool and built-in [yield](yield.md) and [delay](delay.md) support.
All continuations are dispatched immediately when invoked inside the threads of this context.
Resources of this pool (its threads) are reclaimed when job of this context is cancelled.
The specified [name](new-fixed-thread-pool-context.md#kotlinx.coroutines.experimental$newFixedThreadPoolContext(kotlin.Int, kotlin.String, kotlinx.coroutines.experimental.Job)/name) defines the names of the threads.
An optional [parent](new-fixed-thread-pool-context.md#kotlinx.coroutines.experimental$newFixedThreadPoolContext(kotlin.Int, kotlin.String, kotlinx.coroutines.experimental.Job)/parent) job may be specified upon creation. |
| [newSingleThreadContext](new-single-thread-context.md) | `fun newSingleThreadContext(name: String, parent: `[`Job`](-job/index.md)`? = null): CoroutineContext`<br>Creates new coroutine execution context with the a single thread and built-in [yield](yield.md) and [delay](delay.md) support.
All continuations are dispatched immediately when invoked inside the thread of this context.
Resources of this pool (its thread) are reclaimed when job of this context is cancelled.
The specified [name](new-single-thread-context.md#kotlinx.coroutines.experimental$newSingleThreadContext(kotlin.String, kotlinx.coroutines.experimental.Job)/name) defines the name of the new thread.
An optional [parent](new-single-thread-context.md#kotlinx.coroutines.experimental$newSingleThreadContext(kotlin.String, kotlinx.coroutines.experimental.Job)/parent) job may be specified upon creation. |
| [run](run.md) | `suspend fun <T> run(context: CoroutineContext, block: SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): T`<br>Calls the specified suspending block with a given coroutine context, suspends until it completes, and returns
the result. |
| [runBlocking](run-blocking.md) | `fun <T> runBlocking(context: CoroutineContext = EmptyCoroutineContext, block: SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): T`<br>Runs new coroutine and *blocks* current thread *interruptibly* until its completion.
This function should not be used from coroutine. It is designed to bridge regular blocking code
to libraries that are written in suspending style, to be used in `main` functions and in tests. |
| [suspendCancellableCoroutine](suspend-cancellable-coroutine.md) | `suspend fun <T> suspendCancellableCoroutine(holdCancellability: Boolean = false, block: (`[`CancellableContinuation`](-cancellable-continuation/index.md)`<T>) -> Unit): T`<br>Suspend coroutine similar to [suspendCoroutine](#), but provide an implementation of [CancellableContinuation](-cancellable-continuation/index.md) to
the [block](suspend-cancellable-coroutine.md#kotlinx.coroutines.experimental$suspendCancellableCoroutine(kotlin.Boolean, kotlin.Function1((kotlinx.coroutines.experimental.CancellableContinuation((kotlinx.coroutines.experimental.suspendCancellableCoroutine.T)), kotlin.Unit)))/block). This function throws [CancellationException](-cancellation-exception.md) if the coroutine is cancelled while suspended. |
| [unregisterOnCompletion](unregister-on-completion.md) | `fun `[`Job`](-job/index.md)`.unregisterOnCompletion(registration: `[`Registration`](-job/-registration/index.md)`): `[`Registration`](-job/-registration/index.md)<br>Unregisters a specified [registration](unregister-on-completion.md#kotlinx.coroutines.experimental$unregisterOnCompletion(kotlinx.coroutines.experimental.Job, kotlinx.coroutines.experimental.Job.Registration)/registration) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
| [withTimeout](with-timeout.md) | `suspend fun <T> withTimeout(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS, block: SuspendFunction0<T>): T`<br>Runs a given suspending block of code inside a coroutine with a specified timeout and throws
[CancellationException](-cancellation-exception.md) if timeout was exceeded. |
| [yield](yield.md) | `suspend fun yield(): Unit`<br>Yields a thread (or thread pool) of the current coroutine dispatcher to other coroutines to run.
If the coroutine dispatcher does not have its own thread pool (like [Unconfined](-unconfined/index.md) dispatcher) then this
function does nothing, but checks if the coroutine [Job](-job/index.md) was completed.
This suspending function is cancellable.
If the [Job](-job/index.md) of the current coroutine is completed when this suspending function is invoked or while
this function is waiting for dispatching, it resumes with [CancellationException](-cancellation-exception.md). |
