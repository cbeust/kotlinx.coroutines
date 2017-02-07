[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [send](.)

# send

`open suspend fun send(element: E): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L60)

Adds [element](send.md#kotlinx.coroutines.experimental.channels.AbstractChannel$send(kotlinx.coroutines.experimental.channels.AbstractChannel.E)/element) into to this queue, suspending the caller while this queue [isFull](is-full.md),
or throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md) if the channel [isClosedForSend](is-closed-for-send.md) *normally*.
It throws the original [close](close.md) cause exception if the channel has *failed*.

This suspending function is cancellable. If the [Job](#) of the current coroutine is completed while this
function is suspended, this function immediately resumes with [CancellationException](#).
Cancellation of suspended send is *atomic* -- when this function
throws [CancellationException](#) it means that the [element](send.md#kotlinx.coroutines.experimental.channels.AbstractChannel$send(kotlinx.coroutines.experimental.channels.AbstractChannel.E)/element) was not sent to this channel.

Note, that this function does not check for cancellation when it is not suspended.
Use [yield](#) or [CoroutineScope.isActive](#) to periodically check for cancellation in tight loops if needed.

