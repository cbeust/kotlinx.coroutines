[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ChannelIterator](.)

# ChannelIterator

`interface ChannelIterator<out E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L149)

Iterator for [ReceiveChannel](../-receive-channel/index.md). Instances of this interface are *not thread-safe* and shall not be used
from concurrent coroutines.

### Functions

| Name | Summary |
|---|---|
| [hasNext](has-next.md) | `abstract operator suspend fun hasNext(): Boolean`<br>Returns `true` if the channel has more elements suspending the caller while this channel
[isEmpty](../-receive-channel/is-empty.md) or returns `false` if the channel
[isClosedForReceive](../-receive-channel/is-closed-for-receive.md) *normally*.
It throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [next](next.md) | `abstract operator suspend fun next(): E`<br>Retrieves and removes the element from this channel suspending the caller while this channel
[isEmpty](../-receive-channel/is-empty.md) or throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md) if the channel
[isClosedForReceive](../-receive-channel/is-closed-for-receive.md).
It throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
