# Android Leanback

## HorizontalGridView 或 VerticalGridView

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

### 設定 Focus 滾動位置

- `FOCUS_SCROLL_ALIGNED` Focus 固定中間
- `FOCUS_SCROLL_ITEM` Focus 不固定
- `FOCUS_SCROLL_PAGE` Focus 換頁

```java
setFocusScrollStrategy(option)
```

### 設定 Focus 對齊位置

- `WINDOW_ALIGN_BOTH_EDGE` 預設，Focus 對齊兩側邊緣
- `WINDOW_ALIGN_LOW_EDGE` Focus 對齊起始邊緣
- `WINDOW_ALIGN_HIGH_EDGE` Focus 對齊結束邊緣
- `WINDOW_ALIGN_NO_EDGE` 無對齊

```java
// 設定 Focus 固定於第一個
setWindowAlignment(BaseGridView.WINDOW_ALIGN_LOW_EDGE);
setWindowAlignmentOffset(0);
setWindowAlignmentOffsetPercent(0);
setItemAlignmentOffsetPercent(0);
```

### 常用設定

- `setRowHeight(ViewGroup.LayoutParams.WRAP_CONTENT)`  
  Horizontal 高度如果為 wrap_content 須額外設定高度，才能顯示正確的高度
- `setItemAlignmentOffset(0)`  
  Item Focus 如果超出螢幕會導致 Focus 位移，需設定避免位移
