# Basic

# [var - val - const val](https://pl.kotl.in/EAwQARgk2)

var|val|const val
:-:|:-:|:-:
variable|value|constant
recomended for variables|-|string or any primitive data type
run-time|run-time|compile-time
mutable|[read-only, not truly immutable](https://stackoverflow.com/a/70486344/4754141), [example2](https://stackoverflow.com/a/63055134/4754141)|immutable
can be defined local + global|local or global|global
var a = func()|val a = func()|const val a = func() //Error
-|final|static final

```kotlin
const val c=1
val d=2 //can also be defined globally
var e=3 //can also be defined globally

//const val f3 = func(1) //Const 'val' initializer should be a constant value

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

    println("global var " + d)
    println("global val " + e)
    
    var f1 = func(50)
	println("func var " + f1) //51
    
    val f2 = func(100)
    println("func val " + f2) //101
}

fun func(a: Int): Int {
	return a+1    
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

# Object Orient Programming

# INHERITANCE
```kotlin
open class A {
    fun add(x: Int): Int {
        return x
    }
}

open class B:A() {
    //method overloading in inherited class
    fun add(x: Int, y: Int): Int {
        return x+y
    }
}
```

# ABSTRACT CLASS
```kotlin
abstract class C:B() {
	abstract fun add(x: Int, y: Int, z: Int): Int 
}

class D:C() {
    override fun add(x: Int, y: Int, z: Int): Int { //'add' hides member of supertype 'C' and needs an 'override' modifier.
        return x+y+z
    }
}
```

# STATIC CLASS 

### Static inner class (nested class)
```java
class A {
    static class B {
    ...
    }
}

class A {
    class B {
    ...
    }
}
```

### Static methods in java (Companion Object equivalent in Kotlin)
```java
class Foo {
  public static int a() { return 1; }
}

//equivalent in kotlin
class Foo {
  companion object {
     fun a() : Int = 1
  }
}

Foo.a();
```

# SEALED vs FINAL CLASS

### Kotlin
By default, Kotlin classes are final: they can't be inherited. To make a class inheritable, it has to be marked with the open keyword.

```java
sealed class Error(val message: String) {
    class NetworkError : Error("Network failure")
    class DatabaseError : Error("Database cannot be reached")
    class UnknownError : Error("An unknown error has occurred")
}
```

### Difference in java
- A sealed class is a class that can only be extended by a specific set of classes or interfaces, providing a more controlled form of inheritance.
- A final class is a class that cannot be extended at all, ensuring its implementation remains unchanged by subclasses.

