[kotlinx-coroutines-nio](../../index.md) / [kotlinx.coroutines.experimental.nio](../index.md) / [java.nio.channels.AsynchronousFileChannel](index.md) / [aRead](.)

# aRead

`suspend fun `[`AsynchronousFileChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html)`.aRead(buf: `[`ByteBuffer`](http://docs.oracle.com/javase/6/docs/api/java/nio/ByteBuffer.html)`, position: Long): Int` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-nio/src/main/kotlin/kotlinx/coroutines/experimental/nio/Nio.kt#L60)

Performs [AsynchronousFileChannel.read](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html#read(java.nio.ByteBuffer, long, A, java.nio.channels.CompletionHandler<java.lang.Integer,? super A>)) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#).

