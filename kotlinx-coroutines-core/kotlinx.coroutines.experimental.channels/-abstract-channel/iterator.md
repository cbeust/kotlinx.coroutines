[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [iterator](.)

# iterator

`open fun iterator(): `[`ChannelIterator`](../-channel-iterator/index.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L220)

Overrides [ReceiveChannel.iterator](../-receive-channel/iterator.md)

Returns new iterator to receive elements from this channels using `for` loop.
Iteration completes normally when the channel is [closed](is-closed-for-receive.md) *normally* and
throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*.

