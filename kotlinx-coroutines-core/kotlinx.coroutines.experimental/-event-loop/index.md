[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [EventLoop](.)

# EventLoop

`interface EventLoop` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/EventLoop.kt#L29)

Implemented by [CoroutineDispatcher](../-coroutine-dispatcher/index.md) implementations that have event loop inside and can
be asked to process next event from their event queue. It is used by [runBlocking](../run-blocking.md) to
continue processing events when invoked from the event dispatch thread.

### Functions

| Name | Summary |
|---|---|
| [processNextEvent](process-next-event.md) | `abstract fun processNextEvent(): Boolean`<br>Processes next event in this event loop and returns `true` or returns `false` if there are
no events to process or when invoked from the wrong thread. |

### Companion Object Functions

| Name | Summary |
|---|---|
| [invoke](invoke.md) | `operator fun invoke(thread: `[`Thread`](http://docs.oracle.com/javase/6/docs/api/java/lang/Thread.html)` = Thread.currentThread(), parentJob: `[`Job`](../-job/index.md)`? = null): `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md)<br>Creates a new event loop that is bound the specified [thread](invoke.md#kotlinx.coroutines.experimental.EventLoop.Factory$invoke(java.lang.Thread, kotlinx.coroutines.experimental.Job)/thread) (current thread by default) and
stops accepting new events when [parentJob](invoke.md#kotlinx.coroutines.experimental.EventLoop.Factory$invoke(java.lang.Thread, kotlinx.coroutines.experimental.Job)/parentJob) completes. Every continuation that is scheduled
onto this event loop unparks the specified thread via [LockSupport.unpark](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/locks/LockSupport.html#unpark(java.lang.Thread)). |
