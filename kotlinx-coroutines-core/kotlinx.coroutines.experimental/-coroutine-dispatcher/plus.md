[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineDispatcher](index.md) / [plus](.)

# plus

`operator fun ~~plus~~(other: `[`CoroutineDispatcher`](index.md)`): `[`CoroutineDispatcher`](index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineDispatcher.kt#L62)
**Deprecated:** Operator '+' on two CoroutineDispatcher objects is meaningless. CoroutineDispatcher is a coroutine context element and `+` is a set-sum operator for coroutine contexts. The dispatcher to the right of `+` just replaces the dispacher the left of `+`.

