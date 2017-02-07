[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Deferred](.)

# Deferred

`interface Deferred<out T> : `[`Job`](../-job/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Deferred.kt#L27)

Deferred value is conceptually a non-blocking cancellable future.
It is created with [defer](../defer.md) coroutine builder.
It is in [active](../-job/is-active.md) state while the value is being computed.

### Inherited Properties

| Name | Summary |
|---|---|
| [isActive](../-job/is-active.md) | `abstract val isActive: Boolean`<br>Returns `true` when job is still active. |

### Functions

| Name | Summary |
|---|---|
| [await](await.md) | `abstract suspend fun await(): T`<br>Awaits for completion of this value without blocking a thread and resumes when deferred computation is complete.
This suspending function is cancellable.
If the [Job](../-job/index.md) of the current coroutine is completed while this suspending function is waiting, this function
immediately resumes with [CancellationException](../-cancellation-exception.md). |
| [getCompleted](get-completed.md) | `abstract fun getCompleted(): T`<br>Returns *completed* result or throws [IllegalStateException](#) if this deferred value is still [isActive](../-job/is-active.md).
It throws the corresponding exception if this deferred has completed exceptionally.
This function is designed to be used from [onCompletion](../-job/on-completion.md) handlers, when there is an absolute certainty that
the value is already complete. |

### Inherited Functions

| Name | Summary |
|---|---|
| [cancel](../-job/cancel.md) | `abstract fun cancel(cause: Throwable? = null): Boolean`<br>Cancel this activity with an optional cancellation [cause](../-job/cancel.md#kotlinx.coroutines.experimental.Job$cancel(kotlin.Throwable)/cause). The result is `true` if this job was
cancelled as a result of this invocation and `false` otherwise
(if it was already cancelled or it is [NonCancellable](../-non-cancellable/index.md)).
Repeated invocation of this function has no effect and always produces `false`. |
| [getInactiveCancellationException](../-job/get-inactive-cancellation-exception.md) | `abstract fun getInactiveCancellationException(): `[`CancellationException`](../-cancellation-exception.md)<br>Returns [CancellationException](../-cancellation-exception.md) that [cancellable](../suspend-cancellable-coroutine.md) suspending functions throw when
trying to suspend in the context of this job. This function throws [IllegalAccessException](http://docs.oracle.com/javase/6/docs/api/java/lang/IllegalAccessException.html) when invoked
for an [active](../-job/is-active.md) job. |
| [onCompletion](../-job/on-completion.md) | `abstract fun onCompletion(handler: `[`CompletionHandler`](../-completion-handler.md)`): `[`Registration`](../-job/-registration/index.md)<br>Registers completion handler. The action depends on the state of this job.
When job is cancelled with [cancel](../-job/cancel.md), then the handler is immediately invoked
with a cancellation reason. Otherwise, handler will be invoked once when this
job is complete (cancellation also is a form of completion).
The resulting [Registration](../-job/-registration/index.md) can be used to [Registration.unregister](../-job/-registration/unregister.md) if this
registration is no longer needed. There is no need to unregister after completion. |
| [plus](../-job/plus.md) | `open operator fun ~~plus~~(other: `[`Job`](../-job/index.md)`): `[`Job`](../-job/index.md) |

### Extension Functions

| Name | Summary |
|---|---|
| [cancelFutureOnCompletion](../cancel-future-on-completion.md) | `fun `[`Job`](../-job/index.md)`.cancelFutureOnCompletion(future: `[`Future`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/Future.html)`<*>): `[`Registration`](../-job/-registration/index.md)<br>Cancels a specified [future](../cancel-future-on-completion.md#kotlinx.coroutines.experimental$cancelFutureOnCompletion(kotlinx.coroutines.experimental.Job, java.util.concurrent.Future((kotlin.Any)))/future) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
| [join](../join.md) | `suspend fun `[`Job`](../-job/index.md)`.join(): Unit`<br>Suspends coroutine until this job is complete. This invocation resumes normally (without exception)
when the job is complete for any reason. |
| [unregisterOnCompletion](../unregister-on-completion.md) | `fun `[`Job`](../-job/index.md)`.unregisterOnCompletion(registration: `[`Registration`](../-job/-registration/index.md)`): `[`Registration`](../-job/-registration/index.md)<br>Unregisters a specified [registration](../unregister-on-completion.md#kotlinx.coroutines.experimental$unregisterOnCompletion(kotlinx.coroutines.experimental.Job, kotlinx.coroutines.experimental.Job.Registration)/registration) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |

### Inheritors

| Name | Summary |
|---|---|
| [LazyDeferred](../-lazy-deferred/index.md) | `interface LazyDeferred<out T> : Deferred<T>`<br>Lazy deferred value is conceptually a non-blocking cancellable future that is started on
the first [await](await.md) or [start](../-lazy-deferred/start.md) invocation.
It is created with [lazyDefer](../lazy-defer.md) coroutine builder. |
