# BOTTOM SHEET DIALOG FRAGMENT

## EXPAND

> android 11 (TV) 有 bug 無法展開， android 12 (mobile) 正常

```java
@NonNull
@Override
public Dialog onCreateDialog( Bundle savedInstanceState )
{
      Dialog dialog = super.onCreateDialog( savedInstanceState );
      dialog.setOnShowListener( new DialogInterface.OnShowListener()
      {
          @Override
          public void onShow( DialogInterface dialogInterface )
          {
              View sheetView = dialog.findViewById( com.google.android.material.R.id.design_bottom_sheet );
              BottomSheetBehavior<View> behavior = BottomSheetBehavior.from( sheetView );
              behavior.setState( BottomSheetBehavior.STATE_EXPANDED );
              behavior.setSkipCollapsed( true );
          }
      } );
      dialog.getWindow().setBackgroundDrawable( new ColorDrawable( Color.BLUE ) );

      return dialog;
}
```
