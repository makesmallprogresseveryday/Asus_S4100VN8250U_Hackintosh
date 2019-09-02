# Asus-S4100VN8250U-Hackintosh

华硕灵耀 Asus S4100V (具体型号S4100VN8250U)笔记本驱动. 本项目分享适用于本机黑苹果的可用efi文件. 本机mojave正式版使用下来稳定, 流畅. 

如果有解决了不完美的方法, 请在issue告诉我.

## 本机硬件:
CPU: intel i5-8250U

主板: Asus X411UN Series Notebook (BIOS版本302)

内存: 8GB板载

网卡/蓝牙：Qualcomm Atheros QCA9377 (原始网卡无解,可以加USB WIFI或更换网卡芯片)

显卡：集显INTEL UHD620, 独显nVIDIA GeForce MX150

声卡: Conexant CX8050

硬盘: 1. M.2 128G 闪迪 SSD; 2. SATA 500GB hdd (黑苹果驱动与硬盘容量牌子关系不大)

## 哪些可以用？
 CPU变频(大约10级变频)

 显卡硬件加速(QE/CI)

 睡眠和唤醒

 音频正常, 插耳机自动切换,麦克风正常 (若麦克风不能用,复制CodecCommander.kext到"/Library/Extensions"目录下并重建缓存)

 HDMI输出

 USB3.0 USB2.0

 自带的摄像头

 蓝牙可用,wifi不能(可更换wifi芯片)

 电量显示正常(与windows版显示的电量相差3%左右)

 触控板可用（无法媲美白苹果体验）

 右侧自带的SD读卡器正常

 Fn快捷键(部分, FN亮度调节不可用. 不过可修改亮度快捷键为非FN的. 可以参考[此处](https://github.com/stonexing/Asus-S4000VA8550-Hackintosh)解决FN亮度快捷键问题)

## 哪些不能用？
一、独显nVIDIA GeForce MX150(已禁用独显-- SSDT-Disable-DGPU.aml文件, 该文件是从其它人那里复制过来的)

二、自带的WIFI芯片不能用，附随的芯片的蓝牙免驱可用（但这张卡默认没有关闭蓝牙选项）. 

网卡解决办法3选1：

1.可以买usb支持mac的wifi（不拆机方法，本机拆机很容易）。

2.（便宜）更换为DW1820A网卡（即是BCM94350ZAE）。dw1820A的“天线位置”与原装网卡“天线位置”一样，相关驱动教程请看 [黑果小兵](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html) 。注意：《dw1820A有很多版本，目前不是每个版本都能完美驱动》（我上某宝买了0VW3T3芯片型号BCM94350ZAE可以完美使用，有专门卖DW1820A这个版本的店铺，我买的是某双王冠有运费险店铺（黑果小兵也有测试好的网卡闲鱼出售）），如果使用DW1820A需要按照黑果小兵教程里用透明胶屏蔽5个针脚才能正常使用。

3.（贵，本机要另外买天线布局）如果换为dw1560网卡(即是BCM94352Z)需要另外买一条内置天线，因为自带天线不够长（dw1560与自带网卡的天线位置不同），驱动也参考 [黑果小兵](https://blog.daliansky.net/Broadcom-BCM94352z-DW1560-drive-new-posture.html) 。

## 不完美的地方:
不是60hz(实际使用没感觉不同).  系统报告 --> 硬件--> intel UHD Graphics 620：---> UI 看起来类似：1920 x 1080 @ 57 Hz
