# 树夏Music 多端发布中心

树夏Music 是一套「安卓/车机 + Mac 桌面 + NAS 同步服务器 + 飞牛在线听歌」的多端音乐方案。
各端共享同一套歌单、收藏和播放记忆：在任意一端收藏歌曲或建歌单，其它端自动同步。

## 产品与下载

| 端 | 它是干嘛的 | 当前版本 | 下载地址 |
| --- | --- | --- | --- |
| **树夏Music 安卓** | 面向车机、平板和横向大屏的安卓音乐播放器：多平台搜索、多音质播放、歌词、频谱、歌单管理、洛雪插件；支持应用内自动更新 | v2.5.109 | [最新版 APK（本仓库最新 Release）](https://github.com/maiga512/shuxiamusic-release/releases/latest) · [Gitee 国内镜像](https://gitee.com/songsong2020/shuxiamusic-release) |
| **树夏Music 桌面端** | 桌面端音乐播放器（Tauri + Rust + Vue），功能与安卓版对齐：搜索、播放、歌词、歌单、多端同步 | v1.0.6 | [desktop-latest（本仓库固定标签）](https://github.com/maiga512/shuxiamusic-release/releases/tag/desktop-latest) · [Gitee 国内镜像](https://gitee.com/songsong2020/shuxiamusic-desktop-release) |
| **树夏Music 同步服务器** | 部署在自家 NAS 上的歌单同步服务（Docker 一键部署）：保存用户、歌单、歌曲和收藏关系，各端客户端都连它同步 | v0.1.0 | [仓库与部署文档](https://github.com/maiga512/CeruMusic-NAS-Sync) |
| **飞牛在线听歌插件** | 基于 @javycoder 同名开源项目改编增强（版权归原作者）：面向飞牛 fnOS 自带音乐应用的无侵入扩展，在线聚合搜播、管理 WebUI、边听边存，本版本增加多端同步 | v2.6.50 | [.fpk 安装包（本仓库 Release 附件）](https://github.com/maiga512/shuxiamusic-release/releases/tag/fnos-fnmusic-ext-v2.6.50) · [项目源码](https://github.com/maiga512/fnos_music_ext) |

> 版本说明：表中「当前版本」随发布更新；安卓版应用内更新读取本仓库**最新 Release**，
> Mac 版读取本仓库固定标签 **desktop-latest**，两者互不干扰。

## 飞牛在线听歌插件（fnmusic-ext）

> **来源说明**：本插件基于开源作者 [@javycoder](https://github.com/javycoder) 的 [fnos_music_ext（飞牛音乐扩展）](https://github.com/javycoder/fnos_music_ext) 改编，上游项目版权归原作者所有；
> 本版本在其基础上增加了与树夏Music 同步服务器的多端同步等能力。

- 只接管飞牛官方后端的通信入口，不修改官方程序、nginx 配置与数据库，可随时还原官方直连
- 在官方搜索框输入歌名即聚合在线音源，即点即播，自动补滚动歌词与高清封面；本地曲库优先
- 管理 WebUI（仅本机 8774）：音源切换、网易扫码、洛雪源配置、多端同步、音质偏好、边听边存
- 安装：飞牛桌面「应用中心」→ 自定义安装 → 选择本仓库 Release 里的 `fnmusic-ext-x.x.x.fpk`
- 上游原作者项目：[github.com/javycoder/fnos_music_ext](https://github.com/javycoder/fnos_music_ext) · [gitee.com/javycoder/fnos_music_ext](https://gitee.com/javycoder/fnos_music_ext) · 作者 GitHub 主页：[github.com/javycoder](https://github.com/javycoder)

## 树夏Music 同步服务器

- 自部署在 NAS（Docker + SQLite），默认端口 `31231`，含 Web 管理页
- 安卓 / Mac / 飞牛插件的「多端同步」功能都通过它交换歌单、收藏与播放记忆
- 部署步骤见[仓库 README](https://github.com/maiga512/CeruMusic-NAS-Sync)：`docker compose up -d --build` 后在 `http://NAS地址:31231` 管理

---

## 安卓版（历史段落保留）

### 软件界面截图

![树夏music 软件界面截图](screenshots/product/current-pad-dark-music.png)

![树夏music 软件界面截图](screenshots/product/current-pad-dark-podcast.png)

![树夏music 软件界面截图](screenshots/product/current-pad-dark-player.png)

### 最低运行配置

| 项目 | 要求 |
| --- | --- |
| Android 系统 | Android 8.0 / API 26 及以上 |
| 处理器 | `armeabi-v7a` 或 `arm64-v8a` 的 Android 车机 / 平板 |
| 内存 | 2 GB RAM 及以上 |
| 屏幕 | 建议 1280 × 720 及以上的横向屏幕 |
| 网络 | 需要可用网络 |
| 可用存储 | 至少预留 1 GB；下载歌曲时需额外预留媒体文件空间 |

### 推荐体验配置

| 项目 | 建议 |
| --- | --- |
| Android 系统 | Android 10 / API 29 及以上 |
| 处理器 | 64 位 `arm64-v8a` |
| 内存 | 4 GB RAM 及以上 |
| 屏幕 | 1280 × 720、1920 × 720 或更高分辨率横向屏幕 |

> Android 8.0 是项目的实际最低系统版本；其余项目为对外推荐配置。
