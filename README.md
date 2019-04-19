# rntemplate_files使用说明

### rn.gitignore文件
rn.gitignore是React Native项目的gitignore文件模板，是[gitignore](https://github.com/github/gitignore)项目中的[Objective-C.gitignore](https://github.com/github/gitignore/blob/master/Objective-C.gitignore)、[Swift.gitignore](https://github.com/github/gitignore/blob/master/Swift.gitignore)、[Android.gitignore](https://github.com/github/gitignore/blob/master/Android.gitignore)合并而成的。

### android_fastlane & ios_fastlane文件夹
这两个文件夹下是Fastlane的Fastfile脚本，用来实现自动打包Android apk和iOS ipa，并且自动上传到[fir.im](https://fir.im)。

因为分属于iOS和android两个项目，要分别进入两个目录执行打包命令，挺繁琐的。所以在为了简化操作，在【package.json】文件的`scripts`中加入自动打包命令：

```
 "scripts": {
    "package": "cd ./ios/fastlane && fastlane beta && cd ../../android/fastlane && fastlane beta"
  },
```

需要打包时，在`terminal`中执行`npm run package`即可完成iOS和Android打包工作。

