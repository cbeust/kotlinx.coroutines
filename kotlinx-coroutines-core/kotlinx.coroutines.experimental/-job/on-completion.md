[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Job](index.md) / [onCompletion](.)

# onCompletion

`abstract fun onCompletion(handler: `[`CompletionHandler`](../-completion-handler.md)`): `[`Registration`](-registration/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Job.kt#L73)

Registers completion handler. The action depends on the state of this job.
When job is cancelled with [cancel](cancel.md), then the handler is immediately invoked
with a cancellation reason. Otherwise, handler will be invoked once when this
job is complete (cancellation also is a form of completion).
The resulting [Registration](-registration/index.md) can be used to [Registration.unregister](-registration/unregister.md) if this
registration is no longer needed. There is no need to unregister after completion.

