[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental.channels](index.md) / [ChannelJob](.)

# ChannelJob

`interface ChannelJob<out E> : `[`Job`](../kotlinx.coroutines.experimental/-job/index.md)`, `[`ReceiveChannel`](-receive-channel/index.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/ChannelBuilder.kt#L30)

Return type for [buildChannel](build-channel.md).

### Inherited Properties

| Name | Summary |
|---|---|
| [isActive](../kotlinx.coroutines.experimental/-job/is-active.md) | `abstract val isActive: Boolean`<br>Returns `true` when job is still active. |
| [isClosedForReceive](-receive-channel/is-closed-for-receive.md) | `abstract val isClosedForReceive: Boolean`<br>Returns `true` if this channel was closed by invocation of [close](-send-channel/close.md) on the [SendChannel](-send-channel/index.md)
side and all previously sent items were already received, so that the [receive](-receive-channel/receive.md) attempt
throws [ClosedReceiveChannelException](-closed-receive-channel-exception/index.md). If the channel was closed because of the exception, it
is considered closed, too, but it is called a *failed* channel. All suspending attempts to receive
an element from a failed channel throw the original [close](-send-channel/close.md) cause exception. |
| [isEmpty](-receive-channel/is-empty.md) | `abstract val isEmpty: Boolean`<br>Returns `true` if the channel is empty (contains no elements) and the [receive](-receive-channel/receive.md) attempt will suspend.
This function returns `false` for [isClosedForReceive](-receive-channel/is-closed-for-receive.md) channel. |

### Inherited Functions

| Name | Summary |
|---|---|
| [cancel](../kotlinx.coroutines.experimental/-job/cancel.md) | `abstract fun cancel(cause: Throwable? = null): Boolean`<br>Cancel this activity with an optional cancellation [cause](../kotlinx.coroutines.experimental/-job/cancel.md#kotlinx.coroutines.experimental.Job$cancel(kotlin.Throwable)/cause). The result is `true` if this job was
cancelled as a result of this invocation and `false` otherwise
(if it was already cancelled or it is [NonCancellable](../kotlinx.coroutines.experimental/-non-cancellable/index.md)).
Repeated invocation of this function has no effect and always produces `false`. |
| [getInactiveCancellationException](../kotlinx.coroutines.experimental/-job/get-inactive-cancellation-exception.md) | `abstract fun getInactiveCancellationException(): `[`CancellationException`](../kotlinx.coroutines.experimental/-cancellation-exception.md)<br>Returns [CancellationException](../kotlinx.coroutines.experimental/-cancellation-exception.md) that [cancellable](../kotlinx.coroutines.experimental/suspend-cancellable-coroutine.md) suspending functions throw when
trying to suspend in the context of this job. This function throws [IllegalAccessException](http://docs.oracle.com/javase/6/docs/api/java/lang/IllegalAccessException.html) when invoked
for an [active](../kotlinx.coroutines.experimental/-job/is-active.md) job. |
| [iterator](-receive-channel/iterator.md) | `abstract operator fun iterator(): `[`ChannelIterator`](-channel-iterator/index.md)`<E>`<br>Returns new iterator to receive elements from this channels using `for` loop.
Iteration completes normally when the channel is [closed](-receive-channel/is-closed-for-receive.md) *normally* and
throws the original [close](-send-channel/close.md) cause exception if the channel has *failed*. |
| [onCompletion](../kotlinx.coroutines.experimental/-job/on-completion.md) | `abstract fun onCompletion(handler: `[`CompletionHandler`](../kotlinx.coroutines.experimental/-completion-handler.md)`): `[`Registration`](../kotlinx.coroutines.experimental/-job/-registration/index.md)<br>Registers completion handler. The action depends on the state of this job.
When job is cancelled with [cancel](../kotlinx.coroutines.experimental/-job/cancel.md), then the handler is immediately invoked
with a cancellation reason. Otherwise, handler will be invoked once when this
job is complete (cancellation also is a form of completion).
The resulting [Registration](../kotlinx.coroutines.experimental/-job/-registration/index.md) can be used to [Registration.unregister](../kotlinx.coroutines.experimental/-job/-registration/unregister.md) if this
registration is no longer needed. There is no need to unregister after completion. |
| [plus](../kotlinx.coroutines.experimental/-job/plus.md) | `open operator fun ~~plus~~(other: `[`Job`](../kotlinx.coroutines.experimental/-job/index.md)`): `[`Job`](../kotlinx.coroutines.experimental/-job/index.md) |
| [poll](-receive-channel/poll.md) | `abstract fun poll(): E?`<br>Retrieves and removes the head of this queue, or returns `null` if this queue [isEmpty](-receive-channel/is-empty.md)
or is [closed](-receive-channel/is-closed-for-receive.md) *normally*,
or throws the original [close](-send-channel/close.md) cause exception if the channel has *failed*. |
| [receive](-receive-channel/receive.md) | `abstract suspend fun receive(): E`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](-receive-channel/is-empty.md)
or throws [ClosedReceiveChannelException](-closed-receive-channel-exception/index.md) if the channel [isClosedForReceive](-receive-channel/is-closed-for-receive.md).
If the channel was closed because of the exception, it is called a *failed* channel and this function
throws the original [close](-send-channel/close.md) cause exception. |
| [receiveOrNull](-receive-channel/receive-or-null.md) | `abstract suspend fun receiveOrNull(): E?`<br>Retrieves and removes the element from this channel suspending the caller while this channel [isEmpty](-receive-channel/is-empty.md)
or returns `null` if the channel is [closed](-receive-channel/is-closed-for-receive.md) *normally*,
or throws the original [close](-send-channel/close.md) cause exception if the channel has *failed*. |

### Extension Functions

| Name | Summary |
|---|---|
| [cancelFutureOnCompletion](../kotlinx.coroutines.experimental/cancel-future-on-completion.md) | `fun `[`Job`](../kotlinx.coroutines.experimental/-job/index.md)`.cancelFutureOnCompletion(future: `[`Future`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/Future.html)`<*>): `[`Registration`](../kotlinx.coroutines.experimental/-job/-registration/index.md)<br>Cancels a specified [future](../kotlinx.coroutines.experimental/cancel-future-on-completion.md#kotlinx.coroutines.experimental$cancelFutureOnCompletion(kotlinx.coroutines.experimental.Job, java.util.concurrent.Future((kotlin.Any)))/future) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
| [join](../kotlinx.coroutines.experimental/join.md) | `suspend fun `[`Job`](../kotlinx.coroutines.experimental/-job/index.md)`.join(): Unit`<br>Suspends coroutine until this job is complete. This invocation resumes normally (without exception)
when the job is complete for any reason. |
| [unregisterOnCompletion](../kotlinx.coroutines.experimental/unregister-on-completion.md) | `fun `[`Job`](../kotlinx.coroutines.experimental/-job/index.md)`.unregisterOnCompletion(registration: `[`Registration`](../kotlinx.coroutines.experimental/-job/-registration/index.md)`): `[`Registration`](../kotlinx.coroutines.experimental/-job/-registration/index.md)<br>Unregisters a specified [registration](../kotlinx.coroutines.experimental/unregister-on-completion.md#kotlinx.coroutines.experimental$unregisterOnCompletion(kotlinx.coroutines.experimental.Job, kotlinx.coroutines.experimental.Job.Registration)/registration) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created). |
