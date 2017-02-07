[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [Delay](index.md) / [scheduleResumeAfterDelay](.)

# scheduleResumeAfterDelay

`abstract fun scheduleResumeAfterDelay(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)`, continuation: `[`CancellableContinuation`](../-cancellable-continuation/index.md)`<Unit>): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Delay.kt#L42)

Schedules resume of a specified [continuation](schedule-resume-after-delay.md#kotlinx.coroutines.experimental.Delay$scheduleResumeAfterDelay(kotlin.Long, java.util.concurrent.TimeUnit, kotlinx.coroutines.experimental.CancellableContinuation((kotlin.Unit)))/continuation) after a specified delay [time](schedule-resume-after-delay.md#kotlinx.coroutines.experimental.Delay$scheduleResumeAfterDelay(kotlin.Long, java.util.concurrent.TimeUnit, kotlinx.coroutines.experimental.CancellableContinuation((kotlin.Unit)))/time).

