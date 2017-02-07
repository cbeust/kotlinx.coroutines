[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [isFull](.)

# isFull

`open val isFull: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L58)

Overrides [SendChannel.isFull](../-send-channel/is-full.md)

Returns `true` if the channel is full (out of capacity) and the [send](send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](is-closed-for-send.md) channel.

**Getter**

Returns `true` if the channel is full (out of capacity) and the [send](send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](is-closed-for-send.md) channel.

