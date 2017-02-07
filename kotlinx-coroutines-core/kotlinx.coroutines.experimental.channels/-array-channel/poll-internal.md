[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ArrayChannel](index.md) / [pollInternal](.)

# pollInternal

`protected fun pollInternal(): Any?` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/ArrayChannel.kt#L82)

Overrides [AbstractChannel.pollInternal](../-abstract-channel/poll-internal.md)

Tries to remove element from buffer or from queued sender.
Return type is `E | POLL_EMPTY | Closed`

