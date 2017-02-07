[kotlinx-coroutines-nio](../../index.md) / [kotlinx.coroutines.experimental.nio](../index.md) / [java.nio.channels.AsynchronousSocketChannel](index.md) / [aConnect](.)

# aConnect

`suspend fun `[`AsynchronousSocketChannel`](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/AsynchronousSocketChannel.html)`.aConnect(socketAddress: `[`SocketAddress`](http://docs.oracle.com/javase/6/docs/api/java/net/SocketAddress.html)`): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-nio/src/main/kotlin/kotlinx/coroutines/experimental/nio/Nio.kt#L99)

Performs [AsynchronousServerSocketChannel.connect](#) without blocking a thread and resumes when asynchronous operation completes.
This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is suspended, this function
*closes the underlying channel* and immediately resumes with [CancellationException](#).

