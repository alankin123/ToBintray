# ToBintray #

Android Studio上传到BinTray的gradle配置

----------
# 说明 #

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
