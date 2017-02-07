[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [pollInternal](.)

# pollInternal

`protected abstract fun pollInternal(): Any?` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L47)

Tries to remove element from buffer or from queued sender.
Return type is `E | POLL_EMPTY | Closed`

