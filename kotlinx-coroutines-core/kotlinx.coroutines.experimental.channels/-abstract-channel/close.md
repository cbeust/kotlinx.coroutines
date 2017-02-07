[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [close](.)

# close

`open fun close(cause: Throwable?): Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L105)

Overrides [SendChannel.close](../-send-channel/close.md)

Closes this channel with an optional exceptional [cause](close.md#kotlinx.coroutines.experimental.channels.AbstractChannel$close(kotlin.Throwable)/cause).
This is an idempotent operation -- repeated invocations of this function have no effect and return `false`.
Conceptually, its sends a special close token of this channel. Immediately after invocation of this function
[isClosedForSend](is-closed-for-send.md) starts returning `true`. However, [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
on the side of [ReceiveChannel](../-receive-channel/index.md) starts returning `true` only after all previously sent elements
are received.

A channel that was closed without a [cause](close.md#kotlinx.coroutines.experimental.channels.AbstractChannel$close(kotlin.Throwable)/cause), is considered to be *closed normally*.
A channel that was closed with non-null [cause](close.md#kotlinx.coroutines.experimental.channels.AbstractChannel$close(kotlin.Throwable)/cause) is called a *failed channel*. Attempts to send or
receive on a failed channel throw this cause exception.

