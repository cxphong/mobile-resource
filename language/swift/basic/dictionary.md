#### Initialize
```swift
var someDict = [Int: String]()
var someDict:[Int:String] = [1:"One", 2:"Two", 3:"Three"]
```

#### Access
```swift
var someDict:[Int:String] = [1:"One", 2:"Two", 3:"Three"]
var someVar = someDict[1] // [key]
```

#### Modify
```swift
var someDict:[Int:String] = [1:"One", 2:"Two", 3:"Three"]
var oldVal = someDict.updateValue("New value of one", forKey: 1)

// Or
someDict[1] = "New value of one"
```

#### Remove
```swift
someDict.removeValueForKey(2)
```

#### Iterating
```swift
for (key, value) in someDict {
   println("Dictionary key \(key) -  Dictionary value \(value)")
}
```

#### Convert to array
```swift
let dictKeys = [Int](someDict.keys)
let dictValues = [String](someDict.values)
```
#### Count
```swift
someDict.count
```

#### Empty
```swift
var someDict3:[Int:String] = [Int:String]()
```







