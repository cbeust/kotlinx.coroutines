[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [NonCancellable](index.md) / [getInactiveCancellationException](.)

# getInactiveCancellationException

`fun getInactiveCancellationException(): `[`CancellationException`](../-cancellation-exception.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/NonCancellable.kt#L33)

Overrides [Job.getInactiveCancellationException](../-job/get-inactive-cancellation-exception.md)

Returns [CancellationException](../-cancellation-exception.md) that [cancellable](../suspend-cancellable-coroutine.md) suspending functions throw when
trying to suspend in the context of this job. This function throws [IllegalAccessException](http://docs.oracle.com/javase/6/docs/api/java/lang/IllegalAccessException.html) when invoked
for an [active](is-active.md) job.

