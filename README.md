# TWRP Device Tree 生成工具
## 这个工具怎么用？
- 1.首先你要搞到你的设备任意一个可以开机系统的
  - `boot.img` (AB 分区)
  - `recovery.img` (除了 AB 分区以外的所有分区)

-----

- 2.将这个仓库 fork 到你的用户名下

-----

- 3.将 `recovery.img` 或 `boot.img` 上传至一个可以提供直链下载的位置，这里我推荐直接将 img 文件上传至这个仓库，然后点进去点 "view raw"，来获取直链

-----

- 4.点击 "actions － make twrp device － run workflow"，然后在那个链接框里面输入你刚刚获取的直链

-----

 - 5、填写完成后点击 "Run workflow" 开始运行

## 编译结果
- 可以在 [Release](../../releases) 下载

## 注意事项
- 1.如果安卓版本低于 9.0 ，需要手动解包 `recovery.img` 并在 `defxx.prop` 内添加  
`ro.product.first_api_level=23` (安卓api版本号，如安卓6.0是23)  

-----

- 2.如果你的设备是 oppo ，且出现了 `AssertionError: Property ro.product.system.device could not be found in build.prop`  
需要将 `ramdisk` 里面的 `etc/recovery.fstab` 复制到 `system/etc/recovery.fstab`  
`system/build.prop` 和 `vendor/build.prop` 的内容一起合并到 `/prop.default` 然后打包生成
