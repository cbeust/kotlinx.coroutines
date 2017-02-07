[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [runBlocking](.)

# runBlocking

`fun <T> runBlocking(context: CoroutineContext = EmptyCoroutineContext, block: @ExtensionFunctionType SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, T>): T` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Builders.kt#L74)

Runs new coroutine and *blocks* current thread *interruptibly* until its completion.
This function should not be used from coroutine. It is designed to bridge regular blocking code
to libraries that are written in suspending style, to be used in `main` functions and in tests.

The default [CoroutineDispatcher](-coroutine-dispatcher/index.md) for this builder in an implementation of [EventLoop](-event-loop/index.md) that processes continuations
in this blocked thread until the completion of this coroutine.
See [CoroutineDispatcher](-coroutine-dispatcher/index.md) for the other implementations that are provided by `kotlinx.coroutines`.

If this blocked thread is interrupted (see [Thread.interrupt](http://docs.oracle.com/javase/6/docs/api/java/lang/Thread.html#interrupt())), then the coroutine job is cancelled and
this `runBlocking` invocation throws [InterruptedException](http://docs.oracle.com/javase/6/docs/api/java/lang/InterruptedException.html).

See [newCoroutineContext](new-coroutine-context.md) for a description of debugging facilities that are available for newly created coroutine.

