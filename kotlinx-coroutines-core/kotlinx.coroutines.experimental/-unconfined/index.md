[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Unconfined](.)

# Unconfined

`object Unconfined : `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineContext.kt#L43)

A coroutine dispatcher that is not confined to any specific thread.
It executes initial continuation of the coroutine *right here* in the current call-frame
and let the coroutine resume in whatever thread that is used by the corresponding suspending function, without
mandating any specific threading policy.

### Functions

| Name | Summary |
|---|---|
| [dispatch](dispatch.md) | `fun dispatch(context: CoroutineContext, block: `[`Runnable`](http://docs.oracle.com/javase/6/docs/api/java/lang/Runnable.html)`): Unit`<br>Dispatches execution of a runnable [block](dispatch.md#kotlinx.coroutines.experimental.Unconfined$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/block) onto another thread in the given [context](dispatch.md#kotlinx.coroutines.experimental.Unconfined$dispatch(kotlin.coroutines.experimental.CoroutineContext, java.lang.Runnable)/context). |
| [isDispatchNeeded](is-dispatch-needed.md) | `fun isDispatchNeeded(context: CoroutineContext): Boolean`<br>Return `true` if execution shall be dispatched onto another thread.
The default behaviour for most dispatchers is to return `true`. |

### Inherited Functions

| Name | Summary |
|---|---|
| [interceptContinuation](../-coroutine-dispatcher/intercept-continuation.md) | `open fun <T> interceptContinuation(continuation: Continuation<T>): Continuation<T>` |
| [plus](../-coroutine-dispatcher/plus.md) | `operator fun ~~plus~~(other: `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md)`): `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md) |
