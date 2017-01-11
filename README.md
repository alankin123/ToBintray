# ToBintray #

Android Studio上传到BinTray的gradle配置

# 说明 #

# 使用步骤 #
1.将AS中把依赖代码提取成一个依赖工程（module），然后把application module依赖于这个module，在依赖module的build.gradle文件中添加如下预定义变量。这些变量就是以后我们上传到bintray上时的参数。
 
    ext {
    bintrayRepo = 'maven'//仓库名称
    bintrayName = 'mypicker'//工程名称（仓库里面新建的包名）
    publishedGroupId = 'com.idisfkj.picker'//一般是自己的包名
    libraryName = 'MyPicker'//工程名称
    artifact = 'mypicker'//工程名称
    libraryDescription = 'A pickerView on Android'//工程的一些说明
    siteUrl = 'https://github.com/idisfkj/idisfkj.picker'//工程在github的上的url
    gitUrl = 'https://github.com/idisfkj/idisfkj.picker.git'//工程在github的上的克隆url
    libraryVersion = '1.2.1'//定义工程的版本号
    developerId = 'idisfkj'//开发者ID
    developerName = 'idisfkj'//开发者名称
    developerEmail = 'idisfkj@qq.com'//开发者邮箱
    licenseName = 'The Apache Software License, Version 2.0'//证书名称，不用改
    licenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0.txt'//证书地址，不用改
    allLicenses = ["Apache-2.0"]//证书类型，不用改
    }

2.修改好以上参数后，继续再后面继续引入两个gradle文件

https://github.com/alankin123/ToBintray/blob/master/install.gradle

https://github.com/alankin123/ToBintray/blob/master/bintray.gradle

3.找到工程根目录下的local.properties文件，添加你的账号和apikey，注意一定要将这个文件忽略上传，防止隐私信息泄漏。

4.在Terminal窗口运行输入gradlew install运行，成功后继续输入gradlew bintrayUpload运行，
成功后则说明已经上传到bintray上了

5.进入到你的bintray账户，选中你的仓库的包，选择linkToJcenter,绑定到Jcenter上，大概半个小时后你的项目则被上传到Jcenter上了

