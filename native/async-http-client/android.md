## 1. Install

```xml
	compile 'com.loopj.android:android-async-http:1.4.9'
```

Github https://github.com/loopj/android-async-http

## 2. Add permission INTERNET

## 3. Usage

#### 1. Download file

```java
final String url = "http://dl.fiot.vn/atmelRf.zip";
AsyncHttpClient client = new AsyncHttpClient();
client.get(url, new AsyncHttpResponseHandler() {
    @Override
    public void onSuccess(int statusCode, Header[] headers, byte[] responseBody) {
        FileUtils.saveBinaryToSDCard(responseBody, "data.zip");
    }

    @Override
    public void onFailure(int statusCode, Header[] headers, byte[] responseBody, Throwable error) {

    }

    @Override
    public void onProgress(long bytesWritten, long totalSize) {
        super.onProgress(bytesWritten, totalSize);
        Log.i(TAG, "onProgress: " + bytesWritten + "/" + totalSize);
    }
});
```