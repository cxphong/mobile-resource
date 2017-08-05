Optional means has value or no value

#### Initialize variable
```swift
var s:String? # Must unwap to read value
var s:String! # unwrap is automatically, due to it means it always has value
```

#### unwrap optional, only unwrap if it not nil, only can check to nil if it is optional
```swift
var s:String?
s = "Hello, Swift!"

if s != nil {
   println( s! )
} else { 
   println("s has nil value")
}
```

### optional binding without check nil
```swift
var s:String?

s = "Hello, Swift!"

if let yourString = s {
   println("Your string has - \(yourString)")
}else {
   println("Your string does not have a value")
}
```

### Return from fuction

```swift
class func getTemperatureUnit() -> AnyObject? {
  return  UserDefaults.standard.object(forKey: TEMPERATURE_UNIT) as? AnyObject
}
```

