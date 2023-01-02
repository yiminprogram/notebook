# Object Animator

## MainActivity.java

```java
public class MainActivity extends AppCompatActivity
{
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        View focusView = findViewById(R.id.focus_view);

        focusView.setOnFocusChangeListener(new View.OnFocusChangeListener()
        {
            @Override
            public void onFocusChange(View view, boolean isFocus)
            {
                AnimatorSet animatorSet = new AnimatorSet();
                ObjectAnimator scaleX;
                ObjectAnimator scaleY;
                if (isFocus)
                {
                    scaleX = ObjectAnimator.ofFloat(focusView, "scaleX", 1f, 2f);
                    scaleY = ObjectAnimator.ofFloat(focusView, "scaleY", 1f, 2f);
                }
                else
                {
                    scaleX = ObjectAnimator.ofFloat(focusView, "scaleX", 2f, 1f);
                    scaleY = ObjectAnimator.ofFloat(focusView, "scaleY", 2f, 1f);
                }
                scaleX.setDuration(500);
                scaleY.setDuration(500);
                animatorSet.playTogether(scaleX, scaleY);
                animatorSet.start();
            }
        });
    }
}
```
