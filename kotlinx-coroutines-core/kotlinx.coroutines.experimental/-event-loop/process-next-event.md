[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [EventLoop](index.md) / [processNextEvent](.)

# processNextEvent

`abstract fun processNextEvent(): Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/EventLoop.kt#L34)

Processes next event in this event loop and returns `true` or returns `false` if there are
no events to process or when invoked from the wrong thread.

