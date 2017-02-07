[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [suspendCancellableCoroutine](.)

# suspendCancellableCoroutine

`inline suspend fun <T> suspendCancellableCoroutine(holdCancellability: Boolean = false, crossinline block: (`[`CancellableContinuation`](-cancellable-continuation/index.md)`<T>) -> Unit): T` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CancellableContinuation.kt#L73)

Suspend coroutine similar to [suspendCoroutine](#), but provide an implementation of [CancellableContinuation](-cancellable-continuation/index.md) to
the [block](suspend-cancellable-coroutine.md#kotlinx.coroutines.experimental$suspendCancellableCoroutine(kotlin.Boolean, kotlin.Function1((kotlinx.coroutines.experimental.CancellableContinuation((kotlinx.coroutines.experimental.suspendCancellableCoroutine.T)), kotlin.Unit)))/block). This function throws [CancellationException](-cancellation-exception.md) if the coroutine is cancelled while suspended.

If [holdCancellability](suspend-cancellable-coroutine.md#kotlinx.coroutines.experimental$suspendCancellableCoroutine(kotlin.Boolean, kotlin.Function1((kotlinx.coroutines.experimental.CancellableContinuation((kotlinx.coroutines.experimental.suspendCancellableCoroutine.T)), kotlin.Unit)))/holdCancellability) optional parameter is `true`, then the coroutine is suspended, but it is not
cancellable until [CancellableContinuation.initCancellability](-cancellable-continuation/init-cancellability.md) is invoked.

