[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Job](index.md) / [cancel](.)

# cancel

`abstract fun cancel(cause: Throwable? = null): Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Job.kt#L85)

Cancel this activity with an optional cancellation [cause](cancel.md#kotlinx.coroutines.experimental.Job$cancel(kotlin.Throwable)/cause). The result is `true` if this job was
cancelled as a result of this invocation and `false` otherwise
(if it was already cancelled or it is [NonCancellable](../-non-cancellable/index.md)).
Repeated invocation of this function has no effect and always produces `false`.

When cancellation has a clear reason in the code, an instance of [CancellationException](../-cancellation-exception.md) should be created
at the corresponding original cancellation site and passed into this method to aid in debugging by providing
both the context of cancellation and text description of the reason.

