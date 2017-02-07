[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [SendChannel](index.md) / [isClosedForSend](.)

# isClosedForSend

`abstract val isClosedForSend: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L34)

Returns `true` if this channel was closed by invocation of [close](close.md) and thus
the [send](send.md) attempt throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](close.md) cause exception.

