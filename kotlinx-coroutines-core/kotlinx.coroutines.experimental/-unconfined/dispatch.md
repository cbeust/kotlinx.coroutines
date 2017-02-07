[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Unconfined](index.md) / [dispatch](.)

# dispatch

`fun dispatch(context: CoroutineContext, block: `[`Runnable`](http://docs.oracle.com/javase/6/docs/api/java/lang/Runnable.html)`): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineContext.kt#L45)

Overrides [CoroutineDispatcher.dispatch](../-coroutine-dispatcher/dispatch.md)

Dispatches execution of a runnable [block](dispatch.md#kotlinx.coroutines.experimental.Unconfined$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/block) onto another thread in the given [context](dispatch.md#kotlinx.coroutines.experimental.Unconfined$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/context).

