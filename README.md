# 資訊
- [RisingOS Telegram](https://t.me/RisingOS_news)
- [安裝參考](https://droidwin.com/install-evolution-x-android-13-rom-on-pixel-6a-6-6-pro-video/)
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
```powershell
adb reboot bootloader
```
- 刷入 dtbo
```powershell
fastboot flash dtbo dtbo.img
```
- 刷入 vendor_boot
```powershell
fastboot flash vendor_boot vendor_boot.img
```
- 刷入 vendor_kernel_boot
```powershell
fastboot flash vendor_kernel_boot vendor_kernel_boot.img
```
- 刷入 boot
```powershell
fastboot flash boot boot.img
```
- 刷入 init_boot
```powershell
fastboot flash init_boot init_boot.img
```
- 重新啟動至 recovery
```powershell
fastboot reboot recovery
```
- 切換至側載模式，使用 adb sideload 刷入 OTA 檔案
```powershell
adb sideload RisingOS-5.2.1-FINAL-STABLE-EOL-20241006-GAPPS-OFFICIAL-husky-ota-signed.zip
```
- 如果收到以下錯誤訊息之一，則表示安裝成功，您可以將裝置重新啟動到作業系統，沒有任何問題
```
Total xfer: 1.00x
adb: failed to read command: Success/No error
adb: failed to read command: No error
(~47%) adb: failed to read the command: No error
adb: failed to read command: Undefined error: 0
```
- 完成後必須清除使用者資料，使用裝置 recovery mode 中的 Factory reset >> Format data / factory reset >> Format data
- 重新啟動裝置
```powershell
adb reboot
```
# 更新 RisingOS
- 重新啟動至 recovery
```powershell
fastboot reboot recovery
```
- 切換至側載模式，使用 adb sideload 刷入更新的 OTA 檔案
```powershell
adb sideload RisingOS-new-FINAL-STABLE-EOL-XXXXXXXX-GAPPS-OFFICIAL-husky-ota-signed.zip
```
- 無須清除使用者資料
- 重新啟動裝置即可
```powershell
adb reboot
```
