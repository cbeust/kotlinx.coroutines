[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [ReceiveChannel](.)

# ReceiveChannel

`interface ReceiveChannel<out E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L83)

Receiver's interface to [Channel](../-channel/index.md).

### Properties

| Name | Summary |
|---|---|
| [isClosedForReceive](is-closed-for-receive.md) | `abstract val isClosedForReceive: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](../-send-channel/close.md) on the [SendChannel](../-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](receive.md) attempt
throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](../-send-channel/close.md) cause exception. |
| [isEmpty](is-empty.md) | `abstract val isEmpty: Boolean`<br>Returns `true` if the channel is empty (contains no elements) and the [receive](receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](is-closed-for-receive.md) channel. |

### Functions

| Name | Summary |
|---|---|
| [iterator](iterator.md) | `abstract operator fun iterator(): `[`ChannelIterator`](../-channel-iterator/index.md)`<E>`<br>Returns new iterator to receive elements from this channels using `for` loop.
Iteration completes normally when the channel is [closed](is-closed-for-receive.md) *normally* and
throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [poll](poll.md) | `abstract fun poll(): E?`<br>Retrieves and removes the head of this queue, or returns `null` if this queue [isEmpty](is-empty.md)
or is [closed](is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |
| [receive](receive.md) | `abstract suspend fun receive(): E`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](is-empty.md)
or throws [ClosedReceiveChannelException](../-closed-receive-channel-exception/index.md) if the channel [isClosedForReceive](is-closed-for-receive.md).
If the channel was closed because of the exception, it is called a *failed* channel and this function
throws the original [close](../-send-channel/close.md) cause exception. |
| [receiveOrNull](receive-or-null.md) | `abstract suspend fun receiveOrNull(): E?`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](is-empty.md)
or returns `null` if the channel is [closed](is-closed-for-receive.md) *normally*,
or throws the original [close](../-send-channel/close.md) cause exception if the channel has *failed*. |

### Inheritors

| Name | Summary |
|---|---|
| [Channel](../-channel/index.md) | `interface Channel<E> : `[`SendChannel`](../-send-channel/index.md)`<E>, ReceiveChannel<E>`<br>Channel is a non-blocking primitive for communication between sender using [SendChannel](../-send-channel/index.md) and receiver using ReceiveChannel.
Conceptually, a channel is similar to [BlockingQueue](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/BlockingQueue.html),
but it has suspending operations instead of blocking ones and it can be closed. |
| [ChannelJob](../-channel-job.md) | `interface ChannelJob<out E> : `[`Job`](../../kotlinx.coroutines.experimental/-job/index.md)`, ReceiveChannel<E>`<br>Return type for [buildChannel](../build-channel.md). |
