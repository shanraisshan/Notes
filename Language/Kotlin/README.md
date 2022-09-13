# Kotlin

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

# [ARRAY](https://pl.kotl.in/GNA_9D8of)
```kotlin
//https://stackoverflow.com/q/73705958/4754141
//decalre + initialize
var a = arrayOf(1,2,3) 
var b = arrayOf<Int>(4,5,6)
var c = intArrayOf(7,8,9)

println(a) //[Ljava.lang.Integer;@5d099f62
println(b) //[Ljava.lang.Integer;@31cefde0
println(c) //[I@439f5b3d

//Array<Int> is an Integer[] (object) under the hood, while IntArray is an int[] (primitive)
//arr[1] or arr.get(1) both can be used
//arr[1]=2 or arr.set(1,2)

//IntArray example
val arrPrimitive: IntArray = IntArray(3) //declare only with size
//arrPrimitive[0]=1
arrPrimitive[1]=3
arrPrimitive.set(2,8)
for (i in 0 until arrPrimitive.size) {
    println("log->arrPrimitive " + arrPrimitive[i] + "|" + arrPrimitive.get(i))//[0, 3, 8]
}

//Array<Int> example
val arrInteger = Array(3) {0}
//arrInteger[0]=1
arrInteger[1]=3
arrInteger.set(2,8)
for (i in 0 until arrInteger.size) {
    println("log->arrInteger " + arrInteger[i] + "|" + arrInteger.get(i))//[0, 3, 8]
    }
```

# LIST | SET | MAP

https://www.geeksforgeeks.org/difference-between-list-set-and-map-in-java/

List|Set|Map
:-:|:-:|:-:
allow duplicate|does not|does not
maintains insertion order|does not|does not
set any number of null|1 null| 1 null key, any number of null values
implementation classes are Array List, LinkedList|HashSet, LinkedHashSet, TreeSet|HashMap, HashTable, TreeMap, ConcurrentHashMap, LinkedHashMap
provides get() method to get the element at a specified index|does not|does not

# LIST
```kotlin
//java.util;
//val arrayList = ArrayList<Int>() //extends AbstractList<E> implements List<E> (-> extends Collection<E> extends Iterable<E>)
//arrayList.add(1)
val arrayList = arrayListOf(1,3,8,5,4)
println("log->arrayList $arrayList") //[1, 3, 8, 5, 4]
```

# SET
```kotlin
//-> random insertion order
//package java.util;
//val hashSet = HashSet<Int>() //extends AbstractSet<E> implements Set<E> (-> extends Collection<E> extends Iterable<E>)
//hashSet.add(1)
val hashSet = hashSetOf(1,3,8,5,4)
println("log->hashSet $hashSet") //[8, 1, 3, 4, 5]
hashSet.remove(3)
hashSet += listOf(5, 9) //or use hashSetOf(5, 9)
println("log->hashSet $hashSet") //[8, 1, 9, 4, 5]

//-> maintain insertion order
//java.util;
//val linkedHashSet = LinkedHashSet<Int>() //extends HashSet<E> implements Set<E> (-> extends Collection<E> extends Iterable<E>)
//linkedHashSet.add(1)
val linkedHashSet = linkedSetOf(1,3,8,5,4) //not linkedHashSetOf(1,3,8,5,4)
println("log->linkedHashSet $linkedHashSet") //[1, 3, 8, 5, 4]
linkedHashSet.remove(3)
linkedHashSet += listOf(5, 9) //or use linkedSetOf(5, 9)
println("log->linkedHashSet $linkedHashSet") //[1, 8, 5, 4, 9]

//java.util
//val treeSet = TreeSet<Int>() //extends AbstractSet<E> implements NavigableSet<E> (-> extends SortedSet<E> extends Set<E> -> extends Collection<E> extends Iterable<E>)
//treeSet.add(1)
val treeSet = sortedSetOf(1,3,8,5,4) //not treeSetOf(1,3,8,5,4)
println("log->treeSet $treeSet") //[1, 3, 4, 5, 8]
```

# [MAP](https://pl.kotl.in/ANkK4gRcz)
```kotlin
//-> random insertion order
//kotlin.collections
//val hashMap = HashMap<String, Int>() //extends AbstractMap<K, V> implements Map<K, V>
//hashMap["key1"] = 1
//hashMap["key2"] = 3
val hashMap = hashMapOf("key1" to 1, "key2" to 3, "key3" to 8, "key4" to 5, "key5" to 4)
println("log->hashMap $hashMap") //{key1=1, key2=3, key5=4, key3=8, key4=5}

//-> maintain insertion order
//package java.util;
//val linkedHashMap = LinkedHashMap<String, Int>() //extends HashMap<K, V> implements Map<K, V>
val linkedHashMap = linkedMapOf("key1" to 1, "key2" to 3, "key3" to 8, "key4" to 5, "key5" to 4)
println("log->linkedHashMap $linkedHashMap") //{key1=1, key2=3, key3=8, key4=5, key5=4}

//package java.util;
//val treeMap = TreeMap<String, Int>() //extends AbstractMap<K, V> implements NavigableMap<K, V> (-> extends SortedMap<K, V> extends Map<K, V>)
//treeMap["key1"] = 1
val treeMap = sortedMapOf("key1" to 1, "key2" to 3, "key3" to 8, "key4" to 5, "key5" to 4)
println("log->treeMap $treeMap") //{key1=1, key2=3, key3=8, key4=5, key5=4}

//package com.google.gson.internal;
val linkedTreeMap = LinkedTreeMap<String, Int>() //extends AbstractMap<K, V> implements Serializable
linkedTreeMap["key1"] = 1
linkedTreeMap["key2"] = 3

//package com.google.gson.internal;
val linkedHashTreeMap = LinkedHashTreeMap<String, Int>() //extends AbstractMap<K, V> implements Serializable
linkedHashTreeMap["key1"] = 1
linkedHashTreeMap["key2"] = 3
```

## Operations on Map

### [Loop](https://pl.kotl.in/Xq1jDOQtO)
```
var map = hashMapOf(1 to 1, 2 to 2)   //trick -> 121
map.forEach { (key, value) -> 
    println("$key:$value") //1:1 2:2
}

map.forEach { entry ->
    println("${entry.key}:${entry.value}") //1:1 2:2
}

for (entry in map.entries.iterator()) {
    println("${entry.key}:${entry.value}") //1:1 2:2
}
```

# Of
```kotlin
arrayOf(1,2,3)
intArrayOf(1,2,3)
listOf(1,2,3)
arrayListOf(1,2,3)
setOf(1,2,3)
hashSetOf(1,2,3)
linkedSetOf(1,2,3)
mapOf(1,2,3)
hashMapOf(1,2,3)
linkedMapOf(1,2,3)
```

# HASHMAP | JSONOBJECT

HashMap|JsonObject
:-:|:-:
-|JSONObject is backed by a HashMap
{one=1, two=2}|{"one":1,"two":2}

```kotlin
val hashMap = HashMap<String, Int>()
hashMap.put("one",1)
hashMap.put("two",2)
hashMap.put("three",3)
println("log->hashMap $hashMap") //{one=1, two=2, three=3}

val jsonObject = JSONObject()
jsonObject.put("one",1)
jsonObject.put("two",2)
jsonObject.put("three",3)
println("log->jsonObject $jsonObject") //{"one":1,"two":2,"three":3}
```
