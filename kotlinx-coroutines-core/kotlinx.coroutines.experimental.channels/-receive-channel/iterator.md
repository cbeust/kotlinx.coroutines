[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ReceiveChannel](index.md) / [iterator](.)

# iterator

`abstract operator fun iterator(): `[`ChannelIterator`](../-channel-iterator/index.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L142)

Returns new iterator to receive elements from this channels using `for` loop.
Iteration completes normally when the channel is [closed](is-closed-for-receive.md) *normally* and
throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*.

