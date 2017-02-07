[kotlinx-coroutines-nio](../../index.md) / [kotlinx.coroutines.experimental.nio](../index.md) / [java.nio.channels.AsynchronousFileChannel](.)

### Extensions for java.nio.channels.AsynchronousFileChannel

| Name | Summary |
|---|---|
| [aLock](a-lock.md) | `suspend fun `[`AsynchronousFileChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html)`.aLock(): `[`FileLock`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/FileLock.html)<br>`suspend fun `[`AsynchronousFileChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html)`.aLock(position: Long, size: Long, shared: Boolean): `[`FileLock`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/FileLock.html)<br>Performs [AsynchronousFileChannel.lock](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html#lock(long, long, boolean, A, java.nio.channels.CompletionHandler<java.nio.channels.FileLock,? super A>)) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#). |
| [aRead](a-read.md) | `suspend fun `[`AsynchronousFileChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html)`.aRead(buf: `[`ByteBuffer`](http://docs.oracle.com/javase/6/docs/api/java/nio/ByteBuffer.html)`, position: Long): Int`<br>Performs [AsynchronousFileChannel.read](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html#read(java.nio.ByteBuffer, long, A, java.nio.channels.CompletionHandler<java.lang.Integer,? super A>)) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#). |
| [aWrite](a-write.md) | `suspend fun `[`AsynchronousFileChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html)`.aWrite(buf: `[`ByteBuffer`](http://docs.oracle.com/javase/6/docs/api/java/nio/ByteBuffer.html)`, position: Long): Int`<br>Performs [AsynchronousFileChannel.write](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html#write(java.nio.ByteBuffer, long, A, java.nio.channels.CompletionHandler<java.lang.Integer,? super A>)) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#). |
