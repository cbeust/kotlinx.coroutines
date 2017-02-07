[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Deferred](index.md) / [getCompleted](.)

# getCompleted

`abstract fun getCompleted(): T` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Deferred.kt#L42)

Returns *completed* result or throws [IllegalStateException](#) if this deferred value is still [isActive](../-job/is-active.md).
It throws the corresponding exception if this deferred has completed exceptionally.
This function is designed to be used from [onCompletion](../-job/on-completion.md) handlers, when there is an absolute certainty that
the value is already complete.

