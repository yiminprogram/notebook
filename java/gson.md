# Gson

-   [Model 轉 Json](#model-轉-json)
-   [Json 轉 Model](#json-轉-model)
-   [List 轉 Json](#list-轉-json)
-   [Json 轉 List](#json-轉-list)

## Model 轉 Json

```java
Model model = new Model({
    "Apple",100,true
});
Gson gson = new Gson();
String json = gson.toJson(foodModel);
```

## Json 轉 Model

```java
String json = "{\"name\":\"Apple\",\"price\":\"100\",\"isStock\":true}";
Gson gson = new Gson();
Model model = gson.fromJson(json, Model.class);
```

## List 轉 Json

```java
List<Model> list = new ArrayList<>();
list.add(new Model("apple1",100));
list.add(new Model("apple2",200));
list.add(new Model("apple3",300));
Gson gson = new Gson();
String json = gson.toJson(list);
```

## Json 轉 List

### Array

```java
String json = "[{name:\"apple1\",price:100},{name:\"apple2\",price:200},{name:\"apple3\",price:300},]";
Gson gson = new Gson();
Model[] modelArray = gson.fromJson(json, Model[].class);
String name = modelArray[0].getName(); // apple1
int price = modelArray[0].getPrice(); // 100
```

### Array List

```java
String json = "[{name:\"apple1\",price:100},{name:\"apple2\",price:200},{name:\"apple3\",price:300},]";
Type modelType = new TypeToken<List<Model>>() {}.getType();
List<Model> modelList = new ArrayList<>(gson.fromJson(json, modelType));
String name = modelList.get(0).getName(); // apple1
int price = modelList.get(0).getPrice(); // 100
```
