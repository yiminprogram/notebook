# Custom TV RecyclerView Horizontal

## MyLinearSmoothScroller.java

```java
public class MyLinearSmoothScroller extends LinearSmoothScroller
{
    public MyLinearSmoothScroller(Context context)
    {
        super(context);
    }

    @Override
    public int calculateDtToFit(int viewStart, int viewEnd, int boxStart, int boxEnd, int snapPreference)
    {
        return boxStart - viewStart;
    }

    @Override
    protected float calculateSpeedPerPixel(DisplayMetrics displayMetrics)
    {
        return 50f / displayMetrics.densityDpi;
    }
}
```

## MyLinearLayoutManager.java

```java
public class MyLinearLayoutManager extends LinearLayoutManager
{
    public MyLinearLayoutManager(Context context)
    {
        super(context);
    }

    public MyLinearLayoutManager(Context context, int orientation, boolean reverseLayout)
    {
        super(context, orientation, reverseLayout);
    }

    public MyLinearLayoutManager(Context context, AttributeSet attrs, int defStyleAttr, int defStyleRes)
    {
        super(context, attrs, defStyleAttr, defStyleRes);
    }

    @Override
    public void smoothScrollToPosition(RecyclerView recyclerView, RecyclerView.State state, int position)
    {
        HorizontalRecyclerView.MyLinearSmoothScroller myLinearSmoothScroller = new HorizontalRecyclerView.MyLinearSmoothScroller(recyclerView.getContext());
        myLinearSmoothScroller.setTargetPosition(position);
        startSmoothScroll(myLinearSmoothScroller);
    }
}
```

## HorizontalRecyclerView.java

```java
public class HorizontalRecyclerView extends RecyclerView
{
    public HorizontalRecyclerView(@NonNull Context context)
    {
        super(context);
        createView(context);
    }

    public HorizontalRecyclerView(@NonNull Context context, @Nullable AttributeSet attrs)
    {
        super(context, attrs);
        createView(context);
    }

    public HorizontalRecyclerView(@NonNull Context context, @Nullable AttributeSet attrs, int defStyleAttr)
    {
        super(context, attrs, defStyleAttr);
        createView(context);
    }

    private void createView(Context context)
    {
        MyLinearLayoutManager myLinearLayoutManager = new MyLinearLayoutManager(context, LinearLayoutManager.HORIZONTAL, false);
        setLayoutManager(myLinearLayoutManager);
    }
}
```
