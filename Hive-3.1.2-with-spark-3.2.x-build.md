## HIVE 3.1.2 源码编译支持Spark 3.x

#### 参考博客：https://blog.csdn.net/weixin_52918377/article/details/117123969
#### 参考项目；https://github.com/gitlbo/hive/tree/3.1.2

```shell
git clone -b 3.1.2 https://github.com/PyRSA/hive.git

cd hive

mvn clean package -Pdist -DskipTests -Dmaven.javadoc.skip=true
````

#### 此次编译组件版本选择
| 组件      | 版本     |
| --------- | -------- |
| hadoop    | 3.2.3    |
| spark     | 3.2.1    |
| hive      | 3.1.2    |
| zookeeper | 3.6.3    |
| hbase     | 2.3.6    |
| scala     | 2.12.15  |
| java      | 1.8      |
| maven     | 3.6.3    |
| snappy    | 1.1.8    |
| tez       | 0.10.0   |
| protobuf  | 2.5.0    |
| kryo      | 3.0.3    |
| guava     | 27.0-jre |



#### 编译命令： **`mvn clean package -Pdist -DskipTests -Dmaven.javadoc.skip=true`**

### 当出现以下错误时，根据提示在执行一次编译命令即可

编译命令：**`mvn clean package -Pdist -DskipTests -Dmaven.javadoc.skip=true -rf :hive-webhcat`**
```shell
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.6.1:compile (default-compile) on project hive-webhcat: Compilation failure
[ERROR] /opt/dev/apache-hive-3.1.2-src/hcatalog/webhcat/svr/src/main/java/org/apache/hive/hcatalog/templeton/Main.java:
[259,31] 对于FilterHolder(java.langlass<org.apache.hadoop.hdfs.web.AuthFilter>), 找不到合适的构造器
[ERROR]     构造器 org.eclipse.jetty.servlet.FilterHolder.FilterHolder(org.eclipse.jetty.servlet.BaseHolder.Source)不适用
[ERROR]       (参数不匹配; java.lang.Class<org.apache.hadoop.hdfs.web.AuthFilter>无法转换为org.eclipse.jetty.servlet.BaseHolder.Source)
[ERROR]     构造器 org.eclipse.jetty.servlet.FilterHolder.FilterHolder(java.lang.Class<? extends javax.servlet.Filter>)不适用
[ERROR]       (参数不匹配; java.lang.Class<org.apache.hadoop.hdfs.web.AuthFilter>无法转换为java.lang.Class<? extends javax.servlet.Filter>)
[ERROR]     构造器 org.eclipse.jetty.servlet.FilterHolder.FilterHolder(javax.servlet.Filter)不适用
[ERROR]       (参数不匹配; java.lang.Class<org.apache.hadoop.hdfs.web.AuthFilter>无法转换为javax.servlet.Filter)
```
