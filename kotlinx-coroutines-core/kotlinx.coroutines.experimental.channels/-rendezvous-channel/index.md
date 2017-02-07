[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [RendezvousChannel](.)

# RendezvousChannel

`class RendezvousChannel<E> : `[`AbstractChannel`](../-abstract-channel/index.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/RendezvousChannel.kt#L26)

Rendezvous channel. This channel does not have any buffer at all. An element is transferred from sender
to receiver only when [send](#) and [receive](../-abstract-channel/receive.md) invocations meet in time (rendezvous), so [send](#) suspends
until another coroutine invokes [receive](../-abstract-channel/receive.md) and [receive](../-abstract-channel/receive.md) suspends until another coroutine invokes [send](#).

This implementation is fully lock-free.

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `RendezvousChannel()`<br>Rendezvous channel. This channel does not have any buffer at all. An element is transferred from sender
to receiver only when [send](#) and [receive](../-abstract-channel/receive.md) invocations meet in time (rendezvous), so [send](#) suspends
until another coroutine invokes [receive](../-abstract-channel/receive.md) and [receive](../-abstract-channel/receive.md) suspends until another coroutine invokes [send](#). |

### Properties

| Name | Summary |
|---|---|
| [hasBuffer](has-buffer.md) | `val hasBuffer: Boolean` |
| [isBufferEmpty](is-buffer-empty.md) | `val isBufferEmpty: Boolean` |
| [isBufferFull](is-buffer-full.md) | `val isBufferFull: Boolean` |

### Inherited Properties

| Name | Summary |
|---|---|
| [closedForReceive](../-abstract-channel/closed-for-receive.md) | `val closedForReceive: Any?` |
| [closedForSend](../-abstract-channel/closed-for-send.md) | `val closedForSend: Any?` |
| [isClosedForReceive](../-abstract-channel/is-closed-for-receive.md) | `open val isClosedForReceive: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) on the [SendChannel](../-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](../-abstract-channel/receive.md) attempt
throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](../-send-channel/close.md) cause exception. |
| [isClosedForSend](../-abstract-channel/is-closed-for-send.md) | `open val isClosedForSend: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](../-abstract-channel/close.md) and thus
the [send](../-abstract-channel/send.md) attempt throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](../-abstract-channel/close.md) cause exception. |
| [isEmpty](../-abstract-channel/is-empty.md) | `open val isEmpty: Boolean`<br>Returns `true` if the channel is empty (contains no elements) and the [receive](../-abstract-channel/receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](../-abstract-channel/is-closed-for-receive.md) channel. |
| [isFull](../-abstract-channel/is-full.md) | `open val isFull: Boolean`<br>Returns `true` if the channel is full (out of capacity) and the [send](../-abstract-channel/send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](../-abstract-channel/is-closed-for-send.md) channel. |

### Functions

| Name | Summary |
|---|---|
| [offerInternal](offer-internal.md) | `fun offerInternal(element: E): Any`<br>Tries to add element to buffer or to queued receiver.
Return type is `OFFER_SUCCESS | OFFER_FAILED | Closed`. |
| [pollInternal](poll-internal.md) | `fun pollInternal(): Any?`<br>Tries to remove element from buffer or from queued sender.
Return type is `E | POLL_EMPTY | Closed` |

### Inherited Functions

| Name | Summary |
|---|---|
| [close](../-abstract-channel/close.md) | `open fun close(cause: Throwable?): Boolean`<br>Closes this channel with an optional exceptional [cause](../-abstract-channel/close.md#kotlinx.coroutines.experimental.channels.AbstractChannel$close(kotlin.Throwable)/cause).
This is an idempotent operation -- repeated invocations of this function have no effect and return `false`.
Conceptually, its sends a special close token of this channel. Immediately after invocation of this function
[isClosedForSend](../-abstract-channel/is-closed-for-send.md) starts returning `true`. However, [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
on the side of [ReceiveChannel](../-receive-channel/index.md) starts returning `true` only after all previously sent elements
are received. |
| [iterator](../-abstract-channel/iterator.md) | `open fun iterator(): `[`ChannelIterator`](../-channel-iterator/index.md)`<E>`<br>Returns new iterator to receive elements from this channels using `for` loop.
Iteration completes normally when the channel is [closed](../-abstract-channel/is-closed-for-receive.md) *normally* and
throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [poll](../-abstract-channel/poll.md) | `open fun poll(): E?`<br>Retrieves and removes the head of this queue, or returns `null` if this queue [isEmpty](../-abstract-channel/is-empty.md)
or is [closed](../-abstract-channel/is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [receive](../-abstract-channel/receive.md) | `open suspend fun receive(): E`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](../-abstract-channel/is-empty.md)
or throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md) if the channel [isClosedForReceive](../-abstract-channel/is-closed-for-receive.md).
If the channel was closed because of the exception, it is called a *failed* channel and this function
throws the original [close](../-send-channel/close.md) cause exception. |
| [receiveOrNull](../-abstract-channel/receive-or-null.md) | `open suspend fun receiveOrNull(): E?`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](../-abstract-channel/is-empty.md)
or returns `null` if the channel is [closed](../-abstract-channel/is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [takeFirstReceiveOrPeekClosed](../-abstract-channel/take-first-receive-or-peek-closed.md) | `fun takeFirstReceiveOrPeekClosed(): `[`ReceiveOrClosed`](../-abstract-channel/-receive-or-closed/index.md)`<E>?` |
| [takeFirstSendOrPeekClosed](../-abstract-channel/take-first-send-or-peek-closed.md) | `fun takeFirstSendOrPeekClosed(): `[`Send`](../-abstract-channel/-send/index.md)`?` |
