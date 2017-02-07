[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CommonPool](.)

# CommonPool

`object CommonPool : `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CommonPool.kt#L30)

Represents common pool of shared threads as coroutine dispatcher for compute-intensive tasks.
It uses [java.util.concurrent.ForkJoinPool](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/ForkJoinPool.html) when available, which implements efficient work-stealing algorithm for its queues, so every
coroutine resumption is dispatched as a separate task even when it already executes inside the pool.
When available, it wraps `ForkJoinPool.commonPool` and provides a similar shared pool where not.

### Functions

| Name | Summary |
|---|---|
| [dispatch](dispatch.md) | `fun dispatch(context: CoroutineContext, block: `[`Runnable`](http://docs.oracle.com/javase/6/docs/api/java/lang/Runnable.html)`): Unit`<br>Dispatches execution of a runnable [block](dispatch.md#kotlinx.coroutines.experimental.CommonPool$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/block) onto another thread in the given [context](dispatch.md#kotlinx.coroutines.experimental.CommonPool$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/context). |

### Inherited Functions

| Name | Summary |
|---|---|
| [interceptContinuation](../-coroutine-dispatcher/intercept-continuation.md) | `open fun <T> interceptContinuation(continuation: Continuation<T>): Continuation<T>` |
| [isDispatchNeeded](../-coroutine-dispatcher/is-dispatch-needed.md) | `open fun isDispatchNeeded(context: CoroutineContext): Boolean`<br>Return `true` if execution shall be dispatched onto another thread.
The default behaviour for most dispatchers is to return `true`. |
| [plus](../-coroutine-dispatcher/plus.md) | `operator fun ~~plus~~(other: `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md)`): `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md) |
