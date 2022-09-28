# Basic

# [var - val - const val](https://pl.kotl.in/dyle-3t_D)
```kotlin
const val c=1

fun main() {
    
    var a=1
    a=2
    println("var " + a) //2

    val b=1
    //b=2 //Val cannot be reassigned
    println("val " + b)
    
    //val as mutable
    val obj = Test()
    println("val " + obj.b) //10
    obj.a = 20
    println("val " + obj.b) //20
    
    //const val c=1 //Modifier 'const' is not applicable to 'local variable'
    println("const val " + c)
}

class Test {
    var a: Int = 10
    val b get()=a
}
```

# [INPUT](https://ideone.com/V4txKj)
```kotlin
import java.util.*
fun main(args: Array<String>) {
    //method 1
    val xInteger = readLine() //007
    val yString = readLine() //kotlin
    println(xInteger + yString) //007kotlin
 
    //method 2
    val sc = Scanner(System.`in`)
    val a = sc.nextInt() //2
    val b = sc.nextInt() //3
    println(a + b) //5
}
```

# [STRING](https://pl.kotl.in/r9QQ840Oc)
```kotlin
var name1: String = "abcdef"
var name2: String = "abcdyz"
for(i in 0 until name1.length) { //length
    if(name1.get(i) == name2.get(i)) //get(i)
        println("logs-> true ${name1.get(i)} + ${name2.get(i)}") //true a + a
}
println(name1.substring(2,3)) //c -> substring(startIndex, endIndex(not included))
name1 = name1.substring(0,2).plus(name1.substring(3)) //remove character at index
println(name1) //abdef
```

# [CONDITION](https://pl.kotl.in/8UpHUDgt9)
```kotlin
//if expression
println( if(a>b) a else b ) //2
    
//ternary a ? b : c
println( a.takeIf{a>b} ?: b ) //2
    
//when
println( when(a>b) { true->a false->b } ) //2
```

# [FUNCTION](https://pl.kotl.in/ZdTU0UzbY)

> The support for var was removed way back coz this was confusing: people tend to think that this means passing a parameter by reference, which we do not support (it is costly at runtime) [-> details](https://stackoverflow.com/a/68822771/4754141)


```kotlin
fun func1(a:String) {} //valid

fun func2(var a:String) {} //'var' on function parameter is not allowed

fun func3(val a:String) {} //'val' on function parameter is not allowed

//constructor
class Animal(var a: String) { //allowed here
    fun walk() {
        println(a)
    }
}
```

# [LOOP](https://pl.kotl.in/X330G78pm)
```kotlin
val items = listOf(1,3,8,5,4) //items = ArrayList<Int>(); items.add(1)
for (item in items) {
    println("log->loop1 $item")
}
for (index in items.indices) {
    println("log->loop2 item at $index : ${items[index]}")
}
for (index in 0 until items.size) {
    println("log->loop3 item at $index : ${items[index]}")
}
for (index in 6 downTo 0 step 2) {
    println("log->loop4 - range1 : $index") //6,4,2,0
}
for (index in 1..3) {
    println("log->loop5 - range2 : $index") //1,2,3
}
```

### issue in kotlin
i++ in for loop -> val cannot be reassigned [Solution](https://pl.kotl.in/crSb2A5oU)

```kotlin
var n = 5
for (i in 0 until n) {
    println("log->loop (for) $i/$n")
    i++ //todo comment out this to run
}

//use while loop instead
var i = 0
while (i <= n) {
    println("log->loop (while) $i/$n")
    i+=2
}

//do while loop -> factorial
var number = 6; var factorial = 1
do {
    factorial *= number
    number--
} while(number > 0)
println("Factorial of 6 is $factorial")
```

