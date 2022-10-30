# create fragment

1. create fragment class

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

2. parent class

```java
Fragment fragment = new MyFragment();

FragmentManager manager = getSupportFragmentManager();

FragmentTransaction transaction = manager.beginTransaction();

transaction.add(R.layout.activity_main, fragment);

// transaction.replace(R.layout.activity_main, fragment);

transaction.commit();

```
