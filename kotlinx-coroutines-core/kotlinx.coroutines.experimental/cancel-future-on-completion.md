[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [cancelFutureOnCompletion](.)

# cancelFutureOnCompletion

`fun `[`Job`](-job/index.md)`.cancelFutureOnCompletion(future: `[`Future`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/Future.html)`<*>): `[`Registration`](-job/-registration/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Job.kt#L130)

Cancels a specified [future](cancel-future-on-completion.md#kotlinx.coroutines.experimental$cancelFutureOnCompletion(kotlinx.coroutines.experimental.Job, java.util.concurrent.Future((kotlin.Any)))/future) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created).

```
onCompletion { future.cancel(true) }
```

