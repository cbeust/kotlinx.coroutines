[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [handleCoroutineException](.)

# handleCoroutineException

`fun handleCoroutineException(context: CoroutineContext, exception: Throwable): Unit` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineExceptionHandler.kt#L32)

Helper function for coroutine builder implementations to handle uncaught exception in coroutines.
It tries to handle uncaught exception in the following way:

* If there is [CoroutineExceptionHandler](-coroutine-exception-handler/index.md) in the context, then it is used.
* Otherwise, if exception is [CancellationException](-cancellation-exception.md) then it is ignored
(because that is the supposed mechanism to cancel the running coroutine)
* Otherwise, if there is a [Job](-job/index.md) in the context, then [Job.cancel](-job/cancel.md) is invoked and if it
returns `true` (it was still active), then the exception is considered to be handled.
* Otherwise, current thread's [Thread.uncaughtExceptionHandler](#) is used.
