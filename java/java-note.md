# Java

## LocalDateTime

現在時間

```java
LocalDateTime now = LocalDateTime.now();
```

當日午夜零點

```java
LocalDateTime midnight = now.with(LocalTime.MIDNIGHT);
```

增加或減少 LocalDateTime

- `now.minusMinutes(1)`減少一分鐘
- `now.plusMinutes(1)`增加一分鐘

LocalDateTime 類別是不可變的，會返回一個新的 LocalDateTime 實例，所以需要累加必須額外儲存前一次狀態

```java
for (int i = 0; i < 48; i++) {
  LocalDateTime localDateTime = midnight.plusMinutes(i * 30);
}
```

## DateTimeFormatter

```java
DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("yyyy-MM-dd hh:mm:ss", Locale.getDefault());
LocalDateTime now = LocalDateTime.now();
System.out.println(now.format(dateTimeFormatter)); // 2023-06-11 05:50:50
```

### 比較 SimpleDateFormat 和 DateTimeFormatter

SimpleDateFormat

- 舊版 Java API 中用於日期時間格式化的類別
- 非線程安全的，不適合在多執行緒環境中使用
- 在處理時間區域設定（Locale）時可能有一些限制

DateTimeFormatter

- Java 8 新增的日期時間 API
- 線程安全的，適合在多執行緒環境中使用。
- 提供了更多的日期時間格式化選項，例如使用預先定義的模式（例如：ISO_LOCAL_DATE_TIME、ISO_OFFSET_DATE_TIME 等等）或自定義模式。
- 支援本地化和國際化，可以根據不同的地區和語言進行格式化和解析。
- 具有更好的效能，相對於 SimpleDateFormat，DateTimeFormatter 的效能更好。

### 日期 Pattern

| pattern    | example      |
| ---------- | ------------ |
| yyyy/MM/dd | 2023/01/01   |
| hh:mm:ss a | 12:00:00 PM  |
| HH:mm:ss   | 18:00:00     |
| MM/dd,E    | 01/01,Sun    |
| MM/dd,EEEE | 01/01,Sunday |
