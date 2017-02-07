[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [SendChannel](index.md) / [send](.)

# send

`abstract suspend fun send(element: E): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L55)

Adds [element](send.md#kotlinx.coroutines.experimental.channels.SendChannel$send(kotlinx.coroutines.experimental.channels.SendChannel.E)/element) into to this queue, suspending the caller while this queue [isFull](is-full.md),
or throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md) if the channel [isClosedForSend](is-closed-for-send.md) *normally*.
It throws the original [close](close.md) cause exception if the channel has *failed*.

This suspending function is cancellable. If the [Job](../../kotlinx.coroutines.experimental/-job/index.md) of the current coroutine is completed while this
function is suspended, this function immediately resumes with [CancellationException](../../kotlinx.coroutines.experimental/-cancellation-exception.md).
Cancellation of suspended send is *atomic* -- when this function
throws [CancellationException](../../kotlinx.coroutines.experimental/-cancellation-exception.md) it means that the [element](send.md#kotlinx.coroutines.experimental.channels.SendChannel$send(kotlinx.coroutines.experimental.channels.SendChannel.E)/element) was not sent to this channel.

Note, that this function does not check for cancellation when it is not suspended.
Use [yield](../../kotlinx.coroutines.experimental/yield.md) or [CoroutineScope.isActive](../../kotlinx.coroutines.experimental/-coroutine-scope/is-active.md) to periodically check for cancellation in tight loops if needed.

