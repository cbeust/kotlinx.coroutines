[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [launch](.)

# launch

`fun launch(context: CoroutineContext, block: @ExtensionFunctionType SuspendFunction1<`[`CoroutineScope`](-coroutine-scope/index.md)`, Unit>): `[`Job`](-job/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Builders.kt#L39)

Launches new coroutine without blocking current thread and returns a reference to the coroutine as a [Job](-job/index.md).
The running coroutine is cancelled when the resulting job is [cancelled](-job/cancel.md).

The [context](launch.md#kotlinx.coroutines.experimental$launch(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.CoroutineScope, kotlin.Unit)))/context) for the new coroutine must be explicitly specified.
See [CoroutineDispatcher](-coroutine-dispatcher/index.md) for the standard [context](launch.md#kotlinx.coroutines.experimental$launch(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction1((kotlinx.coroutines.experimental.CoroutineScope, kotlin.Unit)))/context) implementations that are provided by `kotlinx.coroutines`.
The [context](-coroutine-scope/context.md) of the parent coroutine from its [scope](-coroutine-scope/index.md) may be used,
in which case the [Job](-job/index.md) of the resulting coroutine is a child of the job of the parent coroutine.

Uncaught exceptions in this coroutine cancel parent job in the context by default
(unless [CoroutineExceptionHandler](-coroutine-exception-handler/index.md) is explicitly specified), which means that when `launch` is used with
the context of another coroutine, then any uncaught exception leads to the cancellation of parent coroutine.

See [newCoroutineContext](new-coroutine-context.md) for a description of debugging facilities that are available for newly created coroutine.

