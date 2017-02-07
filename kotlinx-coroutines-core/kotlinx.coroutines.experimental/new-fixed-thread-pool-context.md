[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [newFixedThreadPoolContext](.)

# newFixedThreadPoolContext

`fun newFixedThreadPoolContext(nThreads: Int, name: String, parent: `[`Job`](-job/index.md)`? = null): CoroutineContext` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/ThreadPoolDispatcher.kt#L42)

Creates new coroutine execution context with the fixed-size thread-pool and built-in [yield](yield.md) and [delay](delay.md) support.
All continuations are dispatched immediately when invoked inside the threads of this context.
Resources of this pool (its threads) are reclaimed when job of this context is cancelled.
The specified [name](new-fixed-thread-pool-context.md#kotlinx.coroutines.experimental$newFixedThreadPoolContext(kotlin.Int, kotlin.String, kotlinx.coroutines.experimental.Job)/name) defines the names of the threads.
An optional [parent](new-fixed-thread-pool-context.md#kotlinx.coroutines.experimental$newFixedThreadPoolContext(kotlin.Int, kotlin.String, kotlinx.coroutines.experimental.Job)/parent) job may be specified upon creation.

