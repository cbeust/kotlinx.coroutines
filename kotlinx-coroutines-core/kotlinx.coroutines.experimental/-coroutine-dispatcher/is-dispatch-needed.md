[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineDispatcher](index.md) / [isDispatchNeeded](.)

# isDispatchNeeded

`open fun isDispatchNeeded(context: CoroutineContext): Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineDispatcher.kt#L47)

Return `true` if execution shall be dispatched onto another thread.
The default behaviour for most dispatchers is to return `true`.

