[kotlinx-coroutines-nio](../../index.md) / [kotlinx.coroutines.experimental.nio](../index.md) / [java.nio.channels.AsynchronousSocketChannel](.)

### Extensions for java.nio.channels.AsynchronousSocketChannel

| Name | Summary |
|---|---|
| [aConnect](a-connect.md) | `suspend fun `[`AsynchronousSocketChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousSocketChannel.html)`.aConnect(socketAddress: `[`SocketAddress`](http://docs.oracle.com/javase/6/docs/api/java/net/SocketAddress.html)`): Unit`<br>Performs [AsynchronousServerSocketChannel.connect](#) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#). |
| [aRead](a-read.md) | `suspend fun `[`AsynchronousSocketChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousSocketChannel.html)`.aRead(buf: `[`ByteBuffer`](http://docs.oracle.com/javase/6/docs/api/java/nio/ByteBuffer.html)`, timeout: Long = 0L, timeUnit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS): Int`<br>Performs [AsynchronousServerSocketChannel.read](#) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#). |
| [aWrite](a-write.md) | `suspend fun `[`AsynchronousSocketChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousSocketChannel.html)`.aWrite(buf: `[`ByteBuffer`](http://docs.oracle.com/javase/6/docs/api/java/nio/ByteBuffer.html)`, timeout: Long = 0L, timeUnit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS): Int`<br>Performs [AsynchronousServerSocketChannel.write](#) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#). |
