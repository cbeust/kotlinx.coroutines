[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [isEmpty](.)

# isEmpty

`open val isEmpty: Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L126)

Overrides [ReceiveChannel.isEmpty](../-receive-channel/is-empty.md)

Returns `true` if the channel is empty (contains no elements) and the [receive](receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](is-closed-for-receive.md) channel.

**Getter**

Returns `true` if the channel is empty (contains no elements) and the [receive](receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](is-closed-for-receive.md) channel.

