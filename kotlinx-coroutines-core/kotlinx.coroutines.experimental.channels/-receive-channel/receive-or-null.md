[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ReceiveChannel](index.md) / [receiveOrNull](.)

# receiveOrNull

`abstract suspend fun receiveOrNull(): E?` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L128)

Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](is-empty.md)
or returns `null` if the channel is [closed](is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*.

This suspending function is cancellable. If the [Job](../../kotlinx.coroutines.experimental/-job/index.md) of the current coroutine is completed while this
function is suspended, this function immediately resumes with [CancellationException](../../kotlinx.coroutines.experimental/-cancellation-exception.md).
Cancellation of suspended receive is *atomic* -- when this function
throws [CancellationException](../../kotlinx.coroutines.experimental/-cancellation-exception.md) it means that the element was not retrieved from this channel.

Note, that this function does not check for cancellation when it is not suspended.
Use [yield](../../kotlinx.coroutines.experimental/yield.md) or [CoroutineScope.isActive](../../kotlinx.coroutines.experimental/-coroutine-scope/is-active.md) to periodically check for cancellation in tight loops if needed.

