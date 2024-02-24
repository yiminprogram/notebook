# BLUR IMAGE

## CLASS

- Bitmap
- RenderScript
- Allocation
- ScriptIntrinsicBlur

## EXAMPLE

```java
public class BitmapBlurBuilder
{
    private static final float SCALE = 0.2f;
    private static final float RADIUS = 15f;

    public static void setImageFromUrl( String url , ImageView imageView ) {
        new Thread( new Runnable() {
            @Override
            public void run() {
                try {
                    Bitmap bitmap = Glide.with( imageView.getContext() ).asBitmap().load( url ).submit().get();
                    Handler handler = new Handler( Looper.getMainLooper() );
                    handler.post( new Runnable() {
                        @Override
                        public void run() {
                            Glide.with( imageView.getContext() ).load( createOutputBitmap( bitmap ) ).into( imageView );
                        }
                    } );
                }
                catch ( Exception e ) {
                    e.printStackTrace();
                }
            }
        } ).start();
    }

    public static Bitmap blur( int drawable ) {
        Application context = AirialTvAtscApplication.getInstance();
        Bitmap bitmap = BitmapFactory.decodeResource( context.getResources(), drawable );

        return createOutputBitmap( bitmap );
    }

    public static Bitmap createOutputBitmap( Bitmap bitmap ) {
        Application context = Application.getInstance();

        int width = Math.round( bitmap.getWidth() * SCALE );
        int height = Math.round( bitmap.getHeight() * SCALE );

        Bitmap inputBitmap = Bitmap.createScaledBitmap( bitmap, width, height, false );
        Bitmap outputBitmap = Bitmap.createBitmap( inputBitmap );

        RenderScript renderScript = RenderScript.create( context );

        Allocation allocationInput = Allocation.createFromBitmap( renderScript, inputBitmap );
        Allocation allocationOutput = Allocation.createFromBitmap( renderScript, outputBitmap );

        ScriptIntrinsicBlur scriptIntrinsic = ScriptIntrinsicBlur.create( renderScript, Element.U8_4( renderScript ) );
        scriptIntrinsic.setRadius( RADIUS );
        scriptIntrinsic.setInput( allocationInput );
        scriptIntrinsic.forEach( allocationOutput );
        allocationOutput.copyTo( outputBitmap );

        return outputBitmap;
    }
}
```
