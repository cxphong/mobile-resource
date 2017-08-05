## Return mulitple value

```Swift
func getHourAndMinute() -> (hour: Int, minute: Int) {
	return (3, 4)
}

let ret = getHourAndMinute()
print ("hour = \(ret.hour), minute = \(ret.minute)")
```