[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [lazyDefer](.)

# lazyDefer

`fun <T> lazyDefer(context: CoroutineContext, block: @ExtensionFunctionType SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): `[`LazyDeferred`](-lazy-deferred/index.md)`<T>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/LazyDeferred.kt#L59)

Lazily starts new coroutine on the first [await](-deferred/await.md) or [start](-lazy-deferred/start.md) invocation
on the resulting [LazyDeferred](-lazy-deferred/index.md).
The running coroutine is cancelled when the resulting value is [cancelled](-job/cancel.md).

The [context](lazy-defer.md#kotlinx.coroutines.experimental$lazyDefer(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.CoroutineScope, kotlinx.coroutines.experimental.lazyDefer.T)))/context) for the new coroutine must be explicitly specified.
See [CoroutineDispatcher](-coroutine-dispatcher/index.md) for the standard [context](lazy-defer.md#kotlinx.coroutines.experimental$lazyDefer(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.CoroutineScope, kotlinx.coroutines.experimental.lazyDefer.T)))/context) implementations that are provided by `kotlinx.coroutines`.
The [context](-coroutine-scope/context.md) of the parent coroutine from its [scope](-coroutine-scope/index.md) may be used,
in which case the [Job](-job/index.md) of the resulting coroutine is a child of the job of the parent coroutine.

