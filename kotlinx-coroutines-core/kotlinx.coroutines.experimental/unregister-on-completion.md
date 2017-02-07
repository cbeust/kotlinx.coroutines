[kotlinx-coroutines-core](../index.md) / [kotlinx.coroutines.experimental](index.md) / [unregisterOnCompletion](.)

# unregisterOnCompletion

`fun `[`Job`](-job/index.md)`.unregisterOnCompletion(registration: `[`Registration`](-job/-registration/index.md)`): `[`Registration`](-job/-registration/index.md) [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-core/src/main/kotlin/kotlinx/coroutines/experimental/Job.kt#L120)

Unregisters a specified [registration](unregister-on-completion.md#kotlinx.coroutines.experimental$unregisterOnCompletion(kotlinx.coroutines.experimental.Job, kotlinx.coroutines.experimental.Job.Registration)/registration) when this job is complete.
This is a shortcut for the following code with slightly more efficient implementation (one fewer object created).

```
onCompletion { registration.unregister() }
```

