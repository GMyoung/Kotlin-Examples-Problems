# Kotlin Examples Problems

The "src" folder contains the resolved exercises of "http://try.kotlinlang.org/#/Examples/Problems/Sum/Sum.kt".

These are the simple solutions of the kotlin example problems ON LINE. If you want to add your answer, you can make a PR.

##Indexes for examples problems online

###Problems
* [Sum](https://github.com/vicboma1/Kotlin-Examples-Problems#Sum)
* [Index of Maximum](https://github.com/vicboma1/Kotlin-Examples-Problems#index-of-maximum)
* [Runs](https://github.com/vicboma1/Kotlin-Examples-Problems#run)
* [Palindrome](https://github.com/vicboma1/Kotlin-Examples-Problems#palindrome)
* [Pairless](https://github.com/vicboma1/Kotlin-Examples-Problems#pairless)

# Problems

## Sum
```

Your task is to implement the sum() function so that it computes the sum of
all elements in the given array a.

```

Solution 1
```kotlin
fun sum(a: IntArray): Int {
 return a.filter { it != null }.sum()
}
```

Solution 2
```kotlin
fun sum(a: IntArray): Int {
  var _sum = 0
  for(element in a)
    _sum += element       
    
  return _sum
```

Solution 3
```kotlin
fun sum(a: IntArray): Int {
  val iterator = a.iterator()
  var _sum: Int = 0
  while (iterator.hasNext()){
    _sum += iterator.next()
  }
  
   return _sum
}
```

## Index of Maximum
```
Your task is to implement the indexOfMax() function so that it returns
the index of the largest element in the array, or null if the array is empty.
```

Solution
```kotlin
fun _indexOfMax(a: IntArray): Int? { 
        var maxIndex = 0
            for(elem in a.indices){
            val newElem = a[elem]
            if (newElem >= a[maxIndex]){
                 maxIndex = elem; 
            }
    	}
        return maxIndex
    }
    return  if(a.size != 0) _indexOfMax(a) else null
```

## Runs
```
 Any array may be viewed as a number of "runs" of equal numbers.
 For example, the following array has two runs:
  1, 1, 1, 2, 2
 Three 1's in a row form the first run, and two 2's form the second.
 This array has two runs of length one:
  3, 4
 And this one has five runs:
  1, 0, 1, 1, 1, 2, 0, 0, 0, 0, 0, 0, 0
 Your task is to implement the runs() function so that it returns the number
 of runs in the given array.
```

Solution
```kotlin
fun runs(a: IntArray): Int {
    // Write your solution here
    return 0
}
```

## Palindrome
```
 Your task is to implement a palindrome test.
 
 A string is called a palindrome when it reads the same way left-to-right
 and right-to-left.
```

Solution 1
```kotlin
fun isPalindrome(s: String): Boolean {
    return s == s.reversed()
}
```

Solution 2
```kotlin
fun isPalindrome(s: String): Boolean {
  var reversed = ""
  for(i in s.indices.reversed())
    reversed = "$reversed${s.charAt(i)}"

    return s == reversed  
}
```

Solution 3
```kotlin
fun isPalindrome(s: String): Boolean {
  val iterator = s.iterator()
  var _reversed = ""
  while(iterator.hasNext()){
      val _char = iterator.next()
      _reversed = "$_char$_reversed"
  }
    return s == _reversed
}
```

## Pairless
```

 Think of a perfect world where everybody has a soulmate.
 Now, the real world is imperfect: there is exactly one number in the array
 that does not have a pair. A pair is an element with the same value.
 For example in this array:
  1, 2, 1, 2
 every number has a pair, but in this one:
  1, 1, 1
 one of the ones is lonely.
 
 Your task is to implement the findPairless() function so that it finds the
 lonely number and returns it.
 
 A hint: there's a solution that looks at each element only once and uses no
 data structures like collections or trees.

```

Solution
```kotlin

INPUT 	OUTPUT
A 	B 	A XOR B
0 	0 	   0      OK
0 	1 	   1
1 	0 	   1
1 	1 	   0      OK


fun findPairless(a: IntArray): Int {
    return a.reduce { a, b -> a xor b }
}
```