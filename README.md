# development-notes

> 开发笔记

### 阿里云 Maven 仓库配置

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

### Gradle 下载地址

```properties
distributionUrl=https\://services.gradle.org/distributions/gradle-9.4.1-bin.zip
# distributionUrl=https\://mirrors.aliyun.com/gradle/gradle-9.4.1-bin.zip
# distributionUrl=https\://mirrors.aliyun.com/macports/distfiles/gradle/gradle-9.4.1-bin.zip
# distributionUrl=https\://mirrors.cloud.tencent.com/gradle/gradle-9.4.1-bin.zip
```
