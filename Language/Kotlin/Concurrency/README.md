# Concurrency
thread, work-manager, process, async

# [Coroutines](https://developer.android.com/kotlin/coroutines)
Co+Routine - Co means Coopearion, Routine means Function. [when functions cooperate with each other](https://www.youtube.com/watch?v=EUlpxloAcWw&list=PLBF0Hb1Nl6I-GZS5U1FrCYHvWK-5qmDgc&t=969)

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

