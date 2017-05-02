##### 1. Sự kiện đóng & mở
##### 2. Đóng & mở & kiểm tra có đang mở hay không
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

###### Đóng chỉ dùng được với TextField

Đóng khi nhấn return

Kết nối event *Did end on exit* 

```
@IBAction func endEdit(_ sender: Any) {

}

```

Đóng khi nhấn outside

###### Kiểm tra có đóng mở hay không

##### 3. Scroll để hiện thị edittext bị che

Bước 1: Thêm thuộc tính *adjustResize* cho Activity trong AndroidManifest.xml

```xml
<activity android:name=".test.TestActivity"
          android:windowSoftInputMode="adjustResize">
```

Bước 2: Đặt layout trong  *ScrollView*







