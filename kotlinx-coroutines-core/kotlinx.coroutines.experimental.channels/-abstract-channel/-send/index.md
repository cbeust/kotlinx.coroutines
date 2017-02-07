[kotlinx-coroutines-core](../../../index.md) / [kotlinx.coroutines.experimental.channels](../../index.md) / [AbstractChannel](../index.md) / [Send](.)

# Send

`protected interface Send` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/channels/AbstractChannel.kt#L300)

### Properties

| Name | Summary |
|---|---|
| [pollResult](poll-result.md) | `abstract val pollResult: Any?` |

### Functions

| Name | Summary |
|---|---|
| [completeResumeSend](complete-resume-send.md) | `abstract fun completeResumeSend(token: Any): Unit` |
| [tryResumeSend](try-resume-send.md) | `abstract fun tryResumeSend(): Any?` |
