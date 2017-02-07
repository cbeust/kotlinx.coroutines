[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [join](.)

# join

`suspend fun `[`Job`](-job/index.md)`.join(): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Job.kt#L143)

Suspends coroutine until this job is complete. This invocation resumes normally (without exception)
when the job is complete for any reason.

This suspending function is cancellable. If the [Job](-job/index.md) of the invoking coroutine is completed while this
suspending function is suspended, this function immediately resumes with [CancellationException](-cancellation-exception.md).

