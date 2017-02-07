[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [defer](.)

# defer

`fun <T> defer(context: CoroutineContext, block: @ExtensionFunctionType SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): `[`Deferred`](-deferred/index.md)`<T>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Deferred.kt#L54)

Starts new coroutine and returns its result as an implementation of [Deferred](-deferred/index.md).
The running coroutine is cancelled when the resulting object is [cancelled](-job/cancel.md).

The [context](defer.md#kotlinx.coroutines.experimental$defer(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.CoroutineScope, kotlinx.coroutines.experimental.defer.T)))/context) for the new coroutine must be explicitly specified.
See [CoroutineDispatcher](-coroutine-dispatcher/index.md) for the standard [context](defer.md#kotlinx.coroutines.experimental$defer(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.CoroutineScope, kotlinx.coroutines.experimental.defer.T)))/context) implementations that are provided by `kotlinx.coroutines`.
The [context](-coroutine-scope/context.md) of the parent coroutine from its [scope](-coroutine-scope/index.md) may be used,
in which case the [Job](-job/index.md) of the resulting coroutine is a child of the job of the parent coroutine.

