#### Initialize
```swift
var s = "123";
var s : String = "123";
var s = String()
```

#### Check empty
```swift
// Empty string creation using String literal
var stringA = ""

if stringA.isEmpty {
   println( "stringA is empty" )
}else {
   println( "stringA is not empty" )
}

// Empty string creation using String instance
let stringB = String()

if stringB.isEmpty {
   println( "stringB is empty" )
} else {
   println( "stringB is not empty" )
}
```

#### Concat
```swift
// stringA can be modified
var stringA = "Hello, Swift!"
stringA + = "--Readers--"
println( stringA )

// stringB can not be modified
let stringB = String("Hello, Swift!")
stringB + = "--Readers--"
println( stringB )
```

##### Iterpolation 
````swift
var varA   = 20
let constA = 100
var varC:Float = 20.0

var stringA = "\(varA) times \(constA) is equal to \(varC * 100)"
println( stringA )
```

#### Concatentation
```swift
let constA = "Hello,"
let constB = "World!"

var stringA = constA + constB

println( stringA )
```

#### length
```swift
var varA   = "Hello, Swift!"

println( "\(varA), length is \(count(varA))" )
```

#### Comparation
```swift
if varA == varB {
	
} else {
	
}
```