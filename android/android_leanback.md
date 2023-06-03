# Android Leanback

## 使用 HorizontalGridView 或 VerticalGridView

1. 新增 ViewHolder

```java
class MyViewHolder extends Presenter.ViewHolder{
  TextView mTextView;

  public MyViewHolder(View view) {
    super(view);

    mTextView = view.findViewById(R.id.text);
  }
}
```

2. 新增 Presenter

```java
class MyPresenter extends Presenter {

  @Override
  public ViewHolder onCreateViewHolder(ViewGroup parent) {
    View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.layout, parent, false);
    return new ViewHolder(view);
  }

  @Override
  public void onBindViewHolder(ViewHolder viewHolder, Object item) {

  }

  @Override
  public void onUnbindViewHolder(ViewHolder viewHolder) {

  }
}
```

3. 新增 Adapter

```java
ArrayObjectAdapter arrayObjectAdapter = new ArrayObjectAdapter(new MyPresenter());
ItemBridgeAdapter itemBridgeAdapter = new ItemBridgeAdapter(arrayObjectAdapter);
setAdapter(itemBridgeAdapter);
```

4. 常用設定

- `setRowHeight(ViewGroup.LayoutParams.WRAP_CONTENT)` Horizontal 高度如果為 wrap_content 須額外設定高度，才能顯示正確的高度
