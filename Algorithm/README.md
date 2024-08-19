# Algorithm

# STRING
https://www.hackerrank.com/challenges/time-conversion/problem

# IMPLEMENTATION

1. LinkedList
2. HashMap
3. Stack
4. Singelton class
5. Custom class override equals and hashCode

# RECURSION

# SEARCH

# SORT
https://github.com/daolq3012/Kotlin-Algorithms

# LOGIC

1. Square Root
2. Power Of
3. Binary
4. Primary
5. Palindrome
6. Pyramid

### [Operators](https://pl.kotl.in/2-7E5Um6f)
```kotlin
var x=4
println("x++:" + x++)//4
var y=4
println("++y:" + ++y)//5
var z =4
z=z++
println("z:" + z)//4
```

### [Alphabets](https://pl.kotl.in/zcI7ztf2b)
```kotlin
for(i in 65 until 91) {
    println(i.toChar()) //A B C ... Z
}
for(i in 97 until 123) {
    println(i.toChar()) //a b c ... z
}
```

### [Swap 2 Strings](https://pl.kotl.in/WL1B6eBZi)
```kotlin
var a = "abc"
var b = "xyz"
a = a+b
b = a.substring(0, a.length-b.length)
a = a.substring(b.length)
println(a + "-" + b)
```

### [Reverse Int](https://pl.kotl.in/VI3t5j2e9)
```kotlin
fun reverseInt(_num: Int): Int {
    var reverse = 0
    var num = _num //var not allowed in function
    while (num != 0) {
        val digit = num % 10
        reverse = reverse * 10 + digit
        num = num/10
    }
    return reverse
}
```

### [Factorial](https://pl.kotl.in/wQATBU-j2)
```kotlin
//for (requires 3 variables)
var number = 5; var fact = 1
for(i in number downTo 1) {
    fact *= i
}
println("Factorial of $number is $fact")

//do-while (does not need 3rd variable)
var _number = 5; var _fact = 1
do {
    _fact *= _number
    _number--
} while(_number > 0)
println("Factorial of 5 is $_fact")
```

### Modulus Operator % [grading round-off problem](https://pl.kotl.in/E9BqWmJLJ)
```kotlin
 8 % 3 evaluates to 2 because 8 divided by 3 has a remainder of 2
```
