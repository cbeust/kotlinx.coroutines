[kotlinx-coroutines-jdk8](../index.md) / [kotlinx.coroutines.experimental.future](.)

## Package kotlinx.coroutines.experimental.future

### Extensions for External Classes

| Name | Summary |
|---|---|
| [java.util.concurrent.CompletableFuture](java.util.concurrent.-completable-future/index.md) |  |
| [kotlinx.coroutines.experimental.Deferred](kotlinx.coroutines.experimental.-deferred/index.md) |  |

### Functions

| Name | Summary |
|---|---|
| [future](future.md) | `fun <T> future(context: CoroutineContext = CommonPool, block: SuspendFunction0<T>): `[`CompletableFuture`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html)`<T>`<br>Starts new coroutine and returns its results an an implementation of [CompletableFuture](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html).
This coroutine builder uses [CommonPool](#) context by default and is conceptually similar to [CompletableFuture.supplyAsync](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html#supplyAsync(java.util.function.Supplier<U>)). |
