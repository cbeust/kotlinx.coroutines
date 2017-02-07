[kotlinx-coroutines-core](../../../index.md) / [kotlinx.coroutines.experimental.channels](../../index.md) / [AbstractChannel](../index.md) / [ReceiveOrClosed](.)

# ReceiveOrClosed

`protected interface ReceiveOrClosed<in E>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L306)

### Properties

| Name | Summary |
|---|---|
| [offerResult](offer-result.md) | `abstract val offerResult: Any` |

### Functions

| Name | Summary |
|---|---|
| [completeResumeReceive](complete-resume-receive.md) | `abstract fun completeResumeReceive(token: Any): Unit` |
| [tryResumeReceive](try-resume-receive.md) | `abstract fun tryResumeReceive(value: E): Any?` |
