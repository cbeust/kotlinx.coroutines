[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Unconfined](index.md) / [isDispatchNeeded](.)

# isDispatchNeeded

`fun isDispatchNeeded(context: CoroutineContext): Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineContext.kt#L44)

Overrides [CoroutineDispatcher.isDispatchNeeded](../-coroutine-dispatcher/is-dispatch-needed.md)

Return `true` if execution shall be dispatched onto another thread.
The default behaviour for most dispatchers is to return `true`.

