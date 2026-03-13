# development-notes

## 测试二级标题 1

> 测试文字

### 测试三级标题 2

```xml
<repositories>
    <repository>
        <id>aliyun</id>
        <url>https://maven.aliyun.com/repository/public</url>
    </repository>
</repositories>
<pluginRepositories>
    <pluginRepository>
        <id>aliyun</id>
        <url>https://maven.aliyun.com/repository/public</url>
    </pluginRepository>
</pluginRepositories>
```

### 测试三级标题 3

```java
public static <O> List<O> subtract(List<O> a, List<O> b, BiPredicate<O, O> equals) {
    List<? extends EqualsWrapper<O>> aw = EqualsUtils.toEqualsWrapper(a, equals);
    List<? extends EqualsWrapper<O>> bw = EqualsUtils.toEqualsWrapper(b, equals);
    Collection<EqualsWrapper<O>> subtract = CollectionUtils.subtract(aw, bw);
    return EqualsUtils.toObject(subtract);
}
```
