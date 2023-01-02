# Custom TV RecyclerView Vertical

## MySmoothLinearScroller.java

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
        return (boxStart + (boxEnd - boxStart) / 2) - (viewStart + (viewEnd - viewStart) / 2);
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

## VerticalRecyclerView.java

```java
public class VerticalRecyclerView extends RecyclerView
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
        MyLinearLayoutManager myLinearLayoutManager = new MyLinearLayoutManager(context, LinearLayoutManager.VERTICAL, false);
        setLayoutManager(myLinearLayoutManager);
    }

    @Override
    public View focusSearch(View focused, int direction)
    {
        int position = getChildAdapterPosition(focused);
        int targetPosition = position;
        if (position == FOCUS_DOWN)
        {
            targetPosition = position + 1;
        }
        else if (position == FOCUS_UP)
        {
            targetPosition = position - 1;
        }
        ViewHolder viewHolder = findViewHolderForAdapterPosition(targetPosition);
        if (viewHolder != null)
        {
            smoothScrollToPosition(position + 1);
        }
        else
        {
            return focused;
        }
        return super.focusSearch(focused, direction);
    }
}
```
