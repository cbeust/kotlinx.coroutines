[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ClosedReceiveChannelException](index.md) / [&lt;init&gt;](.)

# &lt;init&gt;

`ClosedReceiveChannelException(message: String?)`

Indicates attempt to [receive](../-receive-channel/receive.md) on [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
channel that was closed *normally*. A *failed* channel rethrows the original [close](../-send-channel/close.md) cause
exception on receive attempts.

