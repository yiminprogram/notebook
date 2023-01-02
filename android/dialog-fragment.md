# Dialog Fragment

## MyDialogFragment.java

```java
public class MyDialogFragment extends DialogFragment
{
    public static final String MY_DIALOG_FRAGMENT = "MY_DIALOG_FRAGMENT";
    private MyDialogFragmentListener mListener;
    // layout
    private Button mButton;

    public interface MyDialogFragmentListener
    {
        void DoSomething();
    }

    public MyDialogFragment(MyDialogFragmentListener listener)
    {
        this.mListener = listener;
    }

    @Override
    public void onCreate(@Nullable Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setStyle(STYLE_NO_TITLE, R.style.MyDialogFragmentStyle);
    }

    @Nullable
    @Override
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState)
    {
        View rootView = inflater.inflate(R.layout.layout, container, false);

        mButton = rootView.findViewById(R.id.btn);
        mButton.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View view)
            {
                mListener.DoSomething();
            }
        });

        if (getDialog() != null)
        {
            getDialog().getWindow().setBackgroundDrawable(new ColorDrawable(Color.TRANSPARENT));
        }
        return rootView;
    }
}
```

## theme.xml

```xml
<style name="MyDialogFragmentStyle" parent="Theme.AppCompat.Dialog">
    <item name="windowNoTitle">true</item>
    <item name="android:windowFullscreen">true</item>
    <item name="android:windowIsFloating">false</item>
</style>
```

## MainActivity.java

```java
public class MainActivity extends AppCompatActivity implements MyDialogFragment.MyDialogFragmentListener
{
    private MyDialogFragment mMyDialogFragment;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mMyDialogFragment = new MyDialogFragment(this);
        mMyDialogFragment.show(getSupportFragmentManager(), MyDialogFragment.MY_DIALOG_FRAGMENT);
    }

    @Override
    public void DoSomething()
    {
       // TODO Something
    }
}
```
