# Concurrency
thread, work-manager, process, async

# [Coroutines](https://developer.android.com/kotlin/coroutines)
Co+Routine - Co means Coopearion, Routine means Function. [when functions cooperate with each other](https://www.youtube.com/watch?v=EUlpxloAcWw&list=PLBF0Hb1Nl6I-GZS5U1FrCYHvWK-5qmDgc&t=969)

## [Coroutine beautifully explained](https://outcomeschool.com/blog/kotlin-coroutines)
```kotlin
fun functionA(case: Int) {
    when (case) {
        1 -> {
            taskA1()
            functionB(1)
        }
        2 -> {
            taskA2()
            functionB(2)
        }
        3 -> {
            taskA3()
            functionB(3)
        }
        4 -> {
            taskA4()
            functionB(4)
        }
    }
}
```

### Example: viewModelScope - [MVP vs MVVM](https://github.com/shanraisshan/Notes/tree/main/App/Android/Architecture/Architecture#mvvm)

### Example: Savyour
```kotlin
view.lifecycleScope.launch {
    val moderationApi = view.lifecycleScope.async { view.moderationApi(question) }
    repository?.prompt(x, object :
        InterfaceCallbackGeneral<BaseResponse<Prompt>> {
            override fun onSuccess(r: BaseResponse<Prompt>, message: String?) {
                lifecycleScope.launch {
                    val flagged = moderationApi.await()
                    r.data?.let { view.callChatBotApi(question,questionMethod,flagged,it) }
                }
            }
            override fun onNetworkError(message: String,exceptionMessage: String) {}
        })
}
```

## Scopes
[types of scopes in kotlin](https://medium.com/@sujathamudadla1213/how-many-types-of-scopes-are-there-in-kotlin-android-e44e004450d0)
Scope|Defination
-|-
GlobalScope|lifetime of application
CoroutineScope|UI components
ViewModelScopre|specific type of CoroutineScope tied to the lifecycle of a ViewModel (performing background tasks, data retrieval, or asynchronous operations within a ViewModel)
LifecycleScope|Activity or Fragment

## Dispatchers
[Dispatchers help coroutines in deciding the thread on which the work has to be done](https://outcomeschool.com/blog/kotlin-coroutines#:~:text=Dispatchers%20help%20coroutines)
Dispatcher|Defination
-|-
Dispatchers.Default|This dispatcher is optimized for CPU-intensive work (sorting, searching list in memory)
Dispatchers.Main|This dispatcher is designed for UI-related tasks in Android applications. 
Dispatchers.IO|such as network or database operations.
Dispatchers.Unconfined|This dispatcher runs the coroutine in the caller thread until the first suspension point. After suspension, it resumes execution in the appropriate thread, which might be different from the original caller thread.

