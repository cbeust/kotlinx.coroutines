[kotlinx-coroutines-rx](../index.md) / [kotlinx.coroutines.experimental.rx](index.md) / [rxSingle](.)

# rxSingle

`fun <T> rxSingle(context: CoroutineContext = EmptyCoroutineContext, block: SuspendFunction0<T>): Observable<T>` [(source)](http://github.com/kotlin/kotlinx.coroutines/tree/master/kotlinx-coroutines-rx/src/main/kotlin/kotlinx/coroutines/experimental/rx/asyncRx.kt#L35)

Run asynchronous computations based on [block](rx-single.md#kotlinx.coroutines.experimental.rx$rxSingle(kotlin.coroutines.experimental.CoroutineContext, kotlin.coroutines.SuspendFunction0((kotlinx.coroutines.experimental.rx.rxSingle.T)))/block) coroutine parameter

Execution starts immediately within the 'asyncRx' call and it runs until
the first suspension point is reached ('*await' call for some Observable instance).
Remaining part of coroutine will be executed as it's passed into 'subscribe'
call of awaited Observable.

### Parameters

`block` - a coroutine representing reactive computations

**Return**
Observable with single value containing expression returned from coroutine

