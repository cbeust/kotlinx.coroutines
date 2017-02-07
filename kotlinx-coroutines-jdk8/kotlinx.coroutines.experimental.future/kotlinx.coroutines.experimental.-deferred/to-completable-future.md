[kotlinx-coroutines-jdk8](../../index.md) / [kotlinx.coroutines.experimental.future](../index.md) / [kotlinx.coroutines.experimental.Deferred](index.md) / [toCompletableFuture](.)

# toCompletableFuture

`fun <T> Deferred<T>.toCompletableFuture(): `[`CompletableFuture`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html)`<T>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-jdk8/src/main/kotlin/kotlinx/coroutines/experimental/future/Future.kt#L51)

Converts this deferred value to the instance of [CompletableFuture](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html).
The deferred value is cancelled when the resulting future is cancelled or otherwise completed.

