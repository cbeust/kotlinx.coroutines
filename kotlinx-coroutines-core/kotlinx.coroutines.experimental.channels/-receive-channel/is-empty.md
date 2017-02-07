[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ReceiveChannel](index.md) / [isEmpty](.)

# isEmpty

`abstract val isEmpty: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L97)

Returns `true` if the channel is empty (contains no elements) and the [receive](receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](is-closed-for-receive.md) channel.

