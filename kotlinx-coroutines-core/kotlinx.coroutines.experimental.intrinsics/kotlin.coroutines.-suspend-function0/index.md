[kotlinx-coroutines-core](../../index.md) / [kotlinx.coroutines.experimental.intrinsics](../index.md) / [kotlin.coroutines.SuspendFunction0](.)

### Extensions for kotlin.coroutines.SuspendFunction0

| Name | Summary |
|---|---|
| [startCoroutineOrReturn](start-coroutine-or-return.md) | `fun <T> SuspendFunction0<T>.startCoroutineOrReturn(completion: Continuation<T>): Any?`<br>Starts coroutine without receiver and with result type [T](#).
This function creates and start a new, fresh instance of suspendable computation every time it is invoked.
If the coroutine never suspends, then its result is returned directly,
otherwise it returns [COROUTINE_SUSPENDED](#) and the [completion](start-coroutine-or-return.md#kotlinx.coroutines.experimental.intrinsics$startCoroutineOrReturn(kotlin.coroutines.SuspendFunction0((kotlinx.coroutines.experimental.intrinsics.startCoroutineOrReturn.T)), kotlin.coroutines.experimental.Continuation((kotlinx.coroutines.experimental.intrinsics.startCoroutineOrReturn.T)))/completion) continuation is invoked when coroutine completes. |
