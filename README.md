<div>
    <a href="#中文版介绍" style="margin-left: 0; text-decoration: none;"><img src="https://img.shields.io/badge/跳转到中文版-中文介绍-red?style=for-the-badge&logo=gitbook&logoColor=white" alt="跳转到中文版"></a>
    <a href="https://www.gnu.org/licenses/gpl-3.0.txt" target="_blank" style="margin-left: 10px; text-decoration: none;"><img src="https://img.shields.io/badge/License-GPL%203.0-orange?style=for-the-badge&logo=gnu" alt="GPL v3 License"></a>
    <a href="https://github.com/DearCrazyLeaf/CS2-AutoUpdateReboot-PoweshellScript/issues" target="_blank" style="margin-left: 10px; text-decoration: none;"><img src="https://img.shields.io/github/issues/DearCrazyLeaf/CS2-AutoUpdateReboot-PoweshellScript?style=for-the-badge&logo=target" alt="GitHub Issues"></a>
    <a href="https://github.com/DearCrazyLeaf/CS2-AutoUpdateReboot-PoweshellScript/stargazers" target="_blank" style="margin-left: 10px; text-decoration: none;"><img src="https://img.shields.io/github/stars/DearCrazyLeaf/CS2-AutoUpdateReboot-PoweshellScript?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="GitHub Stars"></a>
</div>

---

> [!WARNING]
> This script is only used for windows server!  
> 该脚本仅作用于Windows系统下的服务器！

---

