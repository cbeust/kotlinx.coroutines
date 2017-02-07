[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental](../index.md) / [CoroutineScope](.)

# CoroutineScope

`interface CoroutineScope` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineScope.kt#L26)

Receiver interface for generic coroutine builders, so that the code inside coroutine has a convenient access
to its [context](context.md) and cancellation status via [isActive](is-active.md).

### Properties

| Name | Summary |
|---|---|
| [context](context.md) | `abstract val context: CoroutineContext`<br>Returns the context of this coroutine. |
| [isActive](is-active.md) | `abstract val isActive: Boolean`<br>Returns `true` when this coroutine is still active (was not cancelled). |

### Inheritors

| Name | Summary |
|---|---|
| [ChannelBuilder](../../kotlinx.coroutines.experimental.channels/-channel-builder.md) | `interface ChannelBuilder<in E> : CoroutineScope, `[`SendChannel`](../../kotlinx.coroutines.experimental.channels/-send-channel/index.md)`<E>`<br>Scope for [buildChannel](../../kotlinx.coroutines.experimental.channels/build-channel.md). |
