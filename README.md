# Lytro-illum(B5151501240)

## 👉 软件下载

Lytro-Desktop[下载](http://lightfield-forum.com/lytro/lytro-archive/#downloads)、Lytro-Power-Tool[官网下载](http://lightfield-forum.com/lytro/lytro-archive/lytro-platform-lytro-power-tools-lytro-development-kit-official-product-information/)或[gitHub下载](https://github.com/kmader/lytro-power-tools)

## 🤕 说明

Lytro相机厂商已倒闭，可参考文献较少，本文档重点说明相机光场文件**解码软件的使用**和**脚本控制相机拍照**

## 📖 解码软件的使用

+ 完成Lytro-Power-Tool安装
+ 直接从相机导入SD卡的标定文件可能会在使用中报"Using bitmap demod, but no demod calibration data found (did you specify a calibration folder?)"的错误，此时需将相机通过USB-B线连接电脑，然后通过Lytro-Desktop工具导出标定文件。标定文件已上传至[百度网盘](https://pan.baidu.com/s/1Yz47oSIrQyRWAsL7LSYpdg?pwd=1234)
+ 使用$ lfptool raw -i [raw-path] --calibration-in [cal-path]即可完成光场lfr源文件的[解码](https://blog.csdn.net/ChandelerGause/article/details/114176962)，具体指令可参考上传的lfp指令手册或原光场相机说明书
+ 也可以使用matlab(具体参考[vincentqin](https://vincentqin.tech/posts/LightField-Toolbox/)进行解码，但色彩上不及lytro-power-tool的解码效果，同时无法直接生成深度图

## 🎅 **脚本控制相机拍照**

+ 完成Lytro-Power-Tool安装
+ 重启illum相机的过程中按住AEL和Lytro-button(半按压)，使相机进入开发者模式
+ illum相机的OS为Android，故需下载ADB(安卓调试桥)来使得电脑可进行操纵相机，Win10环境中下载后需为ADB配置环境变量
+ 在ABD窗口模式下输入adb devices查看设备，若出现"B5151501240 device"则说明连接成功，在终端完成测试连接后需执行adb kill-server以防止5037端口继续被占用。在Lytro-Power-Tool环境下运行$ cameratool captures --pictures 3，相机屏幕出现start字样，点击start即可执行脚本拍照

## 🌈 其他

Lytro-Desktop软件可在Windows环境下方便的观察已可视化的光场图像，并支持手动调节图像深度，曝光等信息。它可以导出相机中的标定文件，但使用前同样需要导入相机中的标定文件

