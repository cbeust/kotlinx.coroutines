[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [newSingleThreadContext](.)

# newSingleThreadContext

`fun newSingleThreadContext(name: String, parent: `[`Job`](-job/index.md)`? = null): CoroutineContext` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/ThreadPoolDispatcher.kt#L32)

Creates new coroutine execution context with the a single thread and built-in [yield](yield.md) and [delay](delay.md) support.
All continuations are dispatched immediately when invoked inside the thread of this context.
Resources of this pool (its thread) are reclaimed when job of this context is cancelled.
The specified [name](new-single-thread-context.md#kotlinx.coroutines.experimental$newSingleThreadContext(kotlin.String, kotlinx.coroutines.experimental.Job)/name) defines the name of the new thread.
An optional [parent](new-single-thread-context.md#kotlinx.coroutines.experimental$newSingleThreadContext(kotlin.String, kotlinx.coroutines.experimental.Job)/parent) job may be specified upon creation.

