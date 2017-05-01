###### Close/Show event
######


###### Close/Show event

Sử dụng thư viện https://github.com/AzimoLabs/AndroidKeyboardWatcher

Bước 1: Cài đặt 

```gradle
dependencies {
  compile 'com.azimolabs.keyboardwatcher:keyboardwatcher:0.1.3'
}
```

Bước 2: Thêm thuộc tính cho Activity trong AndroidManifest.xml

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
        keyboardWatcher = new KeyboardWatcher(this);
        keyboardWatcher.setListener(this);
    }

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
		 
