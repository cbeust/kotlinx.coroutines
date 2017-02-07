

Core primitives to work with coroutines.

### All Types

| Name | Summary |
|---|---|
| [kotlinx.coroutines.experimental.channels.AbstractChannel](../kotlinx.coroutines.experimental.channels/-abstract-channel/index.md) | Abstract channel. It is a base class for buffered and unbuffered channels. |
| [kotlinx.coroutines.experimental.channels.ArrayChannel](../kotlinx.coroutines.experimental.channels/-array-channel/index.md) | Channel with array buffer of a fixed [capacity](../kotlinx.coroutines.experimental.channels/-array-channel/capacity.md).
Sender suspends only when buffer is fully and receiver suspends only when buffer is empty. |
| [kotlinx.coroutines.experimental.CancellableContinuation](../kotlinx.coroutines.experimental/-cancellable-continuation/index.md) | Cancellable continuation. Its job is completed when it is resumed or cancelled.
When [cancel](../kotlinx.coroutines.experimental/-job/cancel.md) function is explicitly invoked, this continuation resumes with [CancellationException](../kotlinx.coroutines.experimental/-cancellation-exception.md).
If the cancel reason was not a [CancellationException](../kotlinx.coroutines.experimental/-cancellation-exception.md), then the original exception is added as cause of the
[CancellationException](../kotlinx.coroutines.experimental/-cancellation-exception.md) that this continuation resumes with. |
| [kotlinx.coroutines.experimental.CancellationException](../kotlinx.coroutines.experimental/-cancellation-exception.md) | Thrown by cancellable suspending functions if the [Job](../kotlinx.coroutines.experimental/-job/index.md) of the coroutine is cancelled while it is suspending. |
| [kotlinx.coroutines.experimental.channels.Channel](../kotlinx.coroutines.experimental.channels/-channel/index.md) | Channel is a non-blocking primitive for communication between sender using [SendChannel](../kotlinx.coroutines.experimental.channels/-send-channel/index.md) and receiver using [ReceiveChannel](../kotlinx.coroutines.experimental.channels/-receive-channel/index.md).
Conceptually, a channel is similar to [BlockingQueue](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/BlockingQueue.html),
but it has suspending operations instead of blocking ones and it can be closed. |
| [kotlinx.coroutines.experimental.channels.ChannelBuilder](../kotlinx.coroutines.experimental.channels/-channel-builder.md) | Scope for [buildChannel](../kotlinx.coroutines.experimental.channels/build-channel.md). |
| [kotlinx.coroutines.experimental.channels.ChannelIterator](../kotlinx.coroutines.experimental.channels/-channel-iterator/index.md) | Iterator for [ReceiveChannel](../kotlinx.coroutines.experimental.channels/-receive-channel/index.md). Instances of this interface are *not thread-safe* and shall not be used
from concurrent coroutines. |
| [kotlinx.coroutines.experimental.channels.ChannelJob](../kotlinx.coroutines.experimental.channels/-channel-job.md) | Return type for [buildChannel](../kotlinx.coroutines.experimental.channels/build-channel.md). |
| [kotlinx.coroutines.experimental.channels.ClosedReceiveChannelException](../kotlinx.coroutines.experimental.channels/-closed-receive-channel-exception/index.md) | Indicates attempt to [receive](../kotlinx.coroutines.experimental.channels/-receive-channel/receive.md) on [isClosedForReceive](../kotlinx.coroutines.experimental.channels/-receive-channel/is-closed-for-receive.md)
channel that was closed *normally*. A *failed* channel rethrows the original [close](../kotlinx.coroutines.experimental.channels/-send-channel/close.md) cause
exception on receive attempts. |
| [kotlinx.coroutines.experimental.channels.ClosedSendChannelException](../kotlinx.coroutines.experimental.channels/-closed-send-channel-exception/index.md) | Indicates attempt to [send](../kotlinx.coroutines.experimental.channels/-send-channel/send.md) on [isClosedForSend](../kotlinx.coroutines.experimental.channels/-send-channel/is-closed-for-send.md) channel
that was closed *normally*. A *failed* channel rethrows the original [close](../kotlinx.coroutines.experimental.channels/-send-channel/close.md) cause
exception on send attempts. |
| [kotlinx.coroutines.experimental.CommonPool](../kotlinx.coroutines.experimental/-common-pool/index.md) | Represents common pool of shared threads as coroutine dispatcher for compute-intensive tasks.
It uses [java.util.concurrent.ForkJoinPool](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/ForkJoinPool.html) when available, which implements efficient work-stealing algorithm for its queues, so every
coroutine resumption is dispatched as a separate task even when it already executes inside the pool.
When available, it wraps `ForkJoinPool.commonPool` and provides a similar shared pool where not. |
| [kotlinx.coroutines.experimental.CompletionHandler](../kotlinx.coroutines.experimental/-completion-handler.md) |  |
| [kotlinx.coroutines.experimental.CoroutineDispatcher](../kotlinx.coroutines.experimental/-coroutine-dispatcher/index.md) | Base class that shall be extended by all coroutine dispatcher implementations. |
| [kotlinx.coroutines.experimental.CoroutineExceptionHandler](../kotlinx.coroutines.experimental/-coroutine-exception-handler/index.md) | An optional element on the coroutine context to handler uncaught exceptions.
See [handleCoroutineException](../kotlinx.coroutines.experimental/handle-coroutine-exception.md). |
| [kotlinx.coroutines.experimental.CoroutineName](../kotlinx.coroutines.experimental/-coroutine-name/index.md) | User-specified name of coroutine. This name is used in debugging mode.
See [newCoroutineContext](../kotlinx.coroutines.experimental/new-coroutine-context.md) for the description of coroutine debugging facilities. |
| [kotlinx.coroutines.experimental.CoroutineScope](../kotlinx.coroutines.experimental/-coroutine-scope/index.md) | Receiver interface for generic coroutine builders, so that the code inside coroutine has a convenient access
to its [context](../kotlinx.coroutines.experimental/-coroutine-scope/context.md) and cancellation status via [isActive](../kotlinx.coroutines.experimental/-coroutine-scope/is-active.md). |
| [kotlinx.coroutines.experimental.Deferred](../kotlinx.coroutines.experimental/-deferred/index.md) | Deferred value is conceptually a non-blocking cancellable future.
It is created with [defer](../kotlinx.coroutines.experimental/defer.md) coroutine builder.
It is in [active](../kotlinx.coroutines.experimental/-job/is-active.md) state while the value is being computed. |
| [kotlinx.coroutines.experimental.Delay](../kotlinx.coroutines.experimental/-delay/index.md) | This dispatcher *feature* is implemented by [CoroutineDispatcher](../kotlinx.coroutines.experimental/-coroutine-dispatcher/index.md) implementations that natively support
non-blocking [delay](../kotlinx.coroutines.experimental/-delay/delay.md) function. |
| [kotlinx.coroutines.experimental.EventLoop](../kotlinx.coroutines.experimental/-event-loop/index.md) | Implemented by [CoroutineDispatcher](../kotlinx.coroutines.experimental/-coroutine-dispatcher/index.md) implementations that have event loop inside and can
be asked to process next event from their event queue. It is used by [runBlocking](../kotlinx.coroutines.experimental/run-blocking.md) to
continue processing events when invoked from the event dispatch thread. |
| [java.util.concurrent.Executor](../kotlinx.coroutines.experimental/java.util.concurrent.-executor/index.md) (extensions in package kotlinx.coroutines.experimental) |  |
| [kotlinx.coroutines.experimental.Here](../kotlinx.coroutines.experimental/-here.md) |  |
| [kotlinx.coroutines.experimental.Job](../kotlinx.coroutines.experimental/-job/index.md) | A background job. It has two states: *active* (initial state) and *completed* (final state). |
| [kotlinx.coroutines.experimental.LazyDeferred](../kotlinx.coroutines.experimental/-lazy-deferred/index.md) | Lazy deferred value is conceptually a non-blocking cancellable future that is started on
the first [await](../kotlinx.coroutines.experimental/-deferred/await.md) or [start](../kotlinx.coroutines.experimental/-lazy-deferred/start.md) invocation.
It is created with [lazyDefer](../kotlinx.coroutines.experimental/lazy-defer.md) coroutine builder. |
| [kotlinx.coroutines.experimental.NonCancellable](../kotlinx.coroutines.experimental/-non-cancellable/index.md) | A non-cancelable job that is always [active](../kotlinx.coroutines.experimental/-non-cancellable/is-active.md). It is designed to be used with [run](../kotlinx.coroutines.experimental/run.md) builder
to prevent cancellation of code blocks that need to run without cancellation, like this |
| [kotlinx.coroutines.experimental.channels.ReceiveChannel](../kotlinx.coroutines.experimental.channels/-receive-channel/index.md) | Receiver's interface to [Channel](../kotlinx.coroutines.experimental.channels/-channel/index.md). |
| [kotlinx.coroutines.experimental.channels.RendezvousChannel](../kotlinx.coroutines.experimental.channels/-rendezvous-channel/index.md) | Rendezvous channel. This channel does not have any buffer at all. An element is transferred from sender
to receiver only when [send](#) and [receive](../kotlinx.coroutines.experimental.channels/-abstract-channel/receive.md) invocations meet in time (rendezvous), so [send](#) suspends
until another coroutine invokes [receive](../kotlinx.coroutines.experimental.channels/-abstract-channel/receive.md) and [receive](../kotlinx.coroutines.experimental.channels/-abstract-channel/receive.md) suspends until another coroutine invokes [send](#). |
| [kotlinx.coroutines.experimental.channels.SendChannel](../kotlinx.coroutines.experimental.channels/-send-channel/index.md) | Sender's interface to [Channel](../kotlinx.coroutines.experimental.channels/-channel/index.md). |
| [kotlin.coroutines.SuspendFunction0](../kotlinx.coroutines.experimental.intrinsics/kotlin.coroutines.-suspend-function0/index.md) (extensions in package kotlinx.coroutines.experimental.intrinsics) |  |
| [kotlinx.coroutines.experimental.Unconfined](../kotlinx.coroutines.experimental/-unconfined/index.md) | A coroutine dispatcher that is not confined to any specific thread.
It executes initial continuation of the coroutine *right here* in the current call-frame
and let the coroutine resume in whatever thread that is used by the corresponding suspending function, without
mandating any specific threading policy. |
