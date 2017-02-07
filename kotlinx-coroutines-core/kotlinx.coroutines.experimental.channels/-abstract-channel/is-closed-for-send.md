[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [isClosedForSend](.)

# isClosedForSend

`open val isClosedForSend: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L57)

Overrides [SendChannel.isClosedForSend](../-send-channel/is-closed-for-send.md)

Returns `true` if this channel was closed by invocation of [close](close.md) and thus
the [send](send.md) attempt throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](close.md) cause exception.

**Getter**

Returns `true` if this channel was closed by invocation of [close](close.md) and thus
the [send](send.md) attempt throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](close.md) cause exception.

