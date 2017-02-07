[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [EventLoop](index.md) / [invoke](.)

# invoke

`operator fun invoke(thread: `[`Thread`](http://docs.oracle.com/javase/6/docs/api/java/lang/Thread.html)` = Thread.currentThread(), parentJob: `[`Job`](../-job/index.md)`? = null): `[`CoroutineDispatcher`](../-coroutine-dispatcher/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/EventLoop.kt#L50)

Creates a new event loop that is bound the specified [thread](invoke.md#kotlinx.coroutines.experimental.EventLoop.Factory$invoke(java.lang.Thread, kotlinx.coroutines.experimental.Job)/thread) (current thread by default) and
stops accepting new events when [parentJob](invoke.md#kotlinx.coroutines.experimental.EventLoop.Factory$invoke(java.lang.Thread, kotlinx.coroutines.experimental.Job)/parentJob) completes. Every continuation that is scheduled
onto this event loop unparks the specified thread via [LockSupport.unpark](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/locks/LockSupport.html#unpark(java.lang.Thread)).

The main event-processing loop using the resulting `eventLoop` object should look like this:

```
while (needsToBeRunning) {
    if (Thread.interrupted()) break // or handle somehow
    if (!eventLoop.processNextEvent()) LockSupport.park() // event loop will unpark
}
```

