#### Delay

```Swift
sleep(4) # delay 4s
```

```Swift
DispatchQueue.main.after(when: .now() + 10) { # delay 10s
	// Function
}
```

```Swift
self.perform(#selector(getBrightness), with: self, afterDelay: 2) # Delay 2s

func getBrightness() {
       
}
```

#### Timer

```Swift
// start
timer = Timer.scheduledTimer(timeInterval: 3.0, target: self, selector: #selector(self.getConnected), userInfo: nil, repeats: true)
```

```Swift
// stop
if (timer != nil) {
    timer.invalidate()
}
```

```Swift
// Multiple parameter in selector
timer = NSTimer.scheduledTimerWithTimeInterval(4, target: self, selector: Selector("showAlert2:"), userInfo: ["title":"a title", "message": "a message", "controller": controller], repeats: false)

func showAlert2(timer: NSTimer) {   
  let dict = timer.userInfo as NSDictionary

  showAlert(dict["title"] as String, wwithMessage: dict["message"] as String, fromController: dict["controller"] as UIViewController)
}

func showAlert(alertTitle: String, withMessage alertMessage: String, fromController controller: UIViewController) {
	//    do stuff...
}
```
