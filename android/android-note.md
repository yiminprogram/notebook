# Android

## RecyclerView

### 監聽滾動狀態

- `SCROLL_STATE_IDLE` RecyclerView 靜止，沒有正在進行的滾動操作
- `SCROLL_STATE_DRAGGING` 正在使用手指或滑鼠拖動 RecyclerView 進行滾動
- `SCROLL_STATE_SETTLING` 滾動操作已經結束，但 RecyclerView 仍在滾動並逐漸停止

```java
addOnScrollListener(new OnScrollListener() {
    @Override
    public void onScrollStateChanged(@NonNull RecyclerView recyclerView, int newState) {
        super.onScrollStateChanged(recyclerView, newState);
        // 判斷newState
    }
});
```

## Fragment
