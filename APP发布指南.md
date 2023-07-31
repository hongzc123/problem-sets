# APP发布指南

## APP包发布

1. 切换为 `master` 分支
2. 合并 `test` 分支到 `master` 分支(注意冲突合并)
3. 打开 HbuildX 编辑器
4. 选择项目根目录下的 `manifest.json` 文件
5. 更改应用版本名称，大版本修改 `中间版本号`，如 `1.1.0` -> `1.2.0`
6. 递增应用版本号，如 `6` -> `7`
7. 选择顶部导航栏 `发行` -> `原生APP-云打包`
8. Android 情况下：
   1. 设置包名 `com.cmpanda.charmingpanda`
   2. 选择使用 `云端证书`
   3. 渠道包选择 `GooglePlay(AAB)`
   4. 打正式包
   5. 传统打包
9. IOS 情况下：
   1. Bundle ID `com.cmpanda.charmingpanda`
   2. 证书私钥密码 `cmpanda8888`
   3. profile和私钥都选择 `正式` 的文件
   4. 打正式包
   5. 传统打包
10. 打包成功后会返回下载链接，发送给春哥即可

## APP热更新

1. 1-4 步骤同 APP包发布
2. 更改应用版本名称，小版本修改 `补丁版本号`，如 `1.2.0` -> `1.2.1`
3. 递增应用版本号，如 `6` -> `7`
4. 选择顶部导航栏 `发行` -> `原生APP-制作应用wgt`
5. 构建结束后修改文件名为对应版本名，如 `1.2.1.wgt`
6. 放入对应的 OSS 地址中，比如 IOS 地址为：`oss://cmp-purchase-test/cmp/app_package/ios`
7. 放入 OSS 之后，点击 `OSS浏览器` 的获取地址，获取最终的链接
8. 将链接发送给后端即可

## H5更新

1. APP 更新必然伴随 H5 更新，版本号统一即可
2. 选择顶部导航栏 `发行` -> `网站- PC web或手机`
3. 进行打包构建，构建结束后命令行会显示对应的路径
4. 将路径文件放入 OSS 地址： `oss://cmp-purchase/cmp/front/cmp_h5/` 和 `oss://cmp-prod/cmp-front/cmp_h5/` 即可
