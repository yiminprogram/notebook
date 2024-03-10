# IMAGE IN TEXTVIEW

## EXample

```java
private void setImageInText()
{
    if ( getContext() == null )
    {
        return;
    }
    int size = getResources().getDimensionPixelSize( R.dimen.key_up_icon );

    Drawable image = getContext().getDrawable( R.drawable.img_upbtn_n );
    image.setBounds( 0, 0, size, size );

    ImageSpan imageSpan = null;
    if ( android.os.Build.VERSION.SDK_INT >= android.os.Build.VERSION_CODES.Q )
    {
        imageSpan = new ImageSpan( image, ImageSpan.ALIGN_CENTER );
    }
    SpannableString spannableString = new SpannableString( " " );
    spannableString.setSpan( imageSpan, 0, spannableString.length(), Spanned.SPAN_EXCLUSIVE_EXCLUSIVE );

    mTextKeyUpHint.append( getString( R.string.Launcher_043 ) );
    mTextKeyUpHint.append( "  " );
    mTextKeyUpHint.append( spannableString );
    mTextKeyUpHint.append( "  " );
    mTextKeyUpHint.append( getString( R.string.Launcher_147 ) );
}
```
