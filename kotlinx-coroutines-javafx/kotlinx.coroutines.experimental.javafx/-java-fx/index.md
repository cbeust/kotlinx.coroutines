[kotlinx-coroutines-javafx](../../index.md) / [kotlinx.coroutines.experimental.javafx](../index.md) / [JavaFx](.)

# JavaFx

`object JavaFx : CoroutineDispatcher, Delay` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-javafx/src/main/kotlin/kotlinx/coroutines/experimental/javafx/JavaFx.kt#L36)

Dispatches execution onto JavaFx application thread and provides native [delay](#) support.

### Functions

| Name | Summary |
|---|---|
| [awaitPulse](await-pulse.md) | `suspend fun awaitPulse(): Long`<br>Suspends coroutine until next JavaFx pulse and returns time of the pulse on resumption.
If the [Job](#) of the current coroutine is completed while this suspending function is waiting, this function
immediately resumes with [CancellationException](#) . |
| [dispatch](dispatch.md) | `fun dispatch(context: CoroutineContext, block: `[`Runnable`](http://docs.oracle.com/javase/6/docs/api/java/lang/Runnable.html)`): Unit` |
| [scheduleResumeAfterDelay](schedule-resume-after-delay.md) | `fun scheduleResumeAfterDelay(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)`, continuation: CancellableContinuation<Unit>): Unit` |
