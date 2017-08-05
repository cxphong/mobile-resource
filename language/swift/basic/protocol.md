### Seperate class

```swift

// Class protocol
import UIKit

public protocol FlexibleHeightBarProtocol : class {
    func didScrollUp()
    func didScrollDown()
}


// declare
var delegate: FlexibleHeightBarProtocol?


// using
class FindDeviceViewController: ConnectedViewController, FlexibleHeightBarProtocol {
	
	// ...
	bar.delegate = self

	// ...

	func didScrollUp() {

	}

    func didScrollDown() {

    }

}

```

### Same class
```swift
	protocol FoundDeviceButtonProtocol : class {
	    func didClickCelsius();
	    func didClickFahrenheit();
	}

	class FoundDevice: UIView {
	}
```

### Pass Delegate to child

Child viewcontroller khai báo hàm ovveride, và hàm parrent sẽ không được gọi