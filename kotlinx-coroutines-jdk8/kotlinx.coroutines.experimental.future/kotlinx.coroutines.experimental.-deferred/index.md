[kotlinx-coroutines-jdk8](../../index.md) / [kotlinx.coroutines.experimental.future](../index.md) / [kotlinx.coroutines.experimental.Deferred](.)

### Extensions for kotlinx.coroutines.experimental.Deferred

| Name | Summary |
|---|---|
| [toCompletableFuture](to-completable-future.md) | `fun <T> Deferred<T>.toCompletableFuture(): `[`CompletableFuture`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html)`<T>`<br>Converts this deferred value to the instance of [CompletableFuture](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html).
The deferred value is cancelled when the resulting future is cancelled or otherwise completed. |
