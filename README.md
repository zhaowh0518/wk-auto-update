
# wk-Auto-update

自动同步 BPB-Worker-Panel 项目的最新 worker.js 文件。

## 🚀 快速开始（适合 Fork）

1. 点击右上角 Fork 本仓库到你的 GitHub 账号。
2. 打开你的仓库，进入 Actions 页面，点击 Enable workflows（启用 GitHub Actions）。
3. 无需其他配置，GitHub 默认的 GITHUB_TOKEN 权限即可推送更新。
4. 你可以手动点击 Run workflow，也可以等待每天定时自动检查。

> 注意：确保你的仓库默认分支为 main，否则推送时可能失败。

🌟 如果觉得这个项目对你有帮助，欢迎顺手点个 Star 支持一下！

---

## 功能介绍

- 每天自动检查 bia-pain-bache/BPB-Worker-Panel 仓库的最新 Release
- 自动下载最新版本的 worker.js
- 重命名为 _worker.js
- 同步更新本地 version.txt
- 自动提交并推送到本仓库

## 工作流程

GitHub Actions 会每日 00:00（UTC 时间）自动运行：

1. 获取上游仓库的最新 Release 版本号
2. 比较本地 version.txt 的记录
3. 若版本不同，则自动下载并替换 _worker.js
4. 更新 version.txt
5. 自动提交并推送到主分支（main）

> 若版本一致，则不执行任何操作。

---

## 📂 目录结构

/
├── _worker.js         
├── version.txt        
├── LICENSE            
├── .gitignore         
├── README.md          
└── .github/
    └── workflows/
        └── update_worker.yml

---

## ⚙️ 配置说明

- 无需手动设置 Token：默认使用 GitHub 提供的 GITHUB_TOKEN 进行权限认证。
- 如需修改同步源：编辑 .github/workflows/update_worker.yml，修改源仓库地址即可。

---
##  创建项目：在cloudflare 后台- 左侧点击【pages】—【创建项目】

登录 Cloudflare 后台 → 左侧点击【Pages】→ 【创建项目】
选择 连接到 GitHub：
选择你的 Fork 仓库
允许 Cloudflare Pages 读取你的 GitHub 仓库权限
项目基本配置：
项目名字自己取，比如 cf-auto-update
分支选择 main

##  配置环境变量（Varidbles）
在 Pages 项目设置里：

- 打开 【设置 Settings】→ 【环境变量 Environment Variables】
- 添加这些变量：
- 名字	内容
- UUID	自己生成一个 UUID，比如去 https://1024tools.com/uuid
- TR_PASS	自己设一个密码
- FALLBACK	推荐设置成 example.com
⚡ 注意：
- 变量名字全大写！
- TR_PASS、FALLBACK 都是根据项目需求补充的。

##  配置KV 存储绑定
- Pages Functions 也可以使用 KV，
- 需要绑定 KV 存储桶。

步骤：
- Cloudflare 后台左侧【Workers & KV】→ 【KV 存储】
- 创建一个新的命名空间（比如叫 test）
- 回到 Pages 项目的【Settings → KV Bindings】
- 添加绑定：
- Binding Name	Namespace
- kv	你刚才创建的 test
✅ Binding Name 必须是 kv 小写，保持和代码对应！

##  访问面板
部署完成后：

访问你的 Pages 地址，比如：
https://your-project-name.pages.dev/panel
第一次访问，会让你设置后台管理密码
进入后台后，可以自由开关协议（Trojan、VLess 等），生成订阅链接

## 📜 开源协议

本项目使用 MIT License 开源。

您可以自由地使用、复制、修改和分发本项目，前提是附带原始许可证声明。

---

## 🌐 社区与交流

如果有任何问题或建议，欢迎加入我们的 Telegram 群组交流：

👉 加入 Telegram 群组：https://t.me/+ft-zI76oovgwNmRh


---

## 📢 特别说明

- 本仓库同步的内容来源于 [BPB-Worker-Panel](https://github.com/bia-pain-bache/BPB-Worker-Panel)。
- 原项目版权归原作者所有，本项目仅用于自动同步更新，不对原内容进行修改。

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=byJoey/wk-Auto-update&type=Timeline)](https://www.star-history.com/#byJoey/wk-Auto-update&Timeline)
