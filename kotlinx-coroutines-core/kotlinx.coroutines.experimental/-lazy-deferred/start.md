[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [LazyDeferred](index.md) / [start](.)

# start

`abstract fun start(): Boolean` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/LazyDeferred.kt#L46)

Starts coroutine to compute this lazily deferred value. The result `true` if this invocation actually
started coroutine or `false` if it was already started or cancelled.

