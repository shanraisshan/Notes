# Kotlin

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

# [LOOP](https://pl.kotl.in/lB3HSRU4v)
```kotlin
val items = listOf(1,3,8,5,4) //items = ArrayList<Int>(); items.add(1)
for (item in items) {
    println("log->loop1 $item")
}
for (index in items.indices) {
    println("log->loop2 item at $index is ${items[index]}")
}
for (index in 0 until items.size) {
    println("log->loop3 item at $index is ${items[index]}")
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
```

# [ARRAY](https://pl.kotl.in/DNMLuXzLz)
```kotlin
val array1 = arrayOf(1,3,8) //decalre + initialize
for (i in 0 until array1.size) {
    println("log->array1 " + array1[i])//[1, 3, 8]
}


val array2: IntArray = IntArray(3) //declare only with size
//array2[0]=1
array2[1]=3
array2[2]=8
for (i in 0 until array2.size) {
    println("log->array2 " + array2[i])//[0, 3, 8]
}

//Array<Int> is an Integer[] (object) under the hood, while IntArray is an int[] (primitive)

val array3 = Array(3) {0}
//array3[0]=1
array3[1]=3
array3[2]=8
for (i in 0 until array3.size) {
    println("log->array3 " + array3[i])//[0, 3, 8]
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

# MAP
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

# Of
```kotlin
listOf(1,2,3)
arrayListOf(1,2,3)
setOf(1,2,3)
hashSetOf(1,2,3)
linkedSetOf(1,2,3)
mapOf(1,2,3)
hashMapOf(1,2,3)
linkedMapOf(1,2,3)
```
