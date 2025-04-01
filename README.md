# elsfs-parent

#### 介绍
java 代码依赖pom

#### 软件架构
软件架构说明


#### 安装教程
```xml
 <parent>
    <groupId>org.elsfs.parent</groupId>
    <artifactId>elsfs-parent</artifactId>
    <version>parent.version</version>
    <relativePath/>
  </parent>
```
#### 使用说明

1.  本仓库只提供pom依赖
2.  本仓库不定期更新依赖并发布新的版本到maven中央仓库
3.  该储存库发布到maven中央仓库的只有pom.xml,并使用  **gpg -a  --detach-sign  elsfs-parent-版本号.pom** 生成签名

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request
