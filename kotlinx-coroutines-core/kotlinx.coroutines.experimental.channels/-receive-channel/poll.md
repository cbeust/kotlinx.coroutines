[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ReceiveChannel](index.md) / [poll](.)

# poll

`abstract fun poll(): E?` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L135)

Retrieves and removes the head of this queue, or returns `null` if this queue [isEmpty](is-empty.md)
or is [closed](is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*.

