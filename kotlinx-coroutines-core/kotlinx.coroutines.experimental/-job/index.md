[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Job](.)

# Job

`interface Job : Element` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Job.kt#L42)

A background job. It has two states: *active* (initial state) and *completed* (final state).

A job can be *cancelled* at any time with [cancel](cancel.md) function that forces it to become completed immediately.
A job in the coroutine [context](../-coroutine-scope/context.md) represents the coroutine itself.
A job is active while the coroutine is working and job's cancellation aborts the coroutine when
the coroutine is suspended on a *cancellable* suspension point by throwing [CancellationException](../-cancellation-exception.md)
inside the coroutine.

A job can have a *parent*. A job with a parent is cancelled when its parent completes.

All functions on this interface are thread-safe.

### Types

| Name | Summary |
|---|---|
| [Registration](-registration/index.md) | `interface Registration`<br>Registration object for [onCompletion](on-completion.md). It can be used to [unregister](-registration/unregister.md) if needed.
There is no need to unregister after completion. |

### Properties

| Name | Summary |
|---|---|
| [isActive](is-active.md) | `abstract val isActive: Boolean`<br>Returns `true` when job is still active. |

### Functions

| Name | Summary |
|---|---|
| [cancel](cancel.md) | `abstract fun cancel(cause: Throwable? = null): Boolean`<br>Cancel this activity with an optional cancellation [cause](cancel.md#kotlinx.coroutines.experimental.Job$cancel(kotlin.Throwable)/cause). The result is `true` if this job was
cancelled as a result of this invocation and `false` otherwise
(if it was already cancelled or it is [NonCancellable](../-non-cancellable/index.md)).
Repeated invocation of this function has no effect and always produces `false`. |
| [getInactiveCancellationException](get-inactive-cancellation-exception.md) | `abstract fun getInactiveCancellationException(): `[`CancellationException`](../-cancellation-exception.md)<br>Returns [CancellationException](../-cancellation-exception.md) that [cancellable](../suspend-cancellable-coroutine.md) suspending functions throw when
trying to suspend in the context of this job. This function throws [IllegalAccessException](http://docs.oracle.com/javase/6/docs/api/java/lang/IllegalAccessException.html) when invoked
for an [active](is-active.md) job. |
| [onCompletion](on-completion.md) | `abstract fun onCompletion(handler: `[`CompletionHandler`](../-completion-handler.md)`): `[`Registration`](-registration/index.md)<br>Registers completion handler. The action depends on the state of this job.
When job is cancelled with [cancel](cancel.md), then the handler is immediately invoked
with a cancellation reason. Otherwise, handler will be invoked once when this
job is complete (cancellation also is a form of completion).
The resulting [Registration](-registration/index.md) can be used to [Registration.unregister](-registration/unregister.md) if this
registration is no longer needed. There is no need to unregister after completion. |
| [plus](plus.md) | `open operator fun ~~plus~~(other: Job): Job` |

### Companion Object Functions

| Name | Summary |
|---|---|
| [invoke](invoke.md) | `operator fun invoke(parent: Job? = null): Job`<br>Creates new job object. It is optionally a child of a [parent](invoke.md#kotlinx.coroutines.experimental.Job.Key$invoke(kotlinx.coroutines.experimental.Job)/parent) job. |

### Extension Functions

| Name | Summary |
|---|---|
| [cancelFutureOnCompletion](../cancel-future-on-completion.md) | `fun Job.cancelFutureOnCompletion(future: `[`Future`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/Future.html)`<*>): `[`Registration`](-registration/index.md)<br>Cancels a specified [future](../cancel-future-on-completion.md#kotlinx.coroutines.experimental$cancelFutureOnCompletion(kotlinx.coroutines.experimental.Job, java.util.concurrent.Future((kotlin.Any)))/future) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
| [join](../join.md) | `suspend fun Job.join(): Unit`<br>Suspends coroutine until this job is complete. This invocation resumes normally (without exception)
when the job is complete for any reason. |
| [unregisterOnCompletion](../unregister-on-completion.md) | `fun Job.unregisterOnCompletion(registration: `[`Registration`](-registration/index.md)`): `[`Registration`](-registration/index.md)<br>Unregisters a specified [registration](../unregister-on-completion.md#kotlinx.coroutines.experimental$unregisterOnCompletion(kotlinx.coroutines.experimental.Job, kotlinx.coroutines.experimental.Job.Registration)/registration) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |

### Inheritors

| Name | Summary |
|---|---|
| [CancellableContinuation](../-cancellable-continuation/index.md) | `interface CancellableContinuation<in T> : Continuation<T>, Job`<br>Cancellable continuation. Its job is completed when it is resumed or cancelled.
When [cancel](cancel.md) function is explicitly invoked, this continuation resumes with [CancellationException](../-cancellation-exception.md).
If the cancel reason was not a [CancellationException](../-cancellation-exception.md), then the original exception is added as cause of the
[CancellationException](../-cancellation-exception.md) that this continuation resumes with. |
| [ChannelJob](../../kotlinx.coroutines.experimental.channels/-channel-job.md) | `interface ChannelJob<out E> : Job, `[`ReceiveChannel`](../../kotlinx.coroutines.experimental.channels/-receive-channel/index.md)`<E>`<br>Return type for [buildChannel](../../kotlinx.coroutines.experimental.channels/build-channel.md). |
| [Deferred](../-deferred/index.md) | `interface Deferred<out T> : Job`<br>Deferred value is conceptually a non-blocking cancellable future.
It is created with [defer](../defer.md) coroutine builder.
It is in [active](is-active.md) state while the value is being computed. |
| [NonCancellable](../-non-cancellable/index.md) | `object NonCancellable : AbstractCoroutineContextElement, Job`<br>A non-cancelable job that is always [active](../-non-cancellable/is-active.md). It is designed to be used with [run](../run.md) builder
to prevent cancellation of code blocks that need to run without cancellation, like this |
