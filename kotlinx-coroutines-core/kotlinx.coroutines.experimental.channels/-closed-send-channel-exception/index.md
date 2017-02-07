[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ClosedSendChannelException](.)

# ClosedSendChannelException

`class ClosedSendChannelException : IllegalStateException` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L214)

Indicates attempt to [send](../-send-channel/send.md) on [isClosedForSend](../-send-channel/is-closed-for-send.md) channel
that was closed *normally*. A *failed* channel rethrows the original [close](../-send-channel/close.md) cause
exception on send attempts.

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `ClosedSendChannelException(message: String?)`<br>Indicates attempt to [send](../-send-channel/send.md) on [isClosedForSend](../-send-channel/is-closed-for-send.md) channel
that was closed *normally*. A *failed* channel rethrows the original [close](../-send-channel/close.md) cause
exception on send attempts. |
