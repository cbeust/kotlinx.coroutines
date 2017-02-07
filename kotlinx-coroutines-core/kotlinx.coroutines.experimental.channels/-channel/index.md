[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [Channel](.)

# Channel

`interface Channel<E> : `[`SendChannel`](../-send-channel/index.md)`<E>, `[`ReceiveChannel`](../-receive-channel/index.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L191)

Channel is a non-blocking primitive for communication between sender using [SendChannel](../-send-channel/index.md) and receiver using [ReceiveChannel](../-receive-channel/index.md).
Conceptually, a channel is similar to [BlockingQueue](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/BlockingQueue.html),
but it has suspending operations instead of blocking ones and it can be closed.

### Inherited Properties

| Name | Summary |
|---|---|
| [isClosedForReceive](../-receive-channel/is-closed-for-receive.md) | `abstract val isClosedForReceive: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) on the [SendChannel](../-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](../-receive-channel/receive.md) attempt
throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](../-send-channel/close.md) cause exception. |
| [isClosedForSend](../-send-channel/is-closed-for-send.md) | `abstract val isClosedForSend: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) and thus
the [send](../-send-channel/send.md) attempt throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](../-send-channel/close.md) cause exception. |
| [isEmpty](../-receive-channel/is-empty.md) | `abstract val isEmpty: Boolean`<br>Returns `true` if the channel is empty (contains no elements) and the [receive](../-receive-channel/receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](../-receive-channel/is-closed-for-receive.md) channel. |
| [isFull](../-send-channel/is-full.md) | `abstract val isFull: Boolean`<br>Returns `true` if the channel is full (out of capacity) and the [send](../-send-channel/send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](../-send-channel/is-closed-for-send.md) channel. |

### Inherited Functions

| Name | Summary |
|---|---|
| [close](../-send-channel/close.md) | `abstract fun close(cause: Throwable? = null): Boolean`<br>Closes this channel with an optional exceptional [cause](../-send-channel/close.md#kotlinx.coroutines.experimental.channels.SendChannel$close(kotlin.Throwable)/cause).
This is an idempotent operation -- repeated invocations of this function have no effect and return `false`.
Conceptually, its sends a special close token of this channel. Immediately after invocation of this function
[isClosedForSend](../-send-channel/is-closed-for-send.md) starts returning `true`. However, [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
on the side of [ReceiveChannel](../-receive-channel/index.md) starts returning `true` only after all previously sent elements
are received. |
| [iterator](../-receive-channel/iterator.md) | `abstract operator fun iterator(): `[`ChannelIterator`](../-channel-iterator/index.md)`<E>`<br>Returns new iterator to receive elements from this channels using `for` loop.
Iteration completes normally when the channel is [closed](../-receive-channel/is-closed-for-receive.md) *normally* and
throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [poll](../-receive-channel/poll.md) | `abstract fun poll(): E?`<br>Retrieves and removes the head of this queue, or returns `null` if this queue [isEmpty](../-receive-channel/is-empty.md)
or is [closed](../-receive-channel/is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [receive](../-receive-channel/receive.md) | `abstract suspend fun receive(): E`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](../-receive-channel/is-empty.md)
or throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md) if the channel [isClosedForReceive](../-receive-channel/is-closed-for-receive.md).
If the channel was closed because of the exception, it is called a *failed* channel and this function
throws the original [close](../-send-channel/close.md) cause exception. |
| [receiveOrNull](../-receive-channel/receive-or-null.md) | `abstract suspend fun receiveOrNull(): E?`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](../-receive-channel/is-empty.md)
or returns `null` if the channel is [closed](../-receive-channel/is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |

### Companion Object Functions

| Name | Summary |
|---|---|
| [invoke](invoke.md) | `operator fun <E> invoke(capacity: Int = 0): Channel<E>`<br>Creates a channel with specified buffer capacity (or without a buffer by default). |

### Inheritors

| Name | Summary |
|---|---|
| [AbstractChannel](../-abstract-channel/index.md) | `abstract class AbstractChannel<E> : Channel<E>`<br>Abstract channel. It is a base class for buffered and unbuffered channels. |
