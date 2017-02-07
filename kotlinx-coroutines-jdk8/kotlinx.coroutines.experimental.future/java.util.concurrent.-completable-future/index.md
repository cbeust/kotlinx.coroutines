[kotlinx-coroutines-jdk8](../../index.md) / [kotlinx.coroutines.experimental.future](../index.md) / [java.util.concurrent.CompletableFuture](.)

### Extensions for java.util.concurrent.CompletableFuture

| Name | Summary |
|---|---|
| [await](await.md) | `suspend fun <T> `[`CompletableFuture`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/CompletableFuture.html)`<T>.await(): T`<br>Awaits for completion of the future without blocking a thread. This suspending function is cancellable.
If the [Job](#) of the current coroutine is completed while this suspending function is waiting, this function
immediately resumes with [CancellationException](#) . |
