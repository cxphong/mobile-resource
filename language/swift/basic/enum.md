```swift
enum Climate {
   case India
   case America
   case Africa
   case Australia
}
```

```swift
// Specify value type
enum TemperatureUnit : Int {
    case Celsius = 0
    case Fahrenheit = 1
}
```

## Set value for enum variable
```swift
	var x : TemperatureUnit!

	x = TemperatureUnit.init(rawValue: 0)
```
https://www.weheartswift.com/tuples-enums/
https://appventure.me/2015/10/17/advanced-practical-enum-examples/