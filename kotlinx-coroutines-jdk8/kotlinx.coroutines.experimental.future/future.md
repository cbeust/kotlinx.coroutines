[kotlinx-coroutines-jdk8](../index.md) / [kotlinx.coroutines.experimental.future](index.md) / [future](.)

# future

`fun <T> future(context: CoroutineContext = CommonPool, block: SuspendFunction0<T>): `[`CompletableFuture`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html)`<T>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-jdk8/src/main/kotlin/kotlinx/coroutines/experimental/future/Future.kt#L37)

Starts new coroutine and returns its results an an implementation of [CompletableFuture](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html).
This coroutine builder uses [CommonPool](#) context by default and is conceptually similar to [CompletableFuture.supplyAsync](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html#supplyAsync(java.util.function.Supplier<U>)).

The running coroutine is cancelled when the resulting future is cancelled or otherwise completed.
If the [context](future.md#kotlinx.coroutines.experimental.future$future(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction0((kotlinx.coroutines.experimental.future.future.T)))/context) for the new coroutine is explicitly specified, then it must include [CoroutineDispatcher](#) element.
See [CoroutineDispatcher](#) for the standard [context](future.md#kotlinx.coroutines.experimental.future$future(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction0((kotlinx.coroutines.experimental.future.future.T)))/context) implementations that are provided by `kotlinx.coroutines`.
The specified context is added to the context of the parent running coroutine (if any) inside which this function
is invoked. The [Job](#) of the resulting coroutine is a child of the job of the parent coroutine (if any).

See [newCoroutineContext](#) for a description of debugging facilities that are available for newly created coroutine.

