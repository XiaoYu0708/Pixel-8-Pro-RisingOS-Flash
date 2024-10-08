# 資訊
- [RisingOS Telegram](https://t.me/RisingOS_news)
# 準備工作
## 下載
- [RisingOS for Husky (Pixel 8 Pro)](https://sourceforge.net/projects/risingos-for-husky/)
- Official 版本
### 檔案
- OTA File
- boot.img
- dtbo.img
- vendor_boot.img
# 安裝
- 重新啟動至 bootloader
```
adb reboot bootloader
```
- 刷入 dtbo
```
fastboot flash dtbo dtbo.img
```
- 刷入 vendor_boot
```
fastboot flash vendor_boot vendor_boot.img
```
- 刷入 boot
```
fastboot flash boot boot.img
```
- 重新啟動至 recovery
```
fastboot reboot recovery
```
切換至側載模式，使用 adb sideload 刷入 OTA 檔案
```
adb sideload RisingOS-5.2.1-FINAL-STABLE-EOL-20241006-GAPPS-OFFICIAL-husky-ota-signed.zip
```