# CS2-AutoUpdateReboot Powershell script

 **This is a tool for automatically monitoring and restarting Counter-Strike 2 (CS2) servers. When the CS2 server process is detected to be down, it can automatically execute an update script (if configured) and restart the server, If used together with [CS2 AutoUpdate](https://github.com/M1Kac/CS2-AutoUpdate), it can achieve automated restarts and updates. 
For more details, see the introduction below.**

![1347_U2SQHATASM2MHXX](https://github.com/user-attachments/assets/0eaaf59f-1439-49e2-bad5-5e18c1f45d18)

## Features

- **Automatic Monitoring**: Regularly checks if the CS2 server process is running.
- **Automatic Restart**: Automatically executes an update script (if configured) and restarts the server when the server process stops.
- **Update Support**: Can run an update script before restarting to ensure the server is up-to-date.
- **Customizable**: Users can customize the server launch script path, update script path, check interval, and maximum retry attempts.

## How to Use

### Download the Script

 Click Code to download the script ZIP file.

 ![b8daedd5-5dd2-477d-98e8-906b3ebebe79](https://github.com/user-attachments/assets/1bb988e6-b198-4f08-88a3-be4f74b14730)

 Extract the downloaded file to a suitable location on your server.

### Configure the Script

 Open the `服务器自动重启.ps1` file.
 
 Find and configure the following parameters:
 ```ps1
 # User Configuration Area
 $targetProcessName = "cs2"   # Default process is cs2, replace if monitoring a different process (without .exe suffix)
 $launchBatPath = ""          # Path to your server launch batch script
 $updateScriptPath = ""       # Path to server update script (leave empty if update not required)
 $checkInterval = 5
 $maxRetry = 3
 ```

- `$launchBatPath`: Specify the full path to your server launch script (.bat file).
  
   For example: `C:\steam\...\start.bat`.
- `$updateScriptPath`: Specify the full path to your server update script (.bat file), if you don't need automatic update functionality, leave this empty.
  
  For example: `C:\steam\update.bat`.

### Run the Script

 Double-click the `启动监控.cmd` file to launch the script, The script will begin monitoring the CS2 server process.

## Script Parameter Instructions

| Parameter             | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `$targetProcessName`  | The name of the target process to monitor (default is "cs2", without the ".exe" extension). |
| `$launchBatPath`      | Path to the server launch script.                                          |
| `$updateScriptPath`   | Path to the server update script (optional).                               |
| `$checkInterval`      | Interval between checks (in seconds).                                      |
| `$maxRetry`           | Maximum number of retry attempts.                                          |

## Notes

- This script is only compatible with Windows-based servers.
- Ensure that the launch and update scripts have the appropriate permissions to be executed by this script.
- If the update script path is left empty, no update operation will be performed during restart.
- If your server's launch and update scripts are combined into one, you only need to fill in the `$launchBatPath` parameter.

## Using with CS2 AutoUpdate Plugin

 This script can be used in conjunction with the CS2 AutoUpdate plugin to enable in-game regular update checks or administrator-initiated update checks and remote server shutdowns. It will then automatically execute the update script and start the server. For more details about the plugin, visit the [CS2 AutoUpdate](https://github.com/M1Kac/CS2-AutoUpdate).

## Contributing

 Feel free to create Issues or submit Pull Requests if you have any questions, suggestions, or would like to contribute to the project.

 ## License

 <a href="https://www.gnu.org/licenses/gpl-3.0.txt" target="_blank" style="margin-left: 10px; text-decoration: none;">
        <img src="https://img.shields.io/badge/License-GPL%203.0-orange?style=for-the-badge&logo=gnu" alt="GPL v3 License">
    </a>

---
# 中文版介绍
# 基于 Powershell 脚本的 CS2 服务器自动监控和重启更新器

 这是一个用于 Counter-Strike 2（CS2）服务器的自动监控和重启工具，当检测到CS2服务器进程消失时，能够自动执行更新脚本（如果配置了路径）并重新启动服务器，如若搭配自动检测更新插件使用可以达到自动化重启更新的效果，具体查看下列介绍

 中文论坛帖子：https://bbs.csgocn.net/thread-1014.htm

## 特性

- **自动监控**：定期检测CS2服务器进程是否在运行
- **自动重启**：当检测到服务器进程停止时，自动执行更新脚本（如果配置了路径）并重新启动服务器
- **更新支持**：在重新启动前可执行更新脚本，确保服务器运行的是最新版本
- **可自定义**：可自定义服务器启动脚本路径、更新脚本路径、检查间隔和最大重试次数

## 使用方法

### 下载脚本

 点击仓库主页的 Code 并下载最新版本的脚本ZIP文件

 ![b8daedd5-5dd2-477d-98e8-906b3ebebe79](https://github.com/user-attachments/assets/1bb988e6-b198-4f08-88a3-be4f74b14730)
 
 将下载的文件解压到服务器上的合适位置

### 配置脚本

 打开 `服务器自动重启.ps1` 文件

 找到并配置以下参数：
 ```ps1
 # 用户配置区域
 $targetProcessName = "cs2"   #这里默认进程是cs2，如果想要检测其他的进程请替换！（后面不带.exe）
 $launchBatPath = ""          #这里填写你的服务器启动bat脚本文件路径
 $updateScriptPath = ""       #这里填写服务器更新bat脚本的路径，如果不需要更新功能可以留空
 $checkInterval = 5
 $maxRetry = 3
  ```

- `$launchBatPath`：填写服务器启动脚本（.bat 文件）的完整路径

  例如：`C:\steam\...\start.bat`
- `$updateScriptPath`：填写服务器更新脚本（.bat 文件）的完整路径。如果不需要自动更新功能，可留空

  例如：`C:\steam\update.bat`

### 运行脚本

 双击 `启动监控.cmd` 文件启动脚本，脚本将开始监控 CS2 服务器进程

## 脚本参数说明

| 参数                  | 说明                                                                 |
|-----------------------|--------------------------------------------------------------------|
| `$targetProcessName`  | 要监控的目标进程名称（默认为 “cs2”，不需要带 “.exe” 后缀）        |
| `$launchBatPath`      | 服务器启动脚本路径                                                |
| `$updateScriptPath`   | 服务器更新脚本路径（可选）                                         |
| `$checkInterval`      | 检测间隔时间（秒）                                                |
| `$maxRetry`           | 最大重试次数                                                     |

## 注意事项

- 该脚本仅适用于 Windows 服务器
- 确保启动脚本和更新脚本具有正确的权限，能够被脚本执行
- 如果更新脚本路径留空，则在重启时不会执行更新操作
- 如果服务器的启动脚本和更新脚本整合在一起，只需填写 `$launchBatPath` 参数即可

## 配合 CS2 AutoUpdate 插件使用

 该脚本可以与 CS2 AutoUpdate 插件配合使用，实现游戏内定期检测更新或管理员手动检测更新并远程关服后，自动执行更新脚本并启动服务器的功能。有关插件的更多信息，请访问 [CS2 AutoUpdate](https://github.com/M1Kac/CS2-AutoUpdate)

## 贡献

 如果您有任何问题、建议或希望贡献代码，请随时创建 Issue 或提交 Pull Request

## 许可证

<a href="https://www.gnu.org/licenses/gpl-3.0.txt" target="_blank" style="margin-left: 10px; text-decoration: none;">
        <img src="https://img.shields.io/badge/License-GPL%203.0-orange?style=for-the-badge&logo=gnu" alt="GPL v3 License">
    </a>
 
---
