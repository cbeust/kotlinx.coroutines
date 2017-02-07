[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [delay](.)

# delay

`suspend fun delay(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Delay.kt#L54)

Delays coroutine for a given time without blocking a thread and resumes it after a specified time.
This suspending function is cancellable.
If the [Job](-job/index.md) of the current coroutine is completed while this suspending function is suspended, this function
immediately resumes with [CancellationException](-cancellation-exception.md).

This function delegates to [Delay](-delay/index.md) implementation of the context [CoroutineDispatcher](-coroutine-dispatcher/index.md) if possible,
otherwise it resumes using a built-in single-threaded scheduled executor service.

