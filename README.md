# Asus-S4100VN8250U-Hackintosh

华硕灵耀 Asus S4100V (具体型号S4100VN8250U)笔记本驱动. 本项目分享适用于本机黑苹果的可用efi文件
本机mojave正式版使用下来稳定, 流畅. 
如果有解决了不完美的方法, 请在issue告诉我.

## 本机硬件:
CPU: intel i5-8250U
主板: Asus X411UN Series Notebook
内存: 8GB板载
网卡/蓝牙：Qualcomm Atheros QCA9377 (原始网卡无解,可以加USB WIFI或更换网卡芯片)
显卡：集显INTEL UHD620, 独显nVIDIA GeForce MX150
声卡: Conexant SmartAudio HD/英特尔(R) 显示器音频 (windows下查到的)
硬盘: 1. M.2 128G 闪迪 SSD; 2. SATA 500GB hdd (黑苹果驱动与硬盘容量牌子关系不大)

## 哪些可以用？
 CPU变频(大约10级变频)
 显卡硬件加速(QE/CI)
 睡眠和唤醒
 音频正常, 插耳机自动切换,麦克风正常
 HDMI输出
 USB3.0 USB2.0
 自带的摄像头
 蓝牙可用,wifi不能(可更换wifi芯片为dw1560)
 电量显示正常(与windows版显示的电量相差3%左右)
 触控板可用（无法媲美白苹果体验）
 右侧自带的SD读卡器正常
 Fn快捷键(部分, FN亮度调节不可用. 不过可修改亮度快捷键为非FN的. 可以参考[此处](https://github.com/stonexing/Asus-S4000VA8550-Hackintosh)解决FN亮度快捷键问题)

## 哪些不能用？
独显nVIDIA GeForce MX150(已禁用独显-- SSDT-Disable-DGPU.aml文件, 该文件是从其它人那里复制过来的)
自带的WIFI芯片不能用(附随的蓝牙可用. 可以买usb的wifi, 或者更换为dw1560(即是BCM94352Z))

## 不完美的地方:
不是60hz(实际使用没感觉不同).  系统报告 --> 硬件--> intel UHD Graphics 620：---> UI 看起来类似：1920 x 1080 @ 57 Hz