[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CancellableContinuation](.)

# CancellableContinuation

`interface CancellableContinuation<in T> : Continuation<T>, `[`Job`](../-job/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CancellableContinuation.kt#L34)

Cancellable continuation. Its job is completed when it is resumed or cancelled.
When [cancel](../-job/cancel.md) function is explicitly invoked, this continuation resumes with [CancellationException](../-cancellation-exception.md).
If the cancel reason was not a [CancellationException](../-cancellation-exception.md), then the original exception is added as cause of the
[CancellationException](../-cancellation-exception.md) that this continuation resumes with.

### Properties

| Name | Summary |
|---|---|
| [isCancelled](is-cancelled.md) | `abstract val isCancelled: Boolean`<br>Returns `true` if this continuation was cancelled. It implies that [isActive](../-job/is-active.md) is `false`. |

### Inherited Properties

| Name | Summary |
|---|---|
| [isActive](../-job/is-active.md) | `abstract val isActive: Boolean`<br>Returns `true` when job is still active. |

### Functions

| Name | Summary |
|---|---|
| [completeResume](complete-resume.md) | `abstract fun completeResume(token: Any): Unit`<br>Completes the execution of [tryResume](try-resume.md) or [tryResumeWithException](try-resume-with-exception.md) on its non-null result. |
| [initCancellability](init-cancellability.md) | `abstract fun initCancellability(): Unit`<br>Makes this continuation cancellable. Use it with `holdCancellability` optional parameter to
[suspendCancellableCoroutine](../suspend-cancellable-coroutine.md) function. It throws [IllegalStateException](#) if invoked more than once. |
| [tryResume](try-resume.md) | `abstract fun tryResume(value: T): Any?`<br>Tries to resume this continuation with a given value and returns non-null object token if it was successful,
or `null` otherwise (it was already resumed or cancelled). When non-null object was returned,
[completeResume](complete-resume.md) must be invoked with it. |
| [tryResumeWithException](try-resume-with-exception.md) | `abstract fun tryResumeWithException(exception: Throwable): Any?`<br>Tries to resume this continuation with a given exception and returns non-null object token if it was successful,
or `null` otherwise (it was already resumed or cancelled). When non-null object was returned,
[completeResume](complete-resume.md) must be invoked with it. |

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
