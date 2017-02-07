[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ClosedSendChannelException](index.md) / [&lt;init&gt;](.)

# &lt;init&gt;

`ClosedSendChannelException(message: String?)`

Indicates attempt to [send](../-send-channel/send.md) on [isClosedForSend](../-send-channel/is-closed-for-send.md) channel
that was closed *normally*. A *failed* channel rethrows the original [close](../-send-channel/close.md) cause
exception on send attempts.

