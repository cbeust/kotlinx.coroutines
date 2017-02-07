[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ArrayChannel](index.md) / [&lt;init&gt;](.)

# &lt;init&gt;

`ArrayChannel(capacity: Int)`

Channel with array buffer of a fixed [capacity](-init-.md#kotlinx.coroutines.experimental.channels.ArrayChannel$<init>(kotlin.Int)/capacity).
Sender suspends only when buffer is fully and receiver suspends only when buffer is empty.

This implementation uses lock to protect the buffer, which is held only during very short buffer-update operations.
The lists of suspended senders or receivers are lock-free.

