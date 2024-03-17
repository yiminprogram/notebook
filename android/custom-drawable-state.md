# CUSTOM DRAWABLE STATE

## CREATE att.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <declare-styleable name="epg">
        <attr name="state_epg_channel_selected" format="boolean"/>
    </declare-styleable>
</resources>
```

## JAVA SETTING

```java
private static final int[] STATE_CHANNEL_SELECTED = {R.attr.state_epg_channel_selected};
@Override
    protected int[] onCreateDrawableState( int extraSpace )
    {
        int[] drawableState;
        if ( mIsChannelSelected )
        {
            drawableState = super.onCreateDrawableState( extraSpace + 1 );
            mergeDrawableStates( drawableState, STATE_CHANNEL_SELECTED );
        }
        else
        {
            drawableState = super.onCreateDrawableState( extraSpace );
        }
        return drawableState;
    }
```

## SET SELECTOR

```xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto">
    <item app:state_epg_channel_selected="true" android:drawable="@color/channel_selected_bg"/>
    <item android:drawable="@color/channel_bg"/>
</selector>
```
