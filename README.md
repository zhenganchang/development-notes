# development-notes

> 开发笔记

### Maven Wrapper 腾讯镜像地址

```properties
distributionUrl=https://mirrors.cloud.tencent.com/apache/maven/maven-3/3.9.15/binaries/apache-maven-3.9.15-bin.zip
```

### Maven 腾讯镜像仓库配置

```xml
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

### Gradle Wrapper 腾讯镜像地址

```properties
distributionUrl=https\://mirrors.cloud.tencent.com/gradle/gradle-9.4.1-bin.zip
```

### Gradle 腾讯镜像仓库配置

```groovy
maven { url 'https://mirrors.cloud.tencent.com/nexus/repository/maven-public/' }
```

### Gradle Spring-Boot 添加依赖

```groovy
dependencies {
    implementation 'commons-codec:commons-codec'
    implementation 'org.apache.commons:commons-lang3'
    implementation('com.github.ben-manes.caffeine:caffeine') {
        exclude group: 'com.google.errorprone', module: 'error_prone_annotations'
    }
    developmentOnly 'io.netty:netty-all'
}
```

### 本地开发环境部署 `compose.yaml`

```yaml
name: development

services:

  development-mysql:
    image: mysql:latest
    container_name: development-mysql
    hostname: development-mysql
    restart: unless-stopped
    environment:
      - MYSQL_ALLOW_EMPTY_PASSWORD=yes
    ports:
      - '3306:3306'
    volumes:
      - 'mysql_data:/var/lib/mysql'

  development-redis:
    image: redis:latest
    container_name: development-redis
    hostname: development-redis
    restart: unless-stopped
    ports:
      - '6379:6379'
    volumes:
      - 'redis_data:/data'

  development-rabbitmq:
    image: rabbitmq:management
    container_name: development-rabbitmq
    hostname: development-rabbitmq
    restart: unless-stopped
    ports:
      - "5672:5672"
      - "15672:15672"
    volumes:
      - "rabbitmq_data:/var/lib/rabbitmq"

  development-zookeeper:
    image: zookeeper:latest
    container_name: development-zookeeper
    hostname: development-zookeeper
    restart: unless-stopped
    ports:
      - '2181:2181'
    volumes:
      - 'zookeeper_data:/data'
      - 'zookeeper_datalog:/datalog'
      - 'zookeeper_logs:/logs'

volumes:
  mysql_data:
    name: development.mysql.data
    driver: local
  redis_data:
    name: development.redis.data
    driver: local
  rabbitmq_data:
    name: development.rabbitmq.data
    driver: local
  zookeeper_data:
    name: development.zookeeper.data
    driver: local
  zookeeper_datalog:
    name: development.zookeeper.datalog
    driver: local
  zookeeper_logs:
    name: development.zookeeper.logs
    driver: local
```

