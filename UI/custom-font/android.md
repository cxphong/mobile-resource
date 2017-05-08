### Bước 1: 

Bỏ font vào thư mục assets

### Bước 2:

```java
TextView myTextView = (TextView) findViewById(R.id.textView);
Typeface typeface = Typeface.createFromAsset(getAssets(), "yourfont.ttf");
myTextView.setTypeface(typeface);
```
