# Dependency Injection
dagger, hilt, koin

```
do not create hardcode 'Engine' object inside a 'Car', instead pass all dependencies ('Engine') as parameters
```

How to explain dependency injection to a 5-year-old?

https://stackoverflow.com/q/1638919/4754141


### Tutorial Followed
|Desc|Name|Link|
|:-:|:-:|:-:
|Basic(Hindi)|Cheezy Code|https://www.youtube.com/watch?v=DtzQkBp2M5M&list=PLRKyZvuMYSIPwjYw1bt_7u7nEwe6vATQd

### [Why Dependency Injection?](https://youtu.be/DtzQkBp2M5M?list=PLRKyZvuMYSIPwjYw1bt_7u7nEwe6vATQd&t=146)

![why-dependency-injection](https://github.com/shanraisshan/Notes/blob/main/Android/Architecture/Pattern/Dependency/!/why-dependency-injection.png)

|#|Types Of Injection|
|:-:|:-:|
|1|Constructor Injection|
|2|Field Injection|

# DAGGER 2
[Dagger ko aap 1 programmer samjh saktay ho, jo aap ki madad karta hai 1 acha code likhnay mein](https://youtu.be/cg0yCHW2Keg?t=130)

[Concept](https://youtu.be/cg0yCHW2Keg?t=139)

![dagger1](https://github.com/shanraisshan/Notes/blob/main/Android/Architecture/Pattern/Dependency/!/dagger1.png)
![dagger2](https://github.com/shanraisshan/Notes/blob/main/Android/Architecture/Pattern/Dependency/!/dagger2.png)

# HILT

### Migration Steps (Dagger 2 to Hilt) 

1. Application -> @HiltAndroidApp
2. All Activities/Fragments/Service -> @AndroidEntryPoint
3. Repository -> @Inject constructor
4. RemoteDataSource -> @Inject constructor
5. for abstract class/interface (ApiClass) -> create module class and provide methods

![hilt1](https://github.com/shanraisshan/Notes/blob/main/Android/Architecture/Pattern/Dependency/!/hilt1.png)
![hilt2](https://github.com/shanraisshan/Notes/blob/main/Android/Architecture/Pattern/Dependency/!/hilt2.png)
![hilt3](https://github.com/shanraisshan/Notes/blob/main/Android/Architecture/Pattern/Dependency/!/hilt3.png)
![hilt4](https://github.com/shanraisshan/Notes/blob/main/Android/Architecture/Pattern/Dependency/!/hilt4.png)
