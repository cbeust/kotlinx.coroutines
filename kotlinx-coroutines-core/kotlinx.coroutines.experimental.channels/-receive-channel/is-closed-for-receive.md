[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ReceiveChannel](index.md) / [isClosedForReceive](.)

# isClosedForReceive

`abstract val isClosedForReceive: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L91)

Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) on the [SendChannel](../-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](receive.md) attempt
throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](../-send-channel/close.md) cause exception.

