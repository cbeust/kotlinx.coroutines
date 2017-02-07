[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [RendezvousChannel](index.md) / [offerInternal](.)

# offerInternal

`protected fun offerInternal(element: E): Any` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/RendezvousChannel.kt#L33)

Tries to add element to buffer or to queued receiver.
Return type is `OFFER_SUCCESS | OFFER_FAILED | Closed`.

