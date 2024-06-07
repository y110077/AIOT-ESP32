# AIOT ESP32—ESP-IDF Tools安裝及環境建置（Hello World）（Windows）

## 目錄
#### >> [ESP-IDF 安裝及環境建置（Hello World）（Win）](https://github.com/yuu1177/AIOT-ESP32/blob/main/README.md)
#### [復原眼睛辨識（Win）](https://github.com/yuu1177/AIOT-ESP32-Windows-/blob/main/README.md)

## ESP-IDF Tools 安裝及建置步驟
（以 ESP32S3 晶片在 Windows 環境下的設定為例）

1. 至 <https://dl.espressif.com/dl/esp-idf/> 下載離線安裝包 
*ESP-IDF v5.2.1 - Offline Installer Windows 10, 11 Size: 1.5 GB*
    - [使用一键安装工具快速搭建 ESP-IDF 开发环境（Windows）| YouTube](
    https://www.youtube.com/watch?v=DyioH2PkqLo&t=227s) 

2. 安裝預設路徑 `<D:\ESPIDF>`（可自訂）

3. 安裝時勾選
    - ESP32—S 系列
    - Python 3.7
    - 三項 Select Additional Tasks

4. 安裝完畢後執行 ESP-IDF CMD（預設在桌面）

5. 待終端機輸出 ```idf.py build``` 表示環境設置成功

6. 終端機輸入指令創建資料夾並進入 
   `<D:\ESPIDF\Espressif\frameworks\esp-idf-v5.2.1\examples\get-started>`
    ```
    cd D:\ESPIDF\Espressif\frameworks\esp-idf-v5.2.1\examples\get-started
    ```
7. 終端機輸入指令將晶片設定為 esp32s3
    ```
    idf.py set-target esp32s3
    ```

8. 終端機輸入指令運行 menuconfig
    ```
    idf.py menuconfig
    ```

9. 進入 menuconfig 圖形配置工具修改 flash 記憶體大小（自訂義）

10. 終端機輸入指令創建資料夾並進入
    `<D:\ESPIDF\Espressif\frameworks\myproject>`
    ```
    mkdir myproject
    cd D:\ESPIDF\Espressif\frameworks\myproject
    ```

11. 將本機 `<D:\ESPIDF\Espressif\frameworks\esp-idf-v5.2.1\examples\get-started>` 裡的 `hello_world` 資料夾複製到新創立的 `myproject` 資料夾 `<D:\ESPIDF\Espressif\frameworks\myproject>`

12. 終端機輸入指令清除先前配置
    ```
    idf.py fullclean
    ```

13. 終端機輸入指令編譯燒錄工程
    ```
    idf.py build
    ```

14. 編譯後會在 hello_world 資料夾內生成
    - partition-table.bin
    - hello_world.bin
    - bootloader.bin
 
15. 至裝置管理員查看 ESP32 開發板在電腦接口的名稱 `COM3`

16. 終端機輸入指令下載 hello world 程序到開發板（`COM3` 依電腦接口自訂）
    ```
    idf.py -p COM3 flash
    ```

17. 終端機輸入指令監視 hello world 運行狀況（`COM3` 依電腦接口自訂）
    ```
    idf.py -p COM3 monitor
    ```

18. 終端機反覆輸出 `"Hello world"` 並開始倒數表示執行成功
    ```
    Hello world!
    This is esp32s3 chip with 2 CPU core(s), WiFi BLE, silicon revision v0.2, 
    2MB external flash Minimum free heap size: 386880 bytes
    Restarting in 10 seconds...
    Restarting in 9 seconds...
    Restarting in 8 seconds...
    Restarting in 7 seconds...
    Restarting in 6 seconds...`
    ```
    ![終端機輸出 Hello world](https://hackmd.io/_uploads/SJXdf-sNA.png)


19. 按 `Ctrl + C` 跳出

20. 安裝及建置完成

## 參考資料
- [ESP32 开发之路（1）— 搭建在 Windows 下的开发环境 | CSDN](https://blog.csdn.net/qq_38113006/article/details/116274693)

## 附加資源
- [ESP-IDF 編程指南](https://espressif-docs.readthedocs-hosted.com/projects/esp-idf/zh-cn/latest/get-started/index.html)

