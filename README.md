# AndroidBootAutoStartApp
Simple example to auto start a process once your system one using broadcast.



**Add this to your manifest

```
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />
<uses-permission android:name="android.permission.WAKE_LOCK" />

<receiver
        android:name="com.pm.herem.BroadcastReceiverOnBootComplete"
        android:enabled="true"
        android:exported="false">
        <intent-filter>
            <action android:name="android.intent.action.BOOT_COMPLETED" />
            <action android:name="android.intent.action.QUICKBOOT_POWERON" />
        </intent-filter>
        <intent-filter>
            <action android:name="android.intent.action.PACKAGE_REPLACED" />
            <data android:scheme="package" />
         </intent-filter>
         <intent-filter>
            <action android:name="android.intent.action.PACKAGE_ADDED" />
            <data android:scheme="package" />
         </intent-filter>
 </receiver>

 <service android:name="com.pm.herem.AndroidServiceStartOnBoot" />
 ```
