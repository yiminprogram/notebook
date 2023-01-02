# Get Device Install App

## PackageReveiver.java

```java
public class PackageReceiver extends BroadcastReceiver
{
    @Override
    public void onReceive(Context context, Intent intent)
    {
        String action = intent.getAction();
        switch (action)
        {
            case Intent.ACTION_PACKAGE_ADDED:
                // TODO Package Added
                break;
            case Intent.ACTION_PACKAGE_REMOVED:
                // TODO Package Removed
                break;
            case Intent.ACTION_BOOT_COMPLETED:
                // TODO Boot Completed
                break;

        }
    }
}
```

## AndroidManifest.xml

```xml
<receiver android:name=".PackageReceiver" android:exported="true">
  <intent-filter>
    <action android:name="android.intent.action.PACKAGE_ADDED"/>
    <action android:name="android.intent.action.PACKAGE_REMOVED"/>
    <action android:name="android.intent.action.BOOT_COMPLETED"/>
    <data android:scheme="package"/>
    </intent-filter>
</receiver>
```

## MainActivity.java

```java
public class MainActivity extends AppCompatActivity
{
    private PackageReceiver mPackageReceiver;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        IntentFilter filter = new IntentFilter();
        filter.addAction(Intent.ACTION_PACKAGE_ADDED);
        filter.addAction(Intent.ACTION_PACKAGE_REMOVED);
        filter.addAction(Intent.ACTION_BOOT_COMPLETED);
        filter.addDataScheme("package");
        mPackageReceiver = new PackageReceiver();
        registerReceiver(mPackageReceiver, filter);
    }

    @Override
    protected void onDestroy()
    {
        super.onDestroy();
        unregisterReceiver(mPackageReceiver);
    }
}
```
