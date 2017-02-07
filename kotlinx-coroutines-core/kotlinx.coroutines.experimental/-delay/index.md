[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Delay](.)

# Delay

`interface Delay` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Delay.kt#L26)

This dispatcher *feature* is implemented by [CoroutineDispatcher](../-coroutine-dispatcher/index.md) implementations that natively support
non-blocking [delay](delay.md) function.

### Functions

| Name | Summary |
|---|---|
| [delay](delay.md) | `open suspend fun delay(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)` = TimeUnit.MILLISECONDS): Unit`<br>Delays coroutine for a given time without blocking a thread and resumes it after a specified time.
This suspending function is cancellable.
If the [Job](../-job/index.md) of the current coroutine is completed while this suspending function is suspended, this function
immediately resumes with [CancellationException](../-cancellation-exception.md). |
| [scheduleResumeAfterDelay](schedule-resume-after-delay.md) | `abstract fun scheduleResumeAfterDelay(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)`, continuation: `[`CancellableContinuation`](../-cancellable-continuation/index.md)`<Unit>): Unit`<br>Schedules resume of a specified [continuation](schedule-resume-after-delay.md#kotlinx.coroutines.experimental.Delay$scheduleResumeAfterDelay(kotlin.Long, java.util.concurrent.TimeUnit, kotlinx.coroutines.experimental.CancellableContinuation((kotlin.Unit)))/continuation) after a specified delay [time](schedule-resume-after-delay.md#kotlinx.coroutines.experimental.Delay$scheduleResumeAfterDelay(kotlin.Long, java.util.concurrent.TimeUnit, kotlinx.coroutines.experimental.CancellableContinuation((kotlin.Unit)))/time). |
