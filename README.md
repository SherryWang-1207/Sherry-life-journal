# 她的生活 🌸

一个专为 Sherry 打造的个人生活记录 Web 应用，支持运动打卡、美食记录、亲子出游、育儿心得、亲子对话，以及**一键生成小红书风格图片**。

---

## ✨ 功能特性

| 板块 | 功能 |
|------|------|
| 💪 运动 | 跳操每日打卡、步数记录、跑步公里、GitHub 热力图、连续天数 |
| 🍳 美食 | 记录菜名/日期/描述/图片，双列卡片流展示 |
| 🗺️ 出游 | 地点/日期/感受/图片，时间轴展示 |
| 📚 育儿 | 来源/标题/心得，归档卡片 |
| 💬 对话 | 孩子的话+感受，对话气泡样式 |
| ✨ 自定义 | 右上角 ＋ 可新增任意标签 |
| 📷 一键成图 | 每条记录可生成适合发小红书的竖版图片（1080×1440）|

---

## 🚀 部署步骤

### 1. Fork / 创建仓库

在 GitHub 创建仓库 `Sherry-life-journal`（Public），将本项目所有文件推送进去。

```bash
cd sherry-life-journal
git init
git remote add origin https://github.com/SherryWang-1207/Sherry-life-journal.git
git add .
git commit -m "🌸 初始化她的生活"
git push -u origin main
```

### 2. 开启 GitHub Pages

进入仓库 → Settings → Pages → Source 选 **Deploy from a branch** → Branch: `main` / `/ (root)` → Save

稍等 1-2 分钟，访问：
`https://sherrywang-1207.github.io/Sherry-life-journal/`

---

## 🔑 获取 GitHub PAT（Personal Access Token）

数据读取无需 Token（公开仓库），**写入数据**需要 Token：

1. 登录 GitHub → 右上角头像 → **Settings**
2. 左侧底部 → **Developer settings**
3. **Personal access tokens** → **Tokens (classic)**
4. **Generate new token (classic)**
5. 勾选权限：**`repo`**（完整仓库访问）
6. 设置过期时间（建议 1 year）
7. 点击 **Generate token** 并复制

> ⚠️ Token 只显示一次，请立即复制！

---

## ⚙️ 首次配置

1. 打开应用，点击右上角 **⚙️ 设置**
2. 点击 **修改** Token，粘贴刚才复制的 PAT
3. 保存后即可正常使用所有写入功能

Token 仅存储在本机 `localStorage`，不会上传到任何服务器。

---

## 📷 一键成图使用方法

- 运动板块：点击统计区域右侧的 **📷 生成打卡图** 按钮
- 其他板块：每条记录卡片底部有 **📷 生成图片** 按钮
- 点击后出现预览弹窗，移动端长按图片可保存到相册，或点击 **⬇️ 下载图片**

---

## 📁 数据文件

所有数据存储在仓库 `data/` 目录：

| 文件 | 内容 |
|------|------|
| `data/exercise.json` | 运动数据（2025-01-01 起每日记录） |
| `data/food.json` | 美食记录 |
| `data/travel.json` | 出游记录 |
| `data/parenting.json` | 育儿心得 |
| `data/conversation.json` | 亲子对话 |
| `data/custom.json` | 自定义标签和记录 |

---

## 🛠️ 技术栈

- 纯静态 HTML + CSS + JS（无框架、无构建工具）
- 数据存储：GitHub API（读公开 API，写需 PAT）
- 图片生成：原生 Canvas API
- PWA：manifest.json，可添加到手机主屏幕
- 离线降级：读取失败时使用 localStorage 缓存

---

Made with ❤️ for Sherry · 她的生活，一点一滴都值得记录 🌸
