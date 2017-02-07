[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineExceptionHandler](.)

# CoroutineExceptionHandler

`interface CoroutineExceptionHandler : Element` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineExceptionHandler.kt#L50)

An optional element on the coroutine context to handler uncaught exceptions.
See [handleCoroutineException](../handle-coroutine-exception.md).

### Functions

| Name | Summary |
|---|---|
| [handleException](handle-exception.md) | `abstract fun handleException(context: CoroutineContext, exception: Throwable): Unit` |
