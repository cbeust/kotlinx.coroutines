[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [withTimeout](.)

# withTimeout

`suspend fun <T> withTimeout(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS, block: SuspendFunction0<T>): T` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Scheduled.kt#L44)

Runs a given suspending block of code inside a coroutine with a specified timeout and throws
[CancellationException](-cancellation-exception.md) if timeout was exceeded.

