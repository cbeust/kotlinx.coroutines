[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.channels](../index.md) / [SendChannel](.)

# SendChannel

`interface SendChannel<in E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/Channel.kt#L27)

Sender's interface to [Channel](../-channel/index.md).

### Properties

| Name | Summary |
|---|---|
| [isClosedForSend](is-closed-for-send.md) | `abstract val isClosedForSend: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](close.md) and thus
the [send](send.md) attempt throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](close.md) cause exception. |
| [isFull](is-full.md) | `abstract val isFull: Boolean`<br>Returns `true` if the channel is full (out of capacity) and the [send](send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](is-closed-for-send.md) channel. |

### Functions

| Name | Summary |
|---|---|
| [close](close.md) | `abstract fun close(cause: Throwable? = null): Boolean`<br>Closes this channel with an optional exceptional [cause](close.md#kotlinx.coroutines.experimental.channels.SendChannel$close(kotlin.Throwable)/cause).
This is an idempotent operation -- repeated invocations of this function have no effect and return `false`.
Conceptually, its sends a special close token of this channel. Immediately after invocation of this function
[isClosedForSend](is-closed-for-send.md) starts returning `true`. However, [isClosedForReceive](../-receive-channel/is-closed-for-receive.md)
on the side of [ReceiveChannel](../-receive-channel/index.md) starts returning `true` only after all previously sent elements
are received. |
| [offer](offer.md) | `abstract fun offer(element: E): Boolean`<br>Adds [element](offer.md#kotlinx.coroutines.experimental.channels.SendChannel$offer(kotlinx.coroutines.experimental.channels.SendChannel.E)/element) into this queue if it is possible to do so immediately without violating capacity restrictions
and returns `true`. Otherwise, it returns `false` immediately
or throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md) if the channel [isClosedForSend](is-closed-for-send.md) *normally*.
It throws the original [close](close.md) cause exception if the channel has *failed*. |
| [send](send.md) | `abstract suspend fun send(element: E): Unit`<br>Adds [element](send.md#kotlinx.coroutines.experimental.channels.SendChannel$send(kotlinx.coroutines.experimental.channels.SendChannel.E)/element) into to this queue, suspending the caller while this queue [isFull](is-full.md),
or throws [ClosedSendChannelException](../-closed-send-channel-exception/index.md) if the channel [isClosedForSend](is-closed-for-send.md) *normally*.
It throws the original [close](close.md) cause exception if the channel has *failed*. |

### Inheritors

| Name | Summary |
|---|---|
| [Channel](../-channel/index.md) | `interface Channel<E> : SendChannel<E>, `[`ReceiveChannel`](../-receive-channel/index.md)`<E>`<br>Channel is a non-blocking primitive for communication between sender using SendChannel and receiver using [ReceiveChannel](../-receive-channel/index.md).
Conceptually, a channel is similar to [BlockingQueue](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/BlockingQueue.html),
but it has suspending operations instead of blocking ones and it can be closed. |
| [ChannelBuilder](../-channel-builder.md) | `interface ChannelBuilder<in E> : `[`CoroutineScope`](../../kotlinx.coroutines.experimental/-coroutine-scope/index.md)`, SendChannel<E>`<br>Scope for [buildChannel](../build-channel.md). |
