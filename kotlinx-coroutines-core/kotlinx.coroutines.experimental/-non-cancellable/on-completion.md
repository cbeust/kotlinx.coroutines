[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [NonCancellable](index.md) / [onCompletion](.)

# onCompletion

`fun onCompletion(handler: `[`CompletionHandler`](../-completion-handler.md)`): `[`Registration`](../-job/-registration/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/NonCancellable.kt#L34)

Overrides [Job.onCompletion](../-job/on-completion.md)

Registers completion handler. The action depends on the state of this job.
When job is cancelled with [cancel](cancel.md), then the handler is immediately invoked
with a cancellation reason. Otherwise, handler will be invoked once when this
job is complete (cancellation also is a form of completion).
The resulting [Registration](#) can be used to [Registration.unregister](#) if this
registration is no longer needed. There is no need to unregister after completion.

