[kotlinx-coroutines-javafx](../../index.md) / [kotlinx.coroutines.experimental.javafx](../index.md) / [JavaFx](index.md) / [awaitPulse](.)

# awaitPulse

`suspend fun awaitPulse(): Long` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-javafx/src/main/kotlin/kotlinx/coroutines/experimental/javafx/JavaFx.kt#L48)

Suspends coroutine until next JavaFx pulse and returns time of the pulse on resumption.
If the [Job](#) of the current coroutine is completed while this suspending function is waiting, this function
immediately resumes with [CancellationException](#) .

