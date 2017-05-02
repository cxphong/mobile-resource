#### 1. Download font-awesome tại http://fontawesome.io/#modal-download

#### 2. Copy file fontawesome-webfont.ttf trong folder mới download về vào thư mục app/src/main/assets/

Nếu chưa có folder *asesets* thì phải tự tạo lấy

#### 3. Trong file layout tạo 1 TextView

##### Hình ảnh dùng thuộc tính *android:text*
```xml
android:text="@string/font_awesome_android_icon"
```

```xml
<string name="font_awesome_android_icon">&#xf17b;</string>
```

http://fontawesome.io/icon/android/ có mã unicode là f17b
do đó cấu hình trong strings.xml có dạng ">&#x{unicode};

##### Kích thước dùng thuộc tính *android:textSize*
```xml
android:textSize="50sp"
```
##### Màu sắc dùng thuộc tính *android:textColor*
```xml
android:textColor="#00ff1e"
```

#### 4. Cấu hình font awesome bằng code java

```java
Typeface fontAwesomeFont = Typeface.createFromAsset(getAssets(), "fontawesome-webfont.ttf");
TextView fontAwesomeAndroidIcon = (TextView) findViewById(R.id.font_awesome_android_icon);
fontAwesomeAndroidIcon.setTypeface(fontAwesomeFont);
```