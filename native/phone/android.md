## 1. Gọi một cuộc gọi
### Mở app gọi điện để gọi tới 1 số nhưng chưa gọi đi

```java
String number = "01656175880";
Uri call = Uri.parse("tel:" + number);
Intent surf = new Intent(Intent.ACTION_DIAL, call);
startActivity(surf);
```

### Mở app gọi điện và gọi điện đi

#### Request permission

```java
requestPermissions(new String[]{Manifest.permission.CALL_PHONE}, 123);
```

#### Gọi

```java
String number = "01656175880";
Uri call = Uri.parse("tel:" + number);
Intent surf = new Intent(Intent.ACTION_CALL, call);
startActivity(surf);
```

## 2. Lắng nghe trạng thái cuộc gọi đến
```java
	public enum PhoneState {
    none,
    ringing
}

public PhoneState phoneState = PhoneState.none;
private int prev_state;
private IntentFilter phoneFilter;
String incoming_number;

// Register
phoneFilter = new IntentFilter();
phoneFilter.addAction(TelephonyManager.ACTION_PHONE_STATE_CHANGED);
phoneFilter.addAction(Intent.ACTION_NEW_OUTGOING_CALL);
registerReceiver(mPhoneCallReceiver, phoneFilter);


	public class CustomPhoneStateListener extends PhoneStateListener {
    private static final String TAG = "PhoneStateListener";

    @Override
    public void onCallStateChanged(int state, String incomingNumber) {
        if (incomingNumber != null && incomingNumber.length() > 0)
            incoming_number = incomingNumber;

        switch (state) {
            case TelephonyManager.CALL_STATE_RINGING:
                Log.i(TAG, "onCallStateChanged: new call");
                if (phoneState == PhoneState.none) {
                    phoneState = PhoneState.ringing;
                }

                prev_state = state;
                break;

            case TelephonyManager.CALL_STATE_OFFHOOK:
                Log.i(TAG, "da nhac may");
                if (phoneState == PhoneState.ringing) {
                    phoneState = PhoneState.none;
                }

                prev_state = state;
                break;

            case TelephonyManager.CALL_STATE_IDLE:
                if ((prev_state == TelephonyManager.CALL_STATE_OFFHOOK)) {
                    prev_state = state;
                    //Answered Call which is ended
                    Log.i(TAG, "onCallStateChanged: End call");
                    if (phoneState == PhoneState.ringing) {
                        phoneState = PhoneState.none;
                    }
                }

                if ((prev_state == TelephonyManager.CALL_STATE_RINGING)) {
                    prev_state = state;
                    Log.i(TAG, "onCallStateChanged: " + "Rejected or Missed call");
                    if (phoneState == PhoneState.ringing) {
                        phoneState = PhoneState.none;
                    }
                }
                break;

        }
    }
}

private final BroadcastReceiver mPhoneCallReceiver = new BroadcastReceiver() {

    @Override
    public void onReceive(Context context, Intent intent) {
        Log.i(TAG, "onReceive: " + intent.getAction());
        if (!(intent.getAction().equals(Intent.ACTION_NEW_OUTGOING_CALL))) {
            TelephonyManager telephony = (TelephonyManager) context.getSystemService(Context.TELEPHONY_SERVICE); //TelephonyManager object
            CustomPhoneStateListener customPhoneListener = new CustomPhoneStateListener();
            telephony.listen(customPhoneListener, PhoneStateListener.LISTEN_CALL_STATE); //Register our listener with TelephonyManager
        }
    }
};

```
## 3. Lắng nghe trạng thái cuộc gọi đi