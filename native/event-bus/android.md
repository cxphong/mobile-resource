## 1. Giới thiệu 

EventBus là thư viện giao tiếp giữa các Activity, Fragment, Service, Thread, ...
thay thế cho BroadCastReceiver của Android. 

Ưu điểm là có thể pass các object thay vì primitive data type của BroadcastReceiver.

## 2. Cài đặt

*https://github.com/greenrobot/EventBus*

```xml
compile 'org.greenrobot:eventbus:3.0.0'
```

## 3. Cách sử dụng

### Tạo 1 MessageEvent tuỳ ý

```java
public class MessageEvent {
    public final String message;

    public MessageEvent(String message) {
        this.message = message;
    }
}
```

### Lăng nghe MessageEvent

```java

/* Tên hàm tuỳ ý, chỉ kiểm tra input parameter 
 * Ví dụ: Hàm này chỉ lắng nghe MessageEvent
 */
@Subscribe
public void onMessageEvent(MessageEvent event){
    userStatus.setText("User Status : Logged in, message: " + event.message);
}

/* Lưu ý nới register & unegister */
@Override
public void onStart() {
    super.onStart();
    EventBus.getDefault().register(this); // registering the bus
}

@Override
public void onStop() {
    EventBus.getDefault().unregister(this); // un-registering the bus
    super.onStop();
}
```

## 4. Cao cấp hơn: Thread

http://greenrobot.org/eventbus/documentation/delivery-threads-threadmode/
