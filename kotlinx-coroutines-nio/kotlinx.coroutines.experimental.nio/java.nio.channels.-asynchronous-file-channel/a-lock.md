[kotlinx-coroutines-nio](../../index.md) / [kotlinx.coroutines.experimental.nio](../index.md) / [java.nio.channels.AsynchronousFileChannel](index.md) / [aLock](.)

# aLock

`suspend fun `[`AsynchronousFileChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html)`.aLock(): `[`FileLock`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/FileLock.html) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-nio/src/main/kotlin/kotlinx/coroutines/experimental/nio/Nio.kt#L34)
`suspend fun `[`AsynchronousFileChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html)`.aLock(position: Long, size: Long, shared: Boolean): `[`FileLock`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/FileLock.html) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-nio/src/main/kotlin/kotlinx/coroutines/experimental/nio/Nio.kt#L45)

Performs [AsynchronousFileChannel.lock](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousFileChannel.html#lock(long, long, boolean, A, java.nio.channels.CompletionHandler<java.nio.channels.FileLock,? super A>)) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#).

