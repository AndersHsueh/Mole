<div align="center">
  <h1>Mole</h1>
  <p><em>🐹 像鼹鼠一样深入挖掘，清理你的 Mac。</em></p>
</div>

<p align="center">
  <a href="https://github.com/tw93/mole/stargazers"><img src="https://img.shields.io/github/stars/tw93/mole?style=flat-square" alt="Stars"></a>
  <a href="https://github.com/tw93/mole/releases"><img src="https://img.shields.io/github/v/tag/tw93/mole?label=version&style=flat-square" alt="Version"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square" alt="License"></a>
  <a href="https://github.com/tw93/mole/commits"><img src="https://img.shields.io/github/commit-activity/m/tw93/mole?style=flat-square" alt="Commits"></a>
  <a href="https://twitter.com/HiTw93"><img src="https://img.shields.io/badge/follow-Tw93-red?style=flat-square&logo=Twitter" alt="Twitter"></a>
  <a href="https://t.me/+GclQS9ZnxyI2ODQ1"><img src="https://img.shields.io/badge/chat-Telegram-blueviolet?style=flat-square&logo=Telegram" alt="Telegram"></a>
</p>

<p align="center">
  <img src="https://cdn.tw93.fun/img/mole.jpeg" alt="Mole - 95.50GB freed" width="800" />
</p>

## 功能

- 🐦 **深度系统清理** - 一键清除隐藏的缓存、日志和临时文件
- 📦 **彻底卸载** - 清理 22+ 个位置 vs 1 个标准位置，优于 CleanMyMac/Lemon
- 📊 **交互式磁盘分析器** - 像文件管理器一样导航文件夹，立即查找和删除大文件
- ⚡️ **快速且轻量** - 基于终端，零臃肿，带分页的箭头键导航

## 快速开始

**提示：**

- 在关键任务 Mac 上，请等待 Mole 更成熟，安全第一
- 如果这台 Mac 对你非常重要，建议等 Mole 更成熟时来使用，安全第一
- 不太懂技术？查看 [小白使用指南](./GUIDE.md)

**安装：**

```bash
curl -fsSL https://raw.githubusercontent.com/tw93/mole/main/install.sh | bash
```

或通过 Homebrew：

```bash
brew install tw93/tap/mole
```

**运行：**

```bash
mo                      # 交互式菜单
mo clean                # 系统清理
mo clean --dry-run      # 预览模式
mo clean --whitelist    # 管理受保护的缓存
mo uninstall            # 卸载应用
mo analyze              # 磁盘分析器
mo update               # 更新 Mole
mo remove               # 从系统中移除 Mole
mo --help               # 显示帮助
mo --version            # 显示安装版本
# 如果找不到命令，请运行 `mole update` 一次以升级到最新版本。
```

> 建议先使用 `mo clean --dry-run` 预览，使用 `mo clean --whitelist` 保护缓存

## 功能详情

### 深度系统清理

```bash
$ mo clean

▶ 系统必需品
  ✓ 用户应用缓存 (45.2GB)
  ✓ 用户应用日志 (2.1GB)
  ✓ 回收站 (12.3GB)

▶ 浏览器清理
  ✓ Chrome 缓存 (8.4GB)
  ✓ Safari 缓存 (2.1GB)

▶ 开发者工具
  ✓ Xcode 衍生数据 (9.1GB)
  ✓ Node.js 缓存 (14.2GB)

▶ 其他
  ✓ Dropbox 缓存 (5.2GB)
  ✓ Spotify 缓存 (3.1GB)

====================================================================
🎉 清理完成！
💾 释放空间: 95.50GB | 当前可用空间: 223.5GB
====================================================================
```

### 智能应用卸载器

```bash
$ mo uninstall

🗑️  选择要移除的应用
═══════════════════════════
▶ ☑ Adobe Creative Cloud      (12.4G) | 旧
  ☐ WeChat                    (2.1G) | 最近
  ☐ Final Cut Pro             (3.8G) | 最近

🗑️  正在卸载: Adobe Creative Cloud
  ✓ 已移除应用程序              # /Applications/
  ✓ 清理了 52 个相关文件         # ~/Library/ 共 12 个位置
    - 支持文件和缓存             # 应用支持, 缓存
    - 偏好设置和日志             # 偏好设置, 日志
    - WebKit 存储和 Cookie       # WebKit, HTTPStorages
    - 扩展和插件                 # 互联网插件, 服务
    - 需要 sudo 的系统文件       # /Library/, Launch 守护进程
```

### 磁盘空间分析器

```bash
$ mo analyze

📊 正在分析: /Users/You
═══════════════════════════════════════════════════════
总计: 156.8GB

├─ 📁 Library                                        45.2GB
│  ├─ 📁 Caches                                      28.4GB
│  └─ 📁 Application Support                         16.8GB
├─ 📁 Downloads                                      32.6GB
│  ├─ 📄 Xcode-14.3.1.dmg                            12.3GB
│  ├─ 📄 backup_2023.zip                             8.6GB
│  └─ 📦 old_projects.tar.gz                         5.2GB
├─ 📁 Movies                                         28.9GB
│  ├─ 📄 vacation_2023.mov                           15.4GB
│  └─ 📄 screencast_raw.mp4                          8.8GB
├─ 📁 Documents                                      18.4GB
└─ 📁 Desktop                                        12.7GB
```

## 常见问题

1. **Mole 安全吗？** – Mole 专注于清理缓存和日志，不会触及应用设置、用户文档或系统文件。你可以在实际清理之前运行 `mo clean --dry-run` 预览将要删除的内容。
2. **应该多久清理一次？** – 大约一个月一次，或当你发现磁盘空间不足时。
3. **我可以保护特定缓存吗？** – 是的。运行 `mo clean --whitelist` 交互式选择要保留的缓存。一些常见的缓存（如 Playwright 浏览器和 HuggingFace 模型）默认已受保护。

## 支持

- ⭐️ 如果 Mole 帮你恢复了磁盘空间，请**为这个仓库点星**
- 💬 与**需要清理 Mac 的朋友分享**
- 🐛 通过 [GitHub Issues](https://github.com/tw93/mole/issues) **报告问题**
- 🐱 我有两只猫，<a href="https://miaoyan.app/cats.html?name=Mole" target="_blank">如果你想的话可以喂它们罐头食品</a>

## 许可证

MIT 许可证 - 随意享受和参与开源。