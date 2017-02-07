[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CancellableContinuation](index.md) / [isCancelled](.)

# isCancelled

`abstract val isCancelled: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CancellableContinuation.kt#L38)

Returns `true` if this continuation was cancelled. It implies that [isActive](../-job/is-active.md) is `false`.

