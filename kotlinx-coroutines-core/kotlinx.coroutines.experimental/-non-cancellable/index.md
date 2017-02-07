[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [NonCancellable](.)

# NonCancellable

`object NonCancellable : AbstractCoroutineContextElement, `[`Job`](../-job/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/NonCancellable.kt#L31)

A non-cancelable job that is always [active](is-active.md). It is designed to be used with [run](../run.md) builder
to prevent cancellation of code blocks that need to run without cancellation, like this

```
run(NonCancellable) {
    // this code will not be cancelled
}
```

### Properties

| Name | Summary |
|---|---|
| [isActive](is-active.md) | `val isActive: Boolean`<br>Returns `true` when job is still active. |

### Functions

| Name | Summary |
|---|---|
| [cancel](cancel.md) | `fun cancel(cause: Throwable?): Boolean`<br>Cancel this activity with an optional cancellation [cause](cancel.md#kotlinx.coroutines.experimental.NonCancellable$cancel(kotlin.Throwable)/cause). The result is `true` if this job was
cancelled as a result of this invocation and `false` otherwise
(if it was already cancelled or it is NonCancellable).
Repeated invocation of this function has no effect and always produces `false`. |
| [getInactiveCancellationException](get-inactive-cancellation-exception.md) | `fun getInactiveCancellationException(): `[`CancellationException`](../-cancellation-exception.md)<br>Returns [CancellationException](../-cancellation-exception.md) that [cancellable](../suspend-cancellable-coroutine.md) suspending functions throw when
trying to suspend in the context of this job. This function throws [IllegalAccessException](http://docs.oracle.com/javase/6/docs/api/java/lang/IllegalAccessException.html) when invoked
for an [active](is-active.md) job. |
| [onCompletion](on-completion.md) | `fun onCompletion(handler: `[`CompletionHandler`](../-completion-handler.md)`): `[`Registration`](../-job/-registration/index.md)<br>Registers completion handler. The action depends on the state of this job.
When job is cancelled with [cancel](cancel.md), then the handler is immediately invoked
with a cancellation reason. Otherwise, handler will be invoked once when this
job is complete (cancellation also is a form of completion).
The resulting [Registration](#) can be used to [Registration.unregister](#) if this
registration is no longer needed. There is no need to unregister after completion. |

### Inherited Functions

| Name | Summary |
|---|---|
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
