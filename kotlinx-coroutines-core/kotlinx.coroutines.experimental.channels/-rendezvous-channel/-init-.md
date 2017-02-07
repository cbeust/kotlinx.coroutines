[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [RendezvousChannel](index.md) / [&lt;init&gt;](.)

# &lt;init&gt;

`RendezvousChannel()`

Rendezvous channel. This channel does not have any buffer at all. An element is transferred from sender
to receiver only when [send](#) and [receive](../-abstract-channel/receive.md) invocations meet in time (rendezvous), so [send](#) suspends
until another coroutine invokes [receive](../-abstract-channel/receive.md) and [receive](../-abstract-channel/receive.md) suspends until another coroutine invokes [send](#).

This implementation is fully lock-free.

