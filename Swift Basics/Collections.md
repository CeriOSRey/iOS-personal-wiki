---
title: 'Array'
output: html_document
---

Array: Array<Element> - stores values of the same type in an ordered list. The same value can appear in an array multiple times at different positions/indexes.

Sets: Set<Element> stores distinct values of the same type with no defining order.

Dictionary: Dictionary<Key, Value> - stores associations between keys of the same type and values of the same type in a collection with no defined ordering.

Higher order functions: functions that operate on other functions

sorted: return a new array that is sorted in ascending order. Elements need to conform to Comparable protocol

````let numbers: [Int] = [0,1,4,7,3,5,6,2]
   let ascendingNumbers = numbers.sorted()
   print(numbers) // [0,1,2,3,4,5,6,7]
```

You can also shorten the syntax with this way:
`let ascendingNumbers = numbers.sorted(by: >)`

map: iterates and changes the elements based on the condition passed inside the closure
```let numbersAsStrings = numbers.map(transforms: (Int) throws -> T)
   let strings = numbers.map { String($0) }
   print(strings)
````

filter: return an array that has only the elements that passes the condition specified.

```let numbersAsString = numbers.filter(isIncluded: (Int) throws -> Bool)
   let numbersLessThanFive - numbers.filter { $0 < 5 }
```

reduce: combine all the elements in an array and return an object of any type (Generics),
initialResult or first parameter tells us where to start, nextPartialResult is the condition

```numbers.reduce(initialResult: Result, nextPartialResult: (Result, Int) throws -> Result)
   let sumOfAllNumbers = numbers.reduce("") { $0 + String($1) }
```
