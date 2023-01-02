# Custom Clock

## ClockView.java

```java
public class ClockView extends View
{
    // layout
    private TextView mTextDate;
    private TextView mTextTime;
    // handler
    private Handler mUiHandler;

    public ClockView(Context context)
    {
        super(context);
        createView(context);
    }

    public ClockView(Context context, @Nullable AttributeSet attrs)
    {
        super(context, attrs);
        createView(context);
    }

    public ClockView(Context context, @Nullable AttributeSet attrs, int defStyleAttr)
    {
        super(context, attrs, defStyleAttr);
        createView(context);
    }

    public ClockView(Context context, @Nullable AttributeSet attrs, int defStyleAttr, int defStyleRes)
    {
        super(context, attrs, defStyleAttr, defStyleRes);
        createView(context);
    }

    private void createView(Context context)
    {
        inflate(context, R.layout.layout_clock, this);

        mTextDate = findViewById(R.id.text_date);
        mTextTime = findViewById(R.id.text_time);

        startTime();
    }

    private void startTime()
    {
        mUiHandler = new Handler(Looper.getMainLooper());
        mUiHandler.post(new Runnable()
        {
            @Override
            public void run()
            {
                updateTime();
                mUiHandler.postDelayed(this, 60 * 1000);
            }
        });
    }

    private void updateTime()
    {
        SimpleDateFormat dateFormat = new SimpleDateFormat("yyyy-MM-dd", Locale.getDefault());
        SimpleDateFormat timeFormat = new SimpleDateFormat("HH:mm:ss", Locale.getDefault());

        Date date = Calendar.getInstance().getTime();
        String dateString = dateFormat.format(date);
        String timeString = timeFormat.format(date);

        mTextDate.setText(dateString);
        mTextTime.setText(timeString);
    }
}
```
