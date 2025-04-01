# 软件环境
- deepin 23
- maven 3.8.4

# 申请账号
# 配置maven
远程仓库配置完成后，打开maven的setting.xml
```xml
    <server>
      <id>ossrh</id>
      <username>sonatype账号</username>
      <password>sonatype密码</password>
      <!--创建秘钥的时候输入的密码。可选-->
      <passphrase>gpg密码</passphrase>
    </server>
```
# pom.xml配置
```xml
  <profiles>
    <profile>
      <id>ossrh</id>
      <build>
        <plugins>
          <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-gpg-plugin</artifactId>
            <version>3.1.0</version>
            <executions>
              <execution>
                <id>sign-artifacts</id>
                <phase>verify</phase>
                <goals>
                  <goal>sign</goal>
                </goals>
              </execution>
            </executions>
          </plugin>
          <plugin>
            <groupId>org.sonatype.plugins</groupId>
            <artifactId>nexus-staging-maven-plugin</artifactId>
            <version>1.6.13</version>
            <extensions>true</extensions>
            <configuration>
              <serverId>ossrh</serverId>
              <nexusUrl>https://s01.oss.sonatype.org/</nexusUrl>
              <autoReleaseAfterClose>true</autoReleaseAfterClose>
            </configuration>
          </plugin>
        </plugins>
      </build>
    </profile>
  </profiles>
```
# 运行 发布
```shell
mvn clean deploy -P ossrh
```