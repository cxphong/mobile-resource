### Bước 1: 

Right click *app* -> *New* -> *Vector Asset* -> *Local file (SVG, PSD)*

Tạo file <<vector>>.xml từ file .svg

### Bước 2: Dùng file mới tạo trong imageview

```xml
ic_why.xml là file vector được tạo ra ở trên
<ImageView
    android:layout_width="100dp"
    android:layout_height="100dp"
    android:layout_marginBottom="16dp"
    android:src="@drawable/ic_why"/>
```