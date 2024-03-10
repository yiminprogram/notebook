# LEANBACK TIMEPICKER

## Set To Use

- need set `setActivated( true )` to use

```java
timePicker.setActivated( true );
```

## Change Time List Item Style

- create `lb_picker_item.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<TextView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/time_list_item"
    android:focusable="true"
    android:textSize="16sp"
    android:textColor="@color/white"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_centerHorizontal="true"
    android:gravity="center" />
```
