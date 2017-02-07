[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental.channels](index.md) / [ChannelBuilder](.)

# ChannelBuilder

`interface ChannelBuilder<in E> : `[`CoroutineScope`](../kotlinx.coroutines.experimental/-coroutine-scope/index.md)`, `[`SendChannel`](-send-channel/index.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/ChannelBuilder.kt#L25)

Scope for [buildChannel](build-channel.md).

### Inherited Properties

| Name | Summary |
|---|---|
| [context](../kotlinx.coroutines.experimental/-coroutine-scope/context.md) | `abstract val context: CoroutineContext`<br>Returns the context of this coroutine. |
| [isActive](../kotlinx.coroutines.experimental/-coroutine-scope/is-active.md) | `abstract val isActive: Boolean`<br>Returns `true` when this coroutine is still active (was not cancelled). |
| [isClosedForSend](-send-channel/is-closed-for-send.md) | `abstract val isClosedForSend: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](-send-channel/close.md) and thus
the [send](-send-channel/send.md) attempt throws [ClosedSendChannelException](-closed-send-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to send
an element to a failed channel throw the original [close](-send-channel/close.md) cause exception. |
| [isFull](-send-channel/is-full.md) | `abstract val isFull: Boolean`<br>Returns `true` if the channel is full (out of capacity) and the [send](-send-channel/send.md) attempt will suspend.
This function returns `false` for [isClosedForSend](-send-channel/is-closed-for-send.md) channel. |

### Inherited Functions

| Name | Summary |
|---|---|
| [close](-send-channel/close.md) | `abstract fun close(cause: Throwable? = null): Boolean`<br>Closes this channel with an optional exceptional [cause](-send-channel/close.md#kotlinx.coroutines.experimental.channels.SendChannel$close(kotlin.Throwable)/cause).
This is an idempotent operation -- repeated invocations of this function have no effect and return `false`.
Conceptually, its sends a special close token of this channel. Immediately after invocation of this function
[isClosedForSend](-send-channel/is-closed-for-send.md) starts returning `true`. However, [isClosedForReceive](-receive-channel/is-closed-for-receive.md)
on the side of [ReceiveChannel](-receive-channel/index.md) starts returning `true` only after all previously sent elements
are received. |
