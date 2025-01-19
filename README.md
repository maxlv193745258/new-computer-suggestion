

这是你拿到新电脑后的一些建议

1.windowes

跳过windows的强制联网激活

在 Windows 11 OOBE（Out of Box Experience，首次启动设置）过程中，微软要求用户必须连接网络才能创建账号和继续安装。然而，有一些方法可以跳过联网并直接创建本地账户。以下是几种有效的方法：

方法 1：使用 OOBE\BYPASSNRO 命令（推荐）

Windows 11 有隐藏的“跳过联网”模式，可以通过 Shift + F10 调出命令提示符，然后执行以下步骤：

步骤
在联网页面（“让我们连接到一个网络”）时，按下 Shift + F10，打开命令提示符（CMD）。
2.在 CMD 中输入以下命令并回车：

	OOBE\BYPASSNRO


电脑会自动重启，并重新进入 OOBE 设置界面。
4.这次你会看到一个 “我没有 Internet” 选项，点击它。
5.选择 “继续执行有限的设置”（Continue with limited setup）。
6.继续设置本地账户，无需联网。

✅ 适用于 Windows 11 所有版本，包括 22H2 及更新版本。

方法 2：输入假邮箱（部分版本适用）

在某些 Windows 11 版本（如 Home 版）中，可以输入一个 无效的邮箱 让系统跳过联网要求。

步骤
在联网页面，尝试连接 Wi-Fi，或者插入网线。
在 Microsoft 账号登录页面，输入一个 假邮箱（如 noemail@outlook.com）。
输入任何密码（如 123456），然后点击下一步。
系统会显示“出错了”或“发生问题”，此时点击 “下一步” 或 “跳过”。
你将进入本地账户创建界面。

⚠️ 此方法并不适用于所有 Windows 11 版本，部分新版 Windows 可能已经封锁。

方法 3：直接断网

Windows 11 安装时，如果检测不到网络，它会允许你创建本地账户。

步骤
拔掉网线（如果是有线网络）。
禁用 Wi-Fi：
如果你的电脑有 Wi-Fi 物理开关，直接关闭 Wi-Fi。
如果没有，进入 BIOS/UEFI 禁用无线网卡（部分主板支持）。
重启电脑，继续安装 Windows 11。
进入 OOBE 界面时，系统会提示“无法连接到 Internet”，然后会提供创建本地账户的选项。

✅ 适用于无网络连接的情况，但部分新版本可能强制要求联网。

方法 4：使用 Task Manager 结束 OOBE 进程

在部分 Windows 11 版本中，可以通过任务管理器强制终止网络检查流程。

步骤
在联网页面，按下 Shift + F10 打开命令提示符（CMD）。
在 CMD 中输入：
	taskmgr
然后按 Enter，打开任务管理器。

在任务管理器中找到 “网络连接流”（Network Connection Flow） 或 oobenetworkconnectionflow.exe。
右键它并选择 “结束任务”（End Task）。
回到 OOBE 界面，你应该能看到 “我没有 Internet” 选项，点击它。
继续创建本地账户。

✅ 适用于部分 Windows 11 版本，部分版本可能不会出现该进程。

方法 5：修改注册表（高级用户）

如果你可以访问注册表，可以通过修改注册表来禁用联网强制要求。

步骤
按 Shift + F10 打开 CMD。
输入 
	regedit 
 并回车，打开注册表编辑器。
导航到：

	HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE


在右侧找到 BypassNRO（如果没有，就新建一个 DWORD (32-bit) Value），然后将值改为 1。
关闭注册表，重启电脑。

✅ 适用于部分 Windows 11 版本，但修改注册表需要谨慎。

总结

方法	适用性	难度	适用版本
OOBE\BYPASSNRO 命令	✅ 最推荐	⭐⭐	所有 Windows 11 版本
输入假邮箱	⚠️ 部分有效	⭐	仅部分 Windows 11 版本
拔掉网线 + 断开 Wi-Fi	✅ 简单	⭐	部分 Windows 11 版本
任务管理器结束进程	⚠️ 可能有效	⭐⭐	部分 Windows 11 版本
修改注册表	⚠️ 需要经验	⭐⭐⭐	需要手动操作


