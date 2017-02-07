[kotlinx-coroutines-nio](../../index.md) / [kotlinx.coroutines.experimental.nio](../index.md) / [java.nio.channels.AsynchronousServerSocketChannel](.)

### Extensions for java.nio.channels.AsynchronousServerSocketChannel

| Name | Summary |
|---|---|
| [aAccept](a-accept.md) | `suspend fun `[`AsynchronousServerSocketChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousServerSocketChannel.html)`.aAccept(): `[`AsynchronousSocketChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousSocketChannel.html)<br>Performs [AsynchronousServerSocketChannel.accept](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousServerSocketChannel.html#accept(A, java.nio.channels.CompletionHandler<java.nio.channels.AsynchronousSocketChannel,? super A>)) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#). |
