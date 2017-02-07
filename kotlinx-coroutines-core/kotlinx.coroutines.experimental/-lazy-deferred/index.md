[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [LazyDeferred](.)

# LazyDeferred

`interface LazyDeferred<out T> : `[`Deferred`](../-deferred/index.md)`<T>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/LazyDeferred.kt#L36)

Lazy deferred value is conceptually a non-blocking cancellable future that is started on
the first [await](../-deferred/await.md) or [start](start.md) invocation.
It is created with [lazyDefer](../lazy-defer.md) coroutine builder.

Unlike a simple [Deferred](../-deferred/index.md) value, a lazy deferred value has three states:

* *Pending* -- before the starts of the coroutine ([isActive](#) is `true`, but [isComputing](is-computing.md) is `false`).
* *Computing* -- while computing the value ([isActive](#) is `true` and [isComputing](is-computing.md) is `true`).
* *Complete* -- when done computing the value ([isActive](#) is `false` and [isComputing](is-computing.md) is `false`).

If this lazy deferred value is [cancelled](#), then it becomes immediately complete and
cancels ongoing computation coroutine if it was started.

### Properties

| Name | Summary |
|---|---|
| [isComputing](is-computing.md) | `abstract val isComputing: Boolean`<br>Returns `true` if the coroutine is computing its value. |

### Functions

| Name | Summary |
|---|---|
| [start](start.md) | `abstract fun start(): Boolean`<br>Starts coroutine to compute this lazily deferred value. The result `true` if this invocation actually
started coroutine or `false` if it was already started or cancelled. |

### Inherited Functions

| Name | Summary |
|---|---|
| [await](../-deferred/await.md) | `abstract suspend fun await(): T`<br>Awaits for completion of this value without blocking a thread and resumes when deferred computation is complete.
This suspending function is cancellable.
If the [Job](../-job/index.md) of the current coroutine is completed while this suspending function is waiting, this function
immediately resumes with [CancellationException](../-cancellation-exception.md). |
| [getCompleted](../-deferred/get-completed.md) | `abstract fun getCompleted(): T`<br>Returns *completed* result or throws [IllegalStateException](#) if this deferred value is still [isActive](../-job/is-active.md).
It throws the corresponding exception if this deferred has completed exceptionally.
This function is designed to be used from [onCompletion](../-job/on-completion.md) handlers, when there is an absolute certainty that
the value is already complete. |

### Extension Functions

| Name | Summary |
|---|---|
| [cancelFutureOnCompletion](../cancel-future-on-completion.md) | `fun `[`Job`](../-job/index.md)`.cancelFutureOnCompletion(future: `[`Future`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/Future.html)`<*>): `[`Registration`](../-job/-registration/index.md)<br>Cancels a specified [future](../cancel-future-on-completion.md#kotlinx.coroutines.experimental$cancelFutureOnCompletion(kotlinx.coroutines.experimental.Job, java.util.concurrent.Future((kotlin.Any)))/future) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
| [join](../join.md) | `suspend fun `[`Job`](../-job/index.md)`.join(): Unit`<br>Suspends coroutine until this job is complete. This invocation resumes normally (without exception)
when the job is complete for any reason. |
| [unregisterOnCompletion](../unregister-on-completion.md) | `fun `[`Job`](../-job/index.md)`.unregisterOnCompletion(registration: `[`Registration`](../-job/-registration/index.md)`): `[`Registration`](../-job/-registration/index.md)<br>Unregisters a specified [registration](../unregister-on-completion.md#kotlinx.coroutines.experimental$unregisterOnCompletion(kotlinx.coroutines.experimental.Job, kotlinx.coroutines.experimental.Job.Registration)/registration) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
