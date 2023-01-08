# Blur Mask Filter (Color)

## ColorBlurEdgeView.java

```java
public class ColorBlurEdgeView extends View
{
    private Paint mPain;
    private BlurMaskFilter mBlurMaskFilter;

    public ColorBlurEdgeView(Context context)
    {
        super(context);
        createView(context);
    }

    public ColorBlurEdgeView(Context context, @Nullable AttributeSet attrs)
    {
        super(context, attrs);
        createView(context);
    }

    public ColorBlurEdgeView(Context context, @Nullable AttributeSet attrs, int defStyleAttr)
    {
        super(context, attrs, defStyleAttr);
        createView(context);
    }

    public ColorBlurEdgeView(Context context, @Nullable AttributeSet attrs, int defStyleAttr, int defStyleRes)
    {
        super(context, attrs, defStyleAttr, defStyleRes);
        createView(context);
    }

    private void createView(Context context)
    {
        mPain = new Paint();
        mBlurMaskFilter = new BlurMaskFilter(radius, BlurMaskFilter.Blur.NORMAL);
    }

    @Override
    public void draw(Canvas canvas)
    {
        super.draw(canvas);
        mPain.setColor(Color.RED);
        mPain.setMaskFilter(mBlurMaskFilter);
        canvas.drawRect(startX, startY, endX, endY, mPain);
    }
}
```
