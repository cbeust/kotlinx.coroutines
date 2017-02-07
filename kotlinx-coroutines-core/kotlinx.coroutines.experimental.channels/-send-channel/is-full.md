[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [SendChannel](index.md) / [isFull](.)

# isFull

`abstract val isFull: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L40)

Returns `true` if the channel is full (out of capacity) and the [send](send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](is-closed-for-send.md) channel.

