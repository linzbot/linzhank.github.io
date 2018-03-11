# 深度學習機器人配置

## TK1刷機
> 準備工作： 
> 1. 個人電腦\(需已安裝Ubuntu 14.04\)
> 2. Jetson TK1 開發板
> 3. USB-A轉USB-Micro_B數據線一根
> 4. \(可選)網線兩根\(一根用於Jetson TK1，另一根用於個人電腦，有助於文件下載時的穩定性)

### 用Jetpack刷機
爲了使Jetson TK1開發板具有可用的操作系統，需要用Jetpack工具進行刷機。
- 從[這裏](https://developer.nvidia.com/embedded/downloads?#?tx=$product,jetson_tk1)下載Jetpack3.0 \(需登錄Nvidia developer賬號\)。
- 打開終端\(`Ctrl+Alt+T`)，`$ cd Jetpack的下載路徑`，授予剛剛下載的文件運行權限 `$ chmod +x JetPack-L4T-3.0-linux-x64.run`，運行剛剛下載的Jetpack`$ ./JetPack-L4T-3.0-linux-x64.run`。
- 用USB數據線鏈接個人電腦和Jetson TK1，根據[官方教程](http://docs.nvidia.com/jetpack-l4t/index.html#developertools/mobile/jetpack/l4t/3.0/jetpack_l4t_install.htm)進行刷機\(**注意：TK1進入Force Recovery模式後，在電腦上新開一個終端運行`$ lsusb`，確保設備列表中出現了`ID 0955:7140 NVidia Corp`**)。

### 刷機後的配置（宜在刷機後立即進行配置）
爲了安裝chromium瀏覽器、優化電源管理、優化CPU以及GPU性能、開啓USB3.0，禁用usb自動關閉等功能，需要在成功用Jetpack刷機後進行一系列設置，具體請參考[jetsonhacks](http://www.jetsonhacks.com/2015/03/10/after-lt4-21-3-flash-setup-nvidia-jetson-tk1/)上的鏈接，以及[github](https://github.com/jetsonhacks/postFlash)上的說明。

以下操作均在Jetson TK1上完成，打開一個終端`Ctrl+Alt+T`
  1. 安裝git：`$ sudo apt install git`
  2. `$ git clone https://github.com/jetsonhacks/postFlash.git`
  3. 進入postFlash腳本所在路徑`$ cd postFlash`，運行`$ ./configureSystem.sh`
  4. 重啓TK1使得設置生效。
  5. 運行`$ ./maxPerformances.sh`即刻提升TK1工作性能。

### 安裝自定義內核
1. 爲了方便之後的使用，需要安裝grinch內核，詳情可以參考(這裏)[http://www.jetsonhacks.com/2015/05/26/install-grinch-kernel-for-l4t-21-3-on-nvidia-jetson-tk1/]。
> 首先下載安裝grinch內核的腳本，`$ git clone https://github.com/jetsonhacks/installGrinch.git`；
> 進入腳本所在路徑`$ cd installGrinch`；
> 運行腳本`$ ./installGrinch.sh`\（如果已經下載了grinch內核則執行另一個腳本`$ ./installGrinchNoDownload.sh`）。
> 重啓。並在終端中驗證當前內核版本`$ uname -r`，結果應顯示爲`3.10.40-frinch-21.3.4`
2. 爲了將來可以在ROS中安裝turtlebot的開發包，需要對現有內核作進一步的自定義，詳情可以參考[這裏](http://www.jetsonhacks.com/2016/06/29/build-custom-kernel-nvidia-jetson-tk1/)
> 

## 安裝ROS

## 底座及傳感器配置

### 安裝Kinect2驅動

### 在ROS中配置RpLidar

### 在ROS中配置底座
