[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [isClosedForReceive](.)

# isClosedForReceive

`open val isClosedForReceive: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L125)

Overrides [ReceiveChannel.isClosedForReceive](../-receive-channel/is-closed-for-receive.md)

Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) on the [SendChannel](../-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](receive.md) attempt
throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](../-send-channel/close.md) cause exception.

**Getter**

Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) on the [SendChannel](../-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](receive.md) attempt
throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](../-send-channel/close.md) cause exception.

