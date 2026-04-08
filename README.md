# development-notes

> 开发笔记

### Maven 国内镜像仓库配置

```xml
<!--<repositories>-->
<!--    <repository>-->
<!--        <id>aliyun</id>-->
<!--        <url>https://maven.aliyun.com/repository/public</url>-->
<!--    </repository>-->
<!--</repositories>-->
<!--<pluginRepositories>-->
<!--    <pluginRepository>-->
<!--        <id>aliyun</id>-->
<!--        <url>https://maven.aliyun.com/repository/public</url>-->
<!--    </pluginRepository>-->
<!--</pluginRepositories>-->
<repositories>
    <repository>
        <id>tencent</id>
        <url>https://mirrors.cloud.tencent.com/nexus/repository/maven-public/</url>
    </repository>
</repositories>
<pluginRepositories>
    <pluginRepository>
        <id>tencent</id>
        <url>https://mirrors.cloud.tencent.com/nexus/repository/maven-public/</url>
    </pluginRepository>
</pluginRepositories>
```

### Gradle 国内下载地址

```properties
# distributionUrl=https\://services.gradle.org/distributions/gradle-9.4.1-bin.zip
# distributionUrl=https\://mirrors.aliyun.com/gradle/gradle-9.4.1-bin.zip
# distributionUrl=https\://mirrors.aliyun.com/macports/distfiles/gradle/gradle-9.4.1-bin.zip
distributionUrl=https\://mirrors.cloud.tencent.com/gradle/gradle-9.4.1-bin.zip
```

### Gradle 国内镜像仓库配置

```groovy
// maven { url 'https://maven.aliyun.com/repository/public/' }
maven { url 'https://mirrors.cloud.tencent.com/nexus/repository/maven-public/' }
```
