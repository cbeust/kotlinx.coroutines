[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ClosedReceiveChannelException](.)

# ClosedReceiveChannelException

`class ClosedReceiveChannelException : NoSuchElementException` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L221)

Indicates attempt to [receive](../-receive-channel/receive.md) on [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
channel that was closed *normally*. A *failed* channel rethrows the original [close](../-send-channel/close.md) cause
exception on receive attempts.

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `ClosedReceiveChannelException(message: String?)`<br>Indicates attempt to [receive](../-receive-channel/receive.md) on [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
channel that was closed *normally*. A *failed* channel rethrows the original [close](../-send-channel/close.md) cause
exception on receive attempts. |
