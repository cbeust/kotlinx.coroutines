[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental.channels](.)

## Package kotlinx.coroutines.experimental.channels

Channels -- non-blocking primitives for communicating a stream of values between coroutines.

* `Channel`, `SendChannel`, and `ReceiveChannel` interfaces,
* `RendezvousChannel` (unbuffered) and `ArrayChannel` (buffered) implementations
* `Channel()` factory function and `buildChannel{}` coroutines builder.

### Types

| Name | Summary |
|---|---|
| [AbstractChannel](-abstract-channel/index.md) | `abstract class AbstractChannel<E> : `[`Channel`](-channel/index.md)`<E>`<br>Abstract channel. It is a base class for buffered and unbuffered channels. |
| [ArrayChannel](-array-channel/index.md) | `class ArrayChannel<E> : `[`AbstractChannel`](-abstract-channel/index.md)`<E>`<br>Channel with array buffer of a fixed [capacity](-array-channel/capacity.md).
Sender suspends only when buffer is fully and receiver suspends only when buffer is empty. |
| [Channel](-channel/index.md) | `interface Channel<E> : `[`SendChannel`](-send-channel/index.md)`<E>, `[`ReceiveChannel`](-receive-channel/index.md)`<E>`<br>Channel is a non-blocking primitive for communication between sender using [SendChannel](-send-channel/index.md) and receiver using [ReceiveChannel](-receive-channel/index.md).
Conceptually, a channel is similar to [BlockingQueue](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/BlockingQueue.html),
but it has suspending operations instead of blocking ones and it can be closed. |
| [ChannelBuilder](-channel-builder.md) | `interface ChannelBuilder<in E> : `[`CoroutineScope`](../kotlinx.coroutines.experimental/-coroutine-scope/index.md)`, `[`SendChannel`](-send-channel/index.md)`<E>`<br>Scope for [buildChannel](build-channel.md). |
| [ChannelIterator](-channel-iterator/index.md) | `interface ChannelIterator<out E>`<br>Iterator for [ReceiveChannel](-receive-channel/index.md). Instances of this interface are *not thread-safe* and shall not be used
from concurrent coroutines. |
| [ChannelJob](-channel-job.md) | `interface ChannelJob<out E> : `[`Job`](../kotlinx.coroutines.experimental/-job/index.md)`, `[`ReceiveChannel`](-receive-channel/index.md)`<E>`<br>Return type for [buildChannel](build-channel.md). |
| [ReceiveChannel](-receive-channel/index.md) | `interface ReceiveChannel<out E>`<br>Receiver's interface to [Channel](-channel/index.md). |
| [RendezvousChannel](-rendezvous-channel/index.md) | `class RendezvousChannel<E> : `[`AbstractChannel`](-abstract-channel/index.md)`<E>`<br>Rendezvous channel. This channel does not have any buffer at all. An element is transferred from sender
to receiver only when [send](#) and [receive](-abstract-channel/receive.md) invocations meet in time (rendezvous), so [send](#) suspends
until another coroutine invokes [receive](-abstract-channel/receive.md) and [receive](-abstract-channel/receive.md) suspends until another coroutine invokes [send](#). |
| [SendChannel](-send-channel/index.md) | `interface SendChannel<in E>`<br>Sender's interface to [Channel](-channel/index.md). |

### Exceptions

| Name | Summary |
|---|---|
| [ClosedReceiveChannelException](-closed-receive-channel-exception/index.md) | `class ClosedReceiveChannelException : NoSuchElementException`<br>Indicates attempt to [receive](-receive-channel/receive.md) on [isClosedForReceive](-receive-channel/is-closed-for-receive.md)
channel that was closed *normally*. A *failed* channel rethrows the original [close](-send-channel/close.md) cause
exception on receive attempts. |
| [ClosedSendChannelException](-closed-send-channel-exception/index.md) | `class ClosedSendChannelException : IllegalStateException`<br>Indicates attempt to [send](-send-channel/send.md) on [isClosedForSend](-send-channel/is-closed-for-send.md) channel
that was closed *normally*. A *failed* channel rethrows the original [close](-send-channel/close.md) cause
exception on send attempts. |

### Functions

| Name | Summary |
|---|---|
| [buildChannel](build-channel.md) | `fun <E> buildChannel(context: CoroutineContext, capacity: Int = 0, block: SuspendFunction1<`[`ChannelBuilder`](-channel-builder.md)`<E>, Unit>): `[`ChannelJob`](-channel-job.md)`<E>`<br>Launches new coroutine without blocking current thread to send data over channel
and returns a reference to the coroutine as a [ChannelJob](-channel-job.md), which implements
both [Job](../kotlinx.coroutines.experimental/-job/index.md) and [ReceiveChannel](-receive-channel/index.md).
The scope of the coroutine contains [ChannelBuilder](-channel-builder.md) interface, which implements
both [CoroutineScope](../kotlinx.coroutines.experimental/-coroutine-scope/index.md) and [SendChannel](-send-channel/index.md), so that coroutine can invoke
[send](-send-channel/send.md) directly. The channel is [closed](-send-channel/close.md)
when the coroutine completes.
The running coroutine is cancelled when the its job is [cancelled](../kotlinx.coroutines.experimental/-job/cancel.md). |
