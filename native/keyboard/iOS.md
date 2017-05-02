##### 1. Sự kiện đóng & mở
##### 2. Đóng & mở & kiểm tra có đang mở hay không (Chưa viết)
##### 3. Scroll để hiện thị edittext bị che
##### 4. Tạo keyboard mới (Chưa viết)

=====================================================================================

##### 1. Sự kiện đóng & mở

``` swift
override func viewDidLoad() {
    super.viewDidLoad()
        
    NotificationCenter.default.addObserver(self, selector: #selector(self.didKeyboardShow(_:)), name: NSNotification.Name.UIKeyboardDidShow, object: nil)
    
    NotificationCenter.default.addObserver(self, selector: #selector(self.didKeyboardHide(_:)), name: NSNotification.Name.UIKeyboardDidHide, object: nil)
}

func didKeyboardShow(_ notification : Notification) {
    print ("show")
}

func didKeyboardHide(_ notification : Notification) {
    print ("hide")
}
```

##### 2. Đóng & mở & kiểm tra có đang mở hay không
###### Mở Không thể làm được
###### Đóng chỉ dùng được với TextField (Xem phần TextField)

###### Kiểm tra có đang mở hay không

##### 3. Scroll để hiện thị edittext bị che








