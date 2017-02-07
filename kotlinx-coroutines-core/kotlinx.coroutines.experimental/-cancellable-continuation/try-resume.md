[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CancellableContinuation](index.md) / [tryResume](.)

# tryResume

`abstract fun tryResume(value: T): Any?` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CancellableContinuation.kt#L45)

Tries to resume this continuation with a given value and returns non-null object token if it was successful,
or `null` otherwise (it was already resumed or cancelled). When non-null object was returned,
[completeResume](complete-resume.md) must be invoked with it.

