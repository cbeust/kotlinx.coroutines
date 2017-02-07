[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineName](.)

# CoroutineName

`data class CoroutineName : AbstractCoroutineContextElement` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineName.kt#L26)

User-specified name of coroutine. This name is used in debugging mode.
See [newCoroutineContext](../new-coroutine-context.md) for the description of coroutine debugging facilities.

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `CoroutineName(name: String)`<br>User-specified name of coroutine. This name is used in debugging mode.
See [newCoroutineContext](../new-coroutine-context.md) for the description of coroutine debugging facilities. |

### Properties

| Name | Summary |
|---|---|
| [name](name.md) | `val name: String` |

### Functions

| Name | Summary |
|---|---|
| [toString](to-string.md) | `fun toString(): String` |
