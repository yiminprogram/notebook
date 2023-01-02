# Fragment

## MyFragment.java

```java
public class MyFragment extends Fragment
{
    public View onCreateView(LayoutInflator inflator, ViewGroup container, Bundle savedInstanceState)
    {
        View rootView = inflator.inflate(R.layout.layout, container, false);
        return rootView;
    }
}
```

## MainActivity.java

```java
public class MainActivity extends AppCompatActivity
{
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState)
    {
        Fragment fragment = new MyFragment();
        FragmentManager manager = getSupportFragmentManager();
        FragmentTransaction transaction = manager.beginTransaction();
        transaction.add(R.layout.activity_main, fragment);
        // transaction.replace(R.layout.activity_main, fragment);
        transaction.commit();
    }
}
```
