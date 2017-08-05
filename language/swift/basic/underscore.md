### Function: khi gọi thì ko cần có label

```swift
func myFunc(label name: Int) // call it like myFunc(label: 3)
func myFunc(_ name: Int) // call it like myFunc(3)
```

### For Loop: Index ko được dùng, có thể bỏ qua

```swift
for _ in 1...20 { 
    print ("Hello")
}
```


### Giá trị trả về của 1 hàm ko được dùng đến

```swift
	let _ = func()
```