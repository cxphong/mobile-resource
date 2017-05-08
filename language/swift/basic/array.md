#### Initialize
```swift
var someInts = [Int](count: 3, repeatedValue: 0)

// Or
var someInts:[Int] = [10, 20, 30]
```

#### Access
```swift
var someVar = someInts[0]
```

#### Append
```swift
someInts.append(20)

// Or
someInts += [20]
```

#### Loop
```swift
for item in someInts {
   println(item)
}
```

#### Add 2 arrays
```swift
var intsC = intsA + intsB
```

#### Count
```swift
var intsA = [Int](count:2, repeatedValue: 2)
println("Total items in intsA = \(intsA.count)")
```

#### Empty
```swift
var intsC = [Int]()
```

