# Concurrency
thread, work-manager, process, async

# [Coroutines](https://developer.android.com/kotlin/coroutines)

[Use of viewModelScope in MVP vs MVVM](https://github.com/shanraisshan/Notes/tree/main/App/Android/Architecture/Architecture#mvvm)


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

