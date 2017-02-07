[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental.channels](index.md) / [buildChannel](.)

# buildChannel

`fun <E> buildChannel(context: CoroutineContext, capacity: Int = 0, block: @ExtensionFunctionType SuspendFunction1<`[`ChannelBuilder`](-channel-builder.md)`<E>, Unit>): `[`ChannelJob`](-channel-job.md)`<E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/ChannelBuilder.kt#L52)

Launches new coroutine without blocking current thread to send data over channel
and returns a reference to the coroutine as a [ChannelJob](-channel-job.md), which implements
both [Job](../kotlinx.coroutines.experimental/-job/index.md) and [ReceiveChannel](-receive-channel/index.md).
The scope of the coroutine contains [ChannelBuilder](-channel-builder.md) interface, which implements
both [CoroutineScope](../kotlinx.coroutines.experimental/-coroutine-scope/index.md) and [SendChannel](-send-channel/index.md), so that coroutine can invoke
[send](-send-channel/send.md) directly. The channel is [closed](-send-channel/close.md)
when the coroutine completes.
The running coroutine is cancelled when the its job is [cancelled](../kotlinx.coroutines.experimental/-job/cancel.md).

The [context](build-channel.md#kotlinx.coroutines.experimental.channels$buildChannel(kotlin.coroutines.experimental.CoroutineContext, kotlin.Int, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.channels.ChannelBuilder((kotlinx.coroutines.experimental.channels.buildChannel.E)), kotlin.Unit)))/context) for the new coroutine must be explicitly specified.
See [CoroutineDispatcher](../kotlinx.coroutines.experimental/-coroutine-dispatcher/index.md) for the standard [context](build-channel.md#kotlinx.coroutines.experimental.channels$buildChannel(kotlin.coroutines.experimental.CoroutineContext, kotlin.Int, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.channels.ChannelBuilder((kotlinx.coroutines.experimental.channels.buildChannel.E)), kotlin.Unit)))/context) implementations that are provided by `kotlinx.coroutines`.
The [context](../kotlinx.coroutines.experimental/-coroutine-scope/context.md) of the parent coroutine from its [scope](../kotlinx.coroutines.experimental/-coroutine-scope/index.md) may be used,
in which case the [Job](../kotlinx.coroutines.experimental/-job/index.md) of the resulting coroutine is a child of the job of the parent coroutine.

Uncaught exceptions in this coroutine close the channel with this exception as a cause and
the resulting channel becomes *failed*, so that any attempt to receive from such a channel throws exception.

See [newCoroutineContext](../kotlinx.coroutines.experimental/new-coroutine-context.md) for a description of debugging facilities that are available for newly created coroutine.

