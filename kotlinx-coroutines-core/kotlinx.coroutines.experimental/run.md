[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [run](.)

# run

`suspend fun <T> run(context: CoroutineContext, block: @ExtensionFunctionType SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): T` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Builders.kt#L53)

Calls the specified suspending block with a given coroutine context, suspends until it completes, and returns
the result.

This function immediately applies dispatcher from the new context, shifting execution of the block into the
different thread inside the block, and back when it completes.
The specified [context](run.md#kotlinx.coroutines.experimental$run(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.CoroutineScope, kotlinx.coroutines.experimental.run.T)))/context) is added onto the current coroutine context for the execution of the block.

