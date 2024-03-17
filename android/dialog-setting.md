# DIALOG SETTING

## THEME SETTING

```xml
<style name="DialogStyle" parent="Theme.AppCompat.Dialog">
        <item name="windowNoTitle">true</item>
        <item name="android:windowFullscreen">true</item>
        <item name="android:windowIsFloating">false</item>
        <item name="android:backgroundDimEnabled">false</item>
</style>
```

`backgroundDimEnabled` set background shadow

## SET STYLE

```java
setStyle( STYLE_NO_TITLE, R.style.DialogStyle );
```

## SET WIDTH WRAP CONTENT

```java
public Dialog onCreateDialog() {
    getDialog().getWindow().setBackgroundDrawable( new ColorDrawable( Color.TRANSPARENT ) );
    getDialog().getWindow().getAttributes().windowAnimations = R.style.DialogFragmentEndAnimation;
    getDialog().getWindow().setLayout( ViewGroup.LayoutParams.WRAP_CONTENT, ViewGroup.LayoutParams.MATCH_PARENT );
    getDialog().getWindow().setGravity( Gravity.END );
}
```

## SLIDE ANIMATION

### SLIDE IN END

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="350"
        android:fromXDelta="100%"
        android:toXDelta="0%" />
</set>
```

### SLIDE IN START

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="350"
        android:fromXDelta="100%"
        android:toXDelta="0%" />
</set>
```

### SLIDE IN START

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="350"
        android:fromXDelta="-100%"
        android:toXDelta="0%" />
</set>
```

### SLIDE IN BOTTOM

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="350"
        android:fromYDelta="100%"
        android:toYDelta="0%" />
</set>
```

### SLIDE OUT BOTTOM

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="350"
        android:fromYDelta="0%"
        android:toYDelta="100%" />
</set>
```

### SLIDE OUT END

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="350"
        android:fromXDelta="0%"
        android:toXDelta="100%" />
</set>
```

### SLIDE IN START

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="350"
        android:fromXDelta="0%"
        android:toXDelta="-100%" />
</set>
```
