**注:图片=链接。**

# 安装
## 第一步
当系统启动之后，就可以看到以下这个界面。选择“Install CentOS Linux 8.0”（安装 CentOS Linux 8.0）选项并按回车。<br>
<a href="https://img-blog.csdnimg.cn/img_convert/44cdb526aaf938ef4727d50471271caf.png" target="_blank">图1,查看请点击</a><br>
选择想要在 CentOS 8 安装过程中使用的语言，然后继续。<br>
<a href="https://img-blog.csdnimg.cn/img_convert/120e352795a69f6439a3a72f4686365c.png" target="_blank">图2,查看请点击</a><br>
- 这一步我们会配置以下内容：
  - 键盘布局
  - 日期和时间
  - 安装来源
  - 软件选择
  - 安装目标
  - Kdump
  Kdump
Installation-Summary-CentOS8

如上图所示，安装向导已经自动提供了“键盘布局Keyboard”、“时间和日期Time & Date”、“安装来源Installation Source”和“软件选择Software Selection”的选项。

如果你需要修改以上设置，点击对应的图标就可以了。例如修改系统的时间和日期，只需要点击“时间和日期Time & Date”，选择正确的时区，然后点击“完成Done”即可。

TimeZone-CentOS8-Installation

在软件选择选项中选择安装的模式。例如“包含图形界面Server with GUI”选项会在安装后的系统中提供图形界面，而如果想安装尽可能少的额外软件，可以选择“最小化安装Minimal Install”。

Software-Selection-CentOS8-Installation

这里我们选择“包含图形界面Server with GUI”，点击“完成Done”。

Kdump 功能默认是开启的。尽管这是一个强烈建议开启的功能，但也可以点击对应的图标将其关闭。

如果想要在安装过程中对网络进行配置，可以点击“网络与主机名Network & Host Name”选项。

Networking-During-CentOS8-Installation

如果系统连接到启用了 DHCP 功能的调制解调器上，就会在启动网络接口的时候自动获取一个 IP 地址。如果需要配置静态 IP，点击“配置Configure”并指定 IP 的相关信息。除此以外我们还将主机名设置为 “linuxtechi.com”。

完成网络配置后，点击“完成Done”。

最后我们要配置“安装目标Installation Destination”，指定 CentOS 8 将要安装到哪一个硬盘，以及相关的分区方式。

Installation-Destination-Custom-CentOS8

点击“完成Done”。

如图所示，我为 CentOS 8 分配了 40 GB 的硬盘空间。有两种分区方案可供选择：如果由安装向导进行自动分区，可以从“存储配置Storage Configuration”中选择“自动Automatic”选项；如果想要自己手动进行分区，可以选择“自定义Custom”选项。

在这里我们选择“自定义Custom”选项，并按照以下的方式创建基于 LVM 的分区：

/boot – 2 GB (ext4 文件系统)
/ – 12 GB (xfs 文件系统)
/home – 20 GB (xfs 文件系统)
/tmp – 5 GB (xfs 文件系统)
Swap – 1 GB (xfs 文件系统)
首先创建 /boot 标准分区，设置大小为 2GB，如下图所示：

boot-partition-CentOS8-Installation

点击“添加挂载点Add mount point”。

再创建第二个分区 /，并设置大小为 12GB。点击加号，指定挂载点和分区大小，点击“添加挂载点Add mount point”即可。

slash-root-partition-centos8-installation

然后在页面上将 / 分区的分区类型从标准更改为 LVM，并点击“更新设置Update Settings”。

Change-Partition-Type-CentOS8

如上图所示，安装向导已经自动创建了一个卷组。如果想要更改卷组的名称，只需要点击“卷组Volume Group”标签页中的“修改Modify”选项。

同样地，创建 /home 分区和 /tmp 分区，分别将大小设置为 20GB 和 5GB，并设置分区类型为 LVM。

home-partition-CentOS8-Installation

tmp-partition-centos8-installation

最后创建交换分区Swap Partition。

Swap-Partition-CentOS8-Installation

点击“添加挂载点Add mount point”。

在完成所有分区设置后，点击“完成Done”。

Choose-Done-after-manual-partition-centos8

在下一个界面，点击“应用更改Accept changes”，以上做的更改就会写入到硬盘中。

Accept-changes-CentOS8-Installation

第六步：选择“开始安装”
完成上述的所有更改后，回到先前的安装概览界面，点击“开始安装Begin Installation”以开始安装 CentOS 8。

Begin-Installation-CentOS8

下面这个界面表示安装过程正在进行中。

Installation-progress-centos8

要设置 root 用户的口令，只需要点击 “root 口令Root Password”选项，输入一个口令，然后点击“创建用户User Creation”选项创建一个本地用户。

Root-Password-CentOS8-Installation

填写新创建的用户的详细信息。

Local-User-Details-CentOS8

在安装完成后，安装向导会提示重启系统。

CentOS8-Installation-Progress

第七步：完成安装并重启系统
安装完成后要重启系统。只需点击“重启Reboot”按钮。

Installation-Completed-CentOS8

注意：重启完成后，记得要把安装介质断开，并将 BIOS 的启动介质设置为硬盘。

第八步：启动新安装的 CentOS 8 并接受许可协议
在 GRUB 引导菜单中，选择 CentOS 8 进行启动。

Grub-Boot-CentOS8

同意 CentOS 8 的许可证，点击“完成Done”。

Accept-License-CentOS8-Installation

在下一个界面，点击“完成配置Finish Configuration”。

Finish-Configuration-CentOS8-Installation

第九步：配置完成后登录
同意 CentOS 8 的许可证以及完成配置之后，会来到登录界面。

Login-screen-CentOS8

使用刚才创建的用户以及对应的口令登录，按照提示进行操作，就可以看到以下界面。

CentOS8-Ready-Use-Screen

点击“开始使用 CentOS LinuxStart Using CentOS Linux”。

Desktop-Screen-CentOS8

以上就是 CentOS 8 的安装过程，至此我们已经完成了 CentOS 8 的安装。
