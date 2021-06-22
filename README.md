# HP PRODESK 400G2 DM黑苹果 EFI

## 我的配置

|         硬件       |                   型号                  |
|-------------------:|:----------------------------------------|
|               主板 | HP PRODESK 400G2 DM                       |
|                CPU | Intel Core i5-6600T                  |
|               显卡 | Intel HD Graphics 530 1536 MB   |
|              硬盘1 | 西数 SN750 500G M2 NVMe        |
|              硬盘2 | 东芝 Q200EX 240G SATA     |
|               内存1 | Crucial DDR4 2666Mhz 8G |
|               内存2 | Crucial DDR4 2666Mhz 8G |
|        无线 + 蓝牙 | BCM94360CS2 |
|               键盘 | 罗技 K375s                          |
|               鼠标 | 罗技 MX Anywhere 2S                  |
|            显示器 | Philips 221E 21.5-inch (1920 x 1080) |


## 折腾日志

2021年2月9日：升级WhateverGreen，根据官方文档，删除Clover配置文件中不必要的配置

2021年1月21日：重新修改声卡驱动，使麦克风真正可用，尝试自己定制USB

2021年12月8日：根据AppleALC官方文档，删除Clover配置文件中不必要的配置

2020年12月5日：Clover升级到5123.1，替换无线网卡为BCM94360CS2，尝试为AppleALC增加专用的layout-id，使麦克风可以用起来

2020年11月6日：Clover升级到5122版，并升级驱动到最新版

2020年10月29日：修改机型为iMac17,1，安装DW1820A无线网卡，发现5G连接一会就掉速到7Mbps，后来证实为5G频道问题，更换频道后OK

2020年10月17日：使用ylen0l的EFI文件安装Catalina 10.15.7，后替换为老白完美4K后的配置文件

## 更新注意事项

更新 EFI 之后，第一次进系统最好是带 `-v` 参数启动，否则可能会出现禁止符号，无法启动。如果出现这种情况下，再次启动时，加上 `-v` 参数就可以了。进入系统之后，最好使用 `Hackintool` 重建一下驱动缓存。


## EFI 简介

根据老白的视频，找到了ylen0l的github项目地址，在此基础上将Clover及驱动更新了一下，并定制了声卡驱动，使麦克风可用。


这个 EFI 的特点是使用的是 `iMac17,1` 机型，双硬解正常，因已做了 USB 定制，所有 USB 接口都可用。

未解决：

1、睡眠问题

2、VGA接口不可用



Clover 版本为：5123.1。

Clover 驱动包含：

* ApfsDriverLoader.efi
* AudioDxe.efi
* CsmVideoDxe.efi
* DataHubDxe.efi
* FSInject.efi
* HFSPlus.efi
* OcQuirks.efi
* OpenRuntime.efi

系统驱动包含：

* Lilu.kext
* AppleALC.kext
* WhateverGreen.kext
* HibernationFixup.kext
* RTCMemoryFixup.kext
* RealtekRTL8111.kext
* USBPorts.kext
* VirtualSMC.kext
* SMCProcessor.kext
* SMCSuperIO.kext
## EFI 使用

如果你的配置跟我上面配置相同或兼容，那么你可以直接使用该 EFI 进行安装。安装前请注意，一定要用 `Clover Configurator` 重新生成并替换 `SMBIOS` 部分的内容，否则会因为机器有同一个硬件 ID 而被苹果封锁。生成时，请选择 `iMac17,1` 机型。


## 系统截图
懒得截图了
