# BintrayPush
a fast library for push your code to Bintray by config your  information in local.properties

###如何使用

在项目中的local.properties中根据自己的实际情况配置好下面信息

```java
// 你在bintray网站上注册的用户名
bintray.user = xxx
// 你的apikey
bintray.apikey = xxx
//bintray 网站上仓库的名字
bintrayRepo = maven
//在这个仓库下的项目名字
bintrayName = xxx

//publishedGroupId:artifact:libraryVersion 构成你开源库的唯一路径
publishedGroupId = com.jankin.projectName
artifact = library
libraryVersion = 1.0.0
// 上面就构成了开源库路径 com.jankin.projectName:library:1.0.0

// 这是在bintray网站上对你的开源库的描述
libraryName = projectName
libraryDescription = xxx
siteUrl = https://xxx
gitUrl = https://xxx.git

//开发者信息
developerId = xxx
developerName = xxx
developerEmail = xxx
```

在你要上传的library项目的build.gradle中引入如下：

```java
apply from: 'https://github.com/wang0826jj/BintrayPush/bintray-config.gralde'
```

然后依次执行

`gradlew install`

`gradlew  bintrayUpload`

就把你的library上传到bintray网站上了。