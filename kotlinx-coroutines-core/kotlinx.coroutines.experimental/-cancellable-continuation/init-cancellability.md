[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CancellableContinuation](index.md) / [initCancellability](.)

# initCancellability

`abstract fun initCancellability(): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CancellableContinuation.kt#L63)

Makes this continuation cancellable. Use it with `holdCancellability` optional parameter to
[suspendCancellableCoroutine](../suspend-cancellable-coroutine.md) function. It throws [IllegalStateException](#) if invoked more than once.

