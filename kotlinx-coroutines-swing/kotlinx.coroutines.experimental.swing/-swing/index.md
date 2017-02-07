[kotlinx-coroutines-swing](../../index.md) / [kotlinx.coroutines.experimental.swing](../index.md) / [Swing](.)

# Swing

`object Swing : CoroutineDispatcher, Delay` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-swing/src/main/kotlin/kotlinx/coroutines/experimental/swing/Swing.kt#L32)

Dispatches execution onto Swing event dispatching thread and provides native [delay](#) support.

### Functions

| Name | Summary |
|---|---|
| [dispatch](dispatch.md) | `fun dispatch(context: CoroutineContext, block: `[`Runnable`](http://docs.oracle.com/javase/6/docs/api/java/lang/Runnable.html)`): Unit` |
| [isDispatchNeeded](is-dispatch-needed.md) | `fun isDispatchNeeded(context: CoroutineContext): Boolean` |
| [scheduleResumeAfterDelay](schedule-resume-after-delay.md) | `fun scheduleResumeAfterDelay(time: Long, unit: `[`TimeUnit`](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/TimeUnit.html)`, continuation: CancellableContinuation<Unit>): Unit` |
