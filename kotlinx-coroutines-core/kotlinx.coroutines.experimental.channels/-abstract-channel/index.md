[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [AbstractChannel](.)

# AbstractChannel

`abstract class AbstractChannel<E> : `[`Channel`](../-channel/index.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L28)

Abstract channel. It is a base class for buffered and unbuffered channels.

### Types

| Name | Summary |
|---|---|
| [ReceiveOrClosed](-receive-or-closed/index.md) | `interface ReceiveOrClosed<in E>` |
| [Send](-send/index.md) | `interface Send` |

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `AbstractChannel()`<br>Abstract channel. It is a base class for buffered and unbuffered channels. |

### Properties

| Name | Summary |
|---|---|
| [closedForReceive](closed-for-receive.md) | `val closedForReceive: Any?` |
| [closedForSend](closed-for-send.md) | `val closedForSend: Any?` |
| [hasBuffer](has-buffer.md) | `abstract val hasBuffer: Boolean` |
| [isBufferEmpty](is-buffer-empty.md) | `abstract val isBufferEmpty: Boolean` |
| [isBufferFull](is-buffer-full.md) | `abstract val isBufferFull: Boolean` |
| [isClosedForReceive](is-closed-for-receive.md) | `open val isClosedForReceive: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) on the [SendChannel](../-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](receive.md) attempt
throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](../-send-channel/close.md) cause exception. |
| [isClosedForSend](is-closed-for-send.md) | `open val isClosedForSend: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](close.md) and thus
the [send](send.md) attempt throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](close.md) cause exception. |
| [isEmpty](is-empty.md) | `open val isEmpty: Boolean`<br>Returns `true` if the channel is empty (contains no elements) and the [receive](receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](is-closed-for-receive.md) channel. |
| [isFull](is-full.md) | `open val isFull: Boolean`<br>Returns `true` if the channel is full (out of capacity) and the [send](send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](is-closed-for-send.md) channel. |

### Functions

| Name | Summary |
|---|---|
| [close](close.md) | `open fun close(cause: Throwable?): Boolean`<br>Closes this channel with an optional exceptional [cause](close.md#kotlinx.coroutines.experimental.channels.AbstractChannel$close(kotlin.Throwable)/cause).
This is an idempotent operation -- repeated invocations of this function have no effect and return `false`.
Conceptually, its sends a special close token of this channel. Immediately after invocation of this function
[isClosedForSend](is-closed-for-send.md) starts returning `true`. However, [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
on the side of [ReceiveChannel](../-receive-channel/index.md) starts returning `true` only after all previously sent elements
are received. |
| [iterator](iterator.md) | `open fun iterator(): `[`ChannelIterator`](../-channel-iterator/index.md)`<E>`<br>Returns new iterator to receive elements from this channels using `for` loop.
Iteration completes normally when the channel is [closed](is-closed-for-receive.md) *normally* and
throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [offer](offer.md) | `open fun offer(element: E): Boolean`<br>Adds [element](offer.md#kotlinx.coroutines.experimental.channels.AbstractChannel$offer(kotlinx.coroutines.experimental.channels.AbstractChannel.E)/element) into this queue if it is possible to do so immediately without violating capacity restrictions
and returns `true`. Otherwise, it returns `false` immediately
or throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md) if the channel [isClosedForSend](is-closed-for-send.md) *normally*.
It throws the original [close](close.md) cause exception if the channel has *failed*. |
| [offerInternal](offer-internal.md) | `abstract fun offerInternal(element: E): Any`<br>Tries to add element to buffer or to queued receiver.
Return type is `OFFER_SUCCESS | OFFER_FAILED | Closed`. |
| [poll](poll.md) | `open fun poll(): E?`<br>Retrieves and removes the head of this queue, or returns `null` if this queue [isEmpty](is-empty.md)
or is [closed](is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [pollInternal](poll-internal.md) | `abstract fun pollInternal(): Any?`<br>Tries to remove element from buffer or from queued sender.
Return type is `E | POLL_EMPTY | Closed` |
| [receive](receive.md) | `open suspend fun receive(): E`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](is-empty.md)
or throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md) if the channel [isClosedForReceive](is-closed-for-receive.md).
If the channel was closed because of the exception, it is called a *failed* channel and this function
throws the original [close](../-send-channel/close.md) cause exception. |
| [receiveOrNull](receive-or-null.md) | `open suspend fun receiveOrNull(): E?`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](is-empty.md)
or returns `null` if the channel is [closed](is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [send](send.md) | `open suspend fun send(element: E): Unit`<br>Adds [element](send.md#kotlinx.coroutines.experimental.channels.AbstractChannel$send(kotlinx.coroutines.experimental.channels.AbstractChannel.E)/element) into to this queue, suspending the caller while this queue [isFull](is-full.md),
or throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md) if the channel [isClosedForSend](is-closed-for-send.md) *normally*.
It throws the original [close](close.md) cause exception if the channel has *failed*. |
| [takeFirstReceiveOrPeekClosed](take-first-receive-or-peek-closed.md) | `fun takeFirstReceiveOrPeekClosed(): `[`ReceiveOrClosed`](-receive-or-closed/index.md)`<E>?` |
| [takeFirstSendOrPeekClosed](take-first-send-or-peek-closed.md) | `fun takeFirstSendOrPeekClosed(): `[`Send`](-send/index.md)`?` |

### Companion Object Properties

| Name | Summary |
|---|---|
| [DEFAULT_CLOSE_MESSAGE](-d-e-f-a-u-l-t_-c-l-o-s-e_-m-e-s-s-a-g-e.md) | `const val DEFAULT_CLOSE_MESSAGE: String` |
| [OFFER_FAILED](-o-f-f-e-r_-f-a-i-l-e-d.md) | `val OFFER_FAILED: Any` |
| [OFFER_SUCCESS](-o-f-f-e-r_-s-u-c-c-e-s-s.md) | `val OFFER_SUCCESS: Any` |
| [POLL_EMPTY](-p-o-l-l_-e-m-p-t-y.md) | `val POLL_EMPTY: Any` |

### Companion Object Functions

| Name | Summary |
|---|---|
| [isClosed](is-closed.md) | `fun isClosed(result: Any?): Boolean` |

### Inheritors

| Name | Summary |
|---|---|
| [ArrayChannel](../-array-channel/index.md) | `class ArrayChannel<E> : AbstractChannel<E>`<br>Channel with array buffer of a fixed [capacity](../-array-channel/capacity.md).
Sender suspends only when buffer is fully and receiver suspends only when buffer is empty. |
| [RendezvousChannel](../-rendezvous-channel/index.md) | `class RendezvousChannel<E> : AbstractChannel<E>`<br>Rendezvous channel. This channel does not have any buffer at all. An element is transferred from sender
to receiver only when [send](#) and [receive](receive.md) invocations meet in time (rendezvous), so [send](#) suspends
until another coroutine invokes [receive](receive.md) and [receive](receive.md) suspends until another coroutine invokes [send](#). |
