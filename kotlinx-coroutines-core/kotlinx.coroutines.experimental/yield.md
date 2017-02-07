[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [yield](.)

# yield

`suspend fun yield(): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Yield.kt#L27)

Yields a thread (or thread pool) of the current coroutine dispatcher to other coroutines to run.
If the coroutine dispatcher does not have its own thread pool (like [Unconfined](-unconfined/index.md) dispatcher) then this
function does nothing, but checks if the coroutine [Job](-job/index.md) was completed.
This suspending function is cancellable.
If the [Job](-job/index.md) of the current coroutine is completed when this suspending function is invoked or while
this function is waiting for dispatching, it resumes with [CancellationException](-cancellation-exception.md).

