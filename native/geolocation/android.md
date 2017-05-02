Sử dụng file https://github.com/cxphong/Android-Utils/blob/master/GPSUtils.java

#### Bước 1: Khai báo permission trong AndroidManifest.xml & request permission

Chọn 1 trong 2 permission sau đây:

*ACCESS_COARSE_LOCATION* 

*ACCESS_FINE_LOCATION*

Trong đó *ACCESS_FINE_LOCATION* có độ chính xác cao hơn

#### Bước 2: Sử dụng file GPSUtils.java

##### Lấy giá trị location hiện tại

```java
GPSUtils.requestLocation(this, new GPSUtils.GPSUtilsListener() {
    @Override
    public void didGetGPS(Location location) {
        Log.i(TAG, "didGetGPS: " + location);
    }
});
```

##### Track giá trị location liên tục

###### Start

```java
GPSUtils.startWatchLocation(this, new GPSUtils.GPSUtilsListener() {
    @Override
    public void didGetGPS(Location location) {
        
    }
});
```

###### Stop

```java
GPSUtils.stopWatchLocation();
```



