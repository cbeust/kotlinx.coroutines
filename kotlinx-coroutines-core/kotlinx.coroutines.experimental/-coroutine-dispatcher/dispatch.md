[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineDispatcher](index.md) / [dispatch](.)

# dispatch

`abstract fun dispatch(context: CoroutineContext, block: `[`Runnable`](http://docs.oracle.com/javase/6/docs/api/java/lang/Runnable.html)`): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineDispatcher.kt#L52)

Dispatches execution of a runnable [block](dispatch.md#kotlinx.coroutines.experimental.CoroutineDispatcher$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/block) onto another thread in the given [context](dispatch.md#kotlinx.coroutines.experimental.CoroutineDispatcher$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/context).