💡 推荐使用 OOBE\BYPASSNRO 方法，它适用于所有 Windows 11 版本，并且操作简单。
安装图吧工具 
在 https://www.tbtool.cn/ 下载
图吧工具箱监测 在'图吧工具箱2025.01安装程序.exe'安装完测试

安装英伟达驱动 
英伟达驱动在‘https://www.nvidia.com/en-us/drivers/ 下载
打开下载下来的文件 一直下一步就行

2.安装ubuntu 
在windows按下 Win+X 进入分区管理给ubuntu分 204800MB 不要格式化
在  https://ubuntu.com/download/desktop  下载LST长期支持版
在  https://etcher.balena.io/  下载BalenaEtcher
用BalenaEtcher烧录把 ubuntu-24.04.1-desktop-amd64.iso  烧录到u盘，
开机按F2（华硕laptop是这个 其他电脑可能是 f10 f8 esc dlete等）进入bios，设置u盘（UEFI）为第一引导，
按F10重启
开机后选 Try or install ubuntu 进入安装程序，
语言选择简体中文 
到了分区的地方 选择自己分区 选100mb的EFI分区为efi ，设后面面204.8GB的分区挂在点为 / 
然后一直下一步 正常安装 不要同时安装更新时区选温哥华 然后等带进入系统 

Ubuntu安装英伟达驱动
在 Ubuntu 24.04 上安装 NVIDIA RTX 3060驱动（这给我的显卡，如果你的是其他型号吧“3060”换成你的型号就行） ，推荐使用 Ubuntu 自带的 ubuntu-drivers，步骤如下：

方法 1：使用 Ubuntu 官方驱动（推荐）

适用于大多数用户，系统会自动匹配最稳定的驱动。

步骤

更新系统

	sudo apt update && sudo apt upgrade -y

列出可用的 NVIDIA 驱动

	ubuntu-drivers devices

示例输出（仅供参考，具体版本可能不同）：

	driver : nvidia-driver-550 - third-party free recommended
	driver : nvidia-driver-535 - third-party free


安装推荐的驱动（假设推荐的是 nvidia-driver-550）

	sudo apt install -y nvidia-driver-550

重启系统

	sudo reboot


验证驱动安装是否成功

	nvidia-smi

如果显示 GPU 信息，则说明安装成功。

方法 2：自动安装 NVIDIA 驱动（简化方式）

如果不想手动选择驱动版本，可以让系统自动安装推荐的驱动：

步骤
更新系统

	sudo apt update && sudo apt upgrade -y


自动安装推荐的 NVIDIA 驱动

	sudo ubuntu-drivers autoinstall


重启系统

	sudo reboot

验证 NVIDIA 驱动

	nvidia-smi

方法 3：从 NVIDIA 官网安装最新驱动（高级用户）

如果你需要 最新的 NVIDIA 驱动，可以从 NVIDIA 官网手动安装，但可能会出现兼容性问题。

步骤
卸载已有的 NVIDIA 驱动

	sudo apt remove --purge '^nvidia-.*'
	sudo apt autoremove


下载 NVIDIA 官网驱动
访问 NVIDIA 官方网站
选择 Linux x86_64，下载 .run 文件
切换到文本模式
	按 Ctrl + Alt + F3 进入终端，并登录。
禁用桌面环境（GUI）

	sudo systemctl stop gdm


赋予驱动安装文件执行权限

	chmod +x NVIDIA-Linux-x86_64-*.run


运行安装程序

	sudo ./NVIDIA-Linux-x86_64-*.run

按照提示进行安装。

启用 GUI 并重启

	sudo systemctl start gdm
	sudo reboot


验证驱动

	nvidia-smi

解决常见问题

1. 安装后黑屏或无法进入系统
2. 进入 tty 终端（Ctrl + Alt + F3），然后执行：

	sudo nano /etc/default/grub

找到：

	GRUB_CMDLINE_LINUX_DEFAULT="quiet splash

修改为：

	GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset

然后更新 GRUB：

	sudo update-grub
	sudo reboot



2. 卸载 NVIDIA 驱动

