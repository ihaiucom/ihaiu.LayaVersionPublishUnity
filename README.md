# ihaiu.LayaVersionPublishUnity
发布laya应用版本工具,使用Unity5.4写的

# 发布App版本步骤
1. 生成 JS的Merge和Min
2. 拷贝 bin -> resouces/ios/web/
3. 修改 resouces/ios/web/index.html
4. layanative 命令， app构建 保存到 resouces/ios/build-app/app_v1.05.00
5. 将cache替换发包
6. layadcc 命令, 生成 resouces/web/update 版本信息
7. 拷贝 resouces/ios/web/update -> resouces/ios/build-update/app_v1.05.00/update

# 发布补丁版本步骤
1. 生成 JS的Merge和Min
2. 拷贝 bin -> resouces/web/
3. 修改 resouces/web/index.html
4. layadcc 命令, 生成 resouces/web/update 版本信息
5. 拷贝 resouces/ios/web/update -> resouces/ios/build-update/patch_v1.05.01/update
6. 拷贝 resouces/ios/web/update -> resouces/ios/version-patch/patch_v1.05.01/update
7. 对比 resouces/ios/build-update/patch_v1.05.01/update 和 resouces/ios/build-update/app_v1.05.00/update
8. 生成 补丁zip -> resouces/ios/version-patch/patch_v1.05.01/patch.zip


# 发布分包App版本步骤
*. 收集App 运行到 下载界面需要用到的资源 AppPackageRes.csv

1. 生成 JS的Merge和Min
2. 拷贝 bin -> resouces/ios/web/
3. 修改 resouces/ios/web/index.html
4. 将AppPackageRes.csv里的文件 拷贝到resouces/ios/web-app/
6. layanative 命令， app构建 保存到 resouces/ios/build-app/app_partial_v1.05.00
7. layadcc 命令, 生成 resouces/web/update 版本信息
8. 拷贝 resouces/ios/web/update -> resouces/ios/build-update/app_v1.05.00/update
9. 拷贝 resouces/ios/web/update -> resouces/ios/version-partial/partial_v1.05.00/update
10. 生成 分包zip -> resouces/ios/version-partial/partial_v1.05.00/partial.zip




# 修改 verinfo/DTGameVersion.json

