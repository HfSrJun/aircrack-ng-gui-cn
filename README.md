# aircrack-ng GUI

一个使用python-gtk3编写的[aircrack-ng](https://www.github.com/aircrack-ng/aircrack-ng)图形界面。 

由HfSr进行中文翻译

## 它能干啥？
使用[aircrack-ng](https://www.github.com/aircrack-ng/aircrack-ng)和`iw`对WPA/WPA2网络发动暴力破解攻击。

## 用法
### 在Linux上安装
* 首先确保已安装[aircrack-ng](https://www.github.com/aircrack-ng/aircrack-ng)和`xterm`。
* 克隆仓库：`git clone https://github.com/t-gitt/aircrack-ng-gui.git`
* `cd aircrack-ng-gui/`
* 运行`sudo python start.py install`，安装脚本文件。
* 安装后脚本应当会被添加到/usr/bin/中，你可以在终端里执行`sudo aircrack-ng-gui.py`以运行此软件。

#### 卸载
* 你可以通过pip卸载此软件，只需执行：`pip uninstall aircrack-ng-gui`。


### 手动运行脚本
* 首先确保已安装[aircrack-ng](https://www.github.com/aircrack-ng/aircrack-ng)和`xterm`。
* 克隆仓库
* `cd aircrack-ng-gui/`
* 执行`pip install -r requirements.txt`，安装依赖。 
* 通过`sudo python aircrack-ng-gui/aircrack-ng-gui.py`来运行aircrack-ng-gui。请确保你运行时使用的是python 3。

> Airodump-ng的输出文件被存放于`/home/$USER/.aircrack-ng-gui/`

## 截图

### 主窗口
软件的主界面。用户在选择了网络接口（图中wlp4s0）后，可在此窗口选择跳转到扫描、airmon-ng和aircrack-ng窗口。

![Alt text](screenshots/1.png?raw=true "ScreenShot 1")

### Airmon-ng窗口
用于检查、启动和停止airmon-ng的窗口。还可用于启动与停止systemd NetworkManager.service。

![Alt text](screenshots/9.png?raw=true "ScreenShot 9")

### 扫描窗口
wifi接入点扫描窗口。在选择网络接口后，用户可使用iw扫描wifi接入点。用户在选好了目标接入点后，即可启动airmon-ng并前往airodump-ng。

![Alt text](screenshots/2.png?raw=true "ScreenShot 2")

### “已经选择ssid的”Airmon-ng窗口
与Airmon-ng窗口十分类似，但是此窗口会向Airodump-ng传递ssid变量"SSID, BSSID, CHANNEL"。

![Alt text](screenshots/3.png?raw=true "ScreenShot 3")

### Airodump-ng窗口 | 1
用于（通过指定的终端模拟器）对目标SSID运行airodump-ng，并将文件（内含握手包）输出为你指定的文件名。（最好用STDERR和subprocess）

![Alt text](screenshots/5.png?raw=true "ScreenShot 5")



### Airodump-ng窗口 | 2
在运行airodump-ng后，用户可使用aireplay来向指定station发送指定次数的下线包，以便于获取握手包。

![Alt text](screenshots/6.png?raw=true "ScreenShot 6")

### Aircrack-ng窗口
在将握手包保存到cap文件中后，可通过主窗口访问aircrack。用户需选定某个包含握手包的.cap文件和一个字典文件，以在选定的终端模拟器中进行暴力破解。

![Alt text](screenshots/8.png?raw=true "ScreenShot 8")

## 捐助
![bitcoin](https://raw.githubusercontent.com/t-gitt/aircrack-ng-gui/master/bitcoin-address.txt)

## 目录树
```
├── LICENSE
├── README.md
├── requirements.txt
├── setup.py
├── start.py
├── aircrack-ng-gui
│  ├── __init__.py
│  └── aircrack-ng-gui.py
└── screenshots
   ├── 1.png
   ├── 2.png
   ├── 3.png
   ├── 4.png
   ├── 5.png
   ├── 6.png
   ├── 7.png
   ├── 8.png
   └── 9.png
```
