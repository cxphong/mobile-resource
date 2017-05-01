##### 1. Sự kiện đóng & mở
##### 2. Đóng & mở & kiểm tra có đang mở hay không
##### 3. Scroll để hiện thị edittext bị che

=====================================================================================

##### 1. Sự kiện đóng & mở
Sử dụng thư viện https://github.com/AzimoLabs/AndroidKeyboardWatcher

Bước 1: Cài đặt 
```gradle
dependencies {
  compile 'com.azimolabs.keyboardwatcher:keyboardwatcher:0.1.3'
}
```
Bước 2: Thêm thuộc tính *adjustResize* cho Activity trong AndroidManifest.xml
```xml
<activity android:name=".test.TestActivity"
	      android:windowSoftInputMode="adjustResize">
```
Bước 3: Thêm event trong Activity

```java
public class TestActivity extends Activity implements KeyboardWatcher.OnKeyboardToggleListener {
    private static final String TAG = "TestActivity";
    private KeyboardWatcher keyboardWatcher;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.test_layout);
        
        // Register
        keyboardWatcher = new KeyboardWatcher(this);
        keyboardWatcher.setListener(this);
    }

    // Remember unregister
    @Override
    protected void onDestroy() {
        keyboardWatcher.destroy();
        super.onDestroy();
    }

    @Override
    public void onKeyboardShown(int keyboardSize) {
        Log.i(TAG, "onKeyboardShown: ");
    }

    @Override
    public void onKeyboardClosed() {
        Log.i(TAG, "onKeyboardClosed: ");
    }
}
```

##### 2. Đóng & mở & kiểm tra có đang mở hay không

Dùng file https://github.com/cxphong/Android-Utils/blob/master/KeyboardUtils.java

##### 3. Scroll để hiện thị edittext bị che

Bước 1: Thêm thuộc tính *adjustResize* cho Activity trong AndroidManifest.xml

```xml
<activity android:name=".test.TestActivity"
          android:windowSoftInputMode="adjustResize">
```

Bước 2: Đặt layout trong  *ScrollView*







