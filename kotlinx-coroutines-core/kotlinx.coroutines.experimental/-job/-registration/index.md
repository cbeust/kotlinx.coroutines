[kotlinx-coroutines-core](../../../index.md) / [kotlinx.coroutines.experimental](../../index.md) / [Job](../index.md) / [Registration](.)

# Registration

`interface Registration` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Job.kt#L98)

Registration object for [onCompletion](../on-completion.md). It can be used to [unregister](unregister.md) if needed.
There is no need to unregister after completion.

### Functions

| Name | Summary |
|---|---|
| [unregister](unregister.md) | `abstract fun unregister(): Unit`<br>Unregisters completion handler. |
