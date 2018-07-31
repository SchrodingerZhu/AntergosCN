# 创建Live USB


---
![USB][1]
## 误区警示
一些`USB`烧写工具会改变`ISO`映像里包含的分区标签，**这会导致引导失败**。有解决方法可以来修复这个问题，但是这超出了本文的范围. 为获得最佳结果, 我们建议**不要**使用这些类型的实用工具来创建您的 `Live USB`。其中一些属于这类实用程序的熟知的有:

 - UNetbootin
 - Linux Live USB Creator
 - Universal USB Installer
 - Live USB Creator

## 在 Linux 下创建 Live USB
在`Linux`下创建`USB`镜像的方法有很多。我们将只关注两种推荐的方式：命令行上的`dd`和图形用户界面上的`SUSE Image Writer`。

### 命令行
使用`dd`命令是最常用的制作`Live USB`的方法。我们需要做的只是将路径转换为您的系统映像路径。
>注意: `USB`设备常用的标签是 `/dev/sdx` 而不是 `/dev/sdxX`。`USB` 驱动器的最常见的路径是 `/dev/sdb`。 但您的可能会不同，具体取决于您的系统。

若要查看当前连接到您系统的所有驱动器列表，运行此命令:

```
sudo fdisk -l
```

要烧写 Live Install 映像到您的 USB，运行以下命令:
```
sudo dd bs=4M if=/path/to/antergos-x86_64.iso of=/dev/sdX status=progress && sync 
```

### GUI工具
***etcher*** : 安全便捷地将镜像烧录至`SD`卡和`USB`设备。

 - [AUR - Antergos, Arch, Manjaro](https://aur.archlinux.org/packages/etcher/)
 - [https://etcher.io/](https://etcher.io/)
 
***Suse Image Writer*** : 方便使用，体验良好。您可以按照您系统地具体情况从以下地址选择下载：

 - [AUR - Antergos, Arch, Manjaro](https://aur.archlinux.org/packages/imagewriter/)
 - [.deb - Debian, Ubuntu, Mint](http://sourceforge.net/projects/linuxfreedomfor/files/Mix/imagewriter_1.9-1~lffl_all.deb/download)
 - [.rpm - openSUSE, Fedora](http://software.opensuse.org/package/imagewriter?search_term=imagewriter)

## 在 Windows 下创建 Live USB
USBWriter, Etcher and Rufus are free USB image writers that support .iso files (which Antergos uses) with ease. Just head to the Source Forge link for USBWriter for Windows or the Etcher link below and download the program. Once downloaded, follow the similar instructions for them below:
`USBWriter`，`Etcher`，以及`Rufus`都是免费易用的支持`.iso`文件（即`Antergos`的镜像格式）的`USB`镜像烧写工具。从下面对应的链接即可下载到这些软件。下载完后，就可以按照本文的简单步骤烧写镜像了。
![](https://rufus.akeo.ie/pics/rufus_en_2x.png)


 - [USBWriter][2]：“浏览（browse）”到镜像位置，选择好`USB`设备，然后点击“写入（write）”按钮，该软件便会正确地格式化并写入镜像。
 - [Rufus][3]：`Rufus`的操作界面如上图所示，选好设备，镜像位置，引导方式以及磁盘格式，点击`START`即可。
 - [Etcher][4]：“选择镜像（Select Image）”，然后“选择设备（Select Drive）”，然后点击“写入（Flash!）”

 


  [1]: https://antergos.com/wiki/wp-content/uploads/sites/2/2015/08/thumb-drive-e1317145079675-1080x675.jpg
  [2]: http://sourceforge.net/projects/usbwriter/
  [3]: https://rufus.akeo.ie/
  [4]: https://etcher.io/
