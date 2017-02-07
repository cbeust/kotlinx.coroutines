[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Deferred](index.md) / [await](.)

# await

`abstract suspend fun await(): T` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Deferred.kt#L34)

Awaits for completion of this value without blocking a thread and resumes when deferred computation is complete.
This suspending function is cancellable.
If the [Job](../-job/index.md) of the current coroutine is completed while this suspending function is waiting, this function
immediately resumes with [CancellationException](../-cancellation-exception.md).

