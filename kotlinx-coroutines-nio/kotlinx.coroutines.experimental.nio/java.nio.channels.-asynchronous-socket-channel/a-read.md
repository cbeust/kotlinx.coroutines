[kotlinx-coroutines-nio](../../index.md) / [kotlinx.coroutines.experimental.nio](../index.md) / [java.nio.channels.AsynchronousSocketChannel](index.md) / [aRead](.)

# aRead

`suspend fun `[`AsynchronousSocketChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousSocketChannel.html)`.aRead(buf: `[`ByteBuffer`](http://docs.oracle.com/javase/6/docs/api/java/nio/ByteBuffer.html)`, timeout: Long = 0L, timeUnit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS): Int` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-nio/src/main/kotlin/kotlinx/coroutines/experimental/nio/Nio.kt#L112)

Performs [AsynchronousServerSocketChannel.read](#) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#).

