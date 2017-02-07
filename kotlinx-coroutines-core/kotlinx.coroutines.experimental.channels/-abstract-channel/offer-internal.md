[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](index.md) / [offerInternal](.)

# offerInternal

`protected abstract fun offerInternal(element: E): Any` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L41)

Tries to add element to buffer or to queued receiver.
Return type is `OFFER_SUCCESS | OFFER_FAILED | Closed`.

