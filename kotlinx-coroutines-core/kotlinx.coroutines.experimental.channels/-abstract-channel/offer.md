[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [offer](.)

# offer

`open fun offer(element: E): Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L67)

Adds [element](offer.md#kotlinx.coroutines.experimental.channels.AbstractChannel$offer(kotlinx.coroutines.experimental.channels.AbstractChannel.E)/element) into this queue if it is possible to do so immediately without violating capacity restrictions
and returns `true`. Otherwise, it returns `false` immediately
or throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md) if the channel [isClosedForSend](is-closed-for-send.md) *normally*.
It throws the original [close](close.md) cause exception if the channel has *failed*.