如果遇到问题，想卸载 NVIDIA 驱动：

	sudo apt remove --purge '^nvidia-.*'
	sudo apt autoremove
	sudo reboot

总结

✅ 推荐使用 ubuntu-drivers 进行自动安装，最稳定
✅ 需要最新驱动时，可以去 NVIDIA 官网下载 .run 文件手动安装
⚠️ 如果遇到黑屏问题，可以尝试 nomodeset 选项修复

美化

在 Ubuntu 24.04 上安装 GNOME 扩展，以及进行自定义设置和美化，通常需要以下工具：

✅ GNOME Shell Extensions（GNOME 扩展）
✅ GNOME Tweaks（GNOME 调整工具）
✅ Extensions Manager（扩展管理器）
✅ Gnome Shell 主题和图标

1. 安装 GNOME 扩展管理工具

1.1 安装 GNOME Tweaks & 扩展管理器

	sudo apt update && sudo apt install -y gnome-tweaks gnome-shell-extensions gnome-extension-manager

gnome-tweaks（GNOME Tweaks）：用于调整 GNOME 设置
gnome-shell-extensions（GNOME Shell 扩展集合）：包含官方的 GNOME 扩展
gnome-extension-manager（扩展管理器）：GUI 管理 GNOME 扩展

安装完成后，在 “应用程序” 里搜索 GNOME Tweaks 或 扩展管理器 即可使用。

1.2 启用用户扩展支持（安装浏览器插件）

如果你想从浏览器安装 GNOME 扩展，需要启用 chrome-gnome-shell：

	sudo apt install -y chrome-gnome-shell

然后打开 GNOME 扩展官网 👉 https://extensions.gnome.org/

根据提示安装 浏览器插件，然后你就可以从网站直接安装扩展了！

2. 常用 GNOME 美化扩展

安装后，可以在 “扩展管理器” 或 GNOME Tweaks 中管理这些扩展。

扩展名称	作用	安装命令
Dash to Dock	让 Dock 类似 macOS 样式	
	gnome-extensions install dash-to-dock@micxgx.gmail.com
Arc Menu	类似 Windows 开始菜单	
	gnome-extensions install arcmenu@arcmenu.com
Blur My Shell	添加模糊透明效果	
	gnome-extensions install blur-my-shell@aunetx
Just Perfection	细节调整（隐藏 UI 元素）	
	gnome-extensions install just-perfection@just-perfection
Caffeine	禁止屏幕自动锁定	
	gnome-extensions install caffeine@patapon.info

3. 安装 GNOME 主题和图标

默认的 GNOME 主题可能比较单调，你可以安装一些美化主题。

3.1 安装 GTK 主题

	sudo apt install -y arc-theme materia-gtk-theme

然后在 GNOME Tweaks 里切换主题。

3.2 安装图标主题

	sudo apt install -y papirus-icon-theme numix-icon-theme

在 GNOME Tweaks 里切换图标。

4. 修改 Dock（Ubuntu Dock）

如果你不想使用 Dash to Dock，可以直接修改 Ubuntu Dock 的设置。

4.1 让 Dock 变小

	gsettings set org.gnome.shell.extensions.dash-to-dock dash-max-icon-size 32

4.2 让 Dock 自动隐藏

	gsettings set org.gnome.shell.extensions.dash-to-dock autohide true

5. 其他 GNOME 美化设置

5.1 让 GNOME 终端透明

打开终端 → 首选项 → 外观 → 调整透明度

5.2 让顶部面板透明

安装 Transparent Top Bar 扩展：

	gnome-extensions install transparent@glassman.com

6. 总结
	•	基本工具：gnome-tweaks、gnome-extension-manager
	•	扩展：Dash to Dock、Blur My Shell、Just Perfection
	•	美化：Papirus 图标、Arc 主题
	•	Dock 调整：隐藏、调整大小

这样，你的 Ubuntu 24.04 GNOME 桌面 体验会更美观、更实用！ 🎨✨

steamos桌面教程
文字教程: 
 	https://apiclo.github.io/gamescope

一键安装脚本

	curl -sSL https://raw.githubusercontent.com/Apiclo/Apiclo.github.io/master/shells/steamos.sh -o steam-session.sh && /bin/bash steam-session.sh



