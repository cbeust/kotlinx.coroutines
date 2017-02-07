[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [newCoroutineContext](.)

# newCoroutineContext

`fun newCoroutineContext(context: CoroutineContext): CoroutineContext` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/CoroutineContext.kt#L70)

Creates context for the new coroutine with optional support for debugging facilities (when turned on).

**Debugging facilities:** In debug mode every coroutine is assigned a unique consecutive identifier.
Every thread that executes a coroutine has its name modified to include the name and identifier of the
currently currently running coroutine.
When one coroutine is suspended and resumes another coroutine that is dispatched in the same thread,
then the thread name displays
the whole stack of coroutine descriptions that are being executed on this thread.

Enable debugging facilities with "`kotlinx.coroutines.debug`" system property, use the following values:

* "`auto`" (default mode) -- enabled when assertions are enabled with "`-ea`" JVM option.
* "`on`" or empty string -- enabled.
* "`off`" -- disabled.

Coroutine name can be explicitly assigned using [CoroutineName](-coroutine-name/index.md) context element.
The string "coroutine" is used as a default name.

