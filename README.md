# ToBintray #

Android Studio上传到BinTray的gradle配置

# 说明 #

# 使用步骤 #
1.在工程根目录下的build.gradle添加这两个插件：  
classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.2'  
classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3 
 
2.将AS中把依赖代码提取成一个依赖工程（module），然后把application module依赖于这个module，在依赖module的build.gradle文件中添加如下预定义变量。这些变量就是以后我们上传到bintray上时的参数。
     
    ext {
    bintrayRepo = 'mylibrary'//bintray仓库名称
    bintrayName = 'mylibrary'//bintray仓库中新建包名称
    publishedGroupId = 'com.alankin.mylibrary'//自定义引用分组ID（一般为包名）
    artifact = 'mylibrary'//自定义引用名称
    libraryVersion = '0.0.2'//版本说明
    libraryName = 'mylibrary'//库名字
    libraryDescription = 'A mylibrary on Android'//库说明
    siteUrl = 'https://github.com/alankin123/MyLearn'//github地址
    gitUrl = 'https://github.com/alankin123/MyLearn.git'//github克隆地址
    developerId = ''//开发者ID
    developerName = 'alankin'//开发者名称
    developerEmail = '460682402@qq.com'//开发者邮箱
    licenseName = 'The Apache Software License, Version 2.0'//证书名称
    licenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0.txt'//证书路径
    allLicenses = ["Apache-2.0"]//证书类型
    }  
3.修改好以上参数后，继续再后面继续添加上这两个gradle脚本

apply from: 'https://github.com/alankin123/ToBintray/blob/master/install.gradle'  
apply from: 'https://github.com/alankin123/ToBintray/blob/master/bintray.gradle'

4.找到工程根目录下的local.properties文件，添加你的账号和apikey
如：  
bintray.user=lalala   
bintray.apikey=0423fe77c268cf65aa5054g465bc4dera326c627  
注意一定要将这个文件忽略上传，防止隐私信息泄漏。

5.在Terminal窗口运行输入gradlew install运行，成功后继续输入gradlew bintrayUpload运行，
成功后则说明已经上传到bintray上了

6.进入到你的bintray账户，选中你的仓库的包，选择linkToJcenter,绑定到Jcenter上，大概半个小时后你的项目则被上传到Jcenter上了

