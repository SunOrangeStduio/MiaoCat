# Miao Study Game

这是从 `Design/html-game-v5` 整理出的独立静态发布副本，目标环境为 GitHub Pages 和现代手机浏览器。

## 发布根目录

```text
miao-study-game/
├─ index.html
├─ game.css
├─ game.js
└─ sprites/
```

GitHub Pages 应选择 `main` 分支的 `/(root)`。`index.html` 必须保持在仓库根目录。

## 整理原则

- 原始 `Design/html-game-v5` 不修改。
- HTML、CSS、JavaScript 和被运行代码引用的素材保留。
- 不复制 Unity 工程文件、C# 工具、临时文件、概念图、废弃角色和处理中间素材。
- 素材目录保持原相对路径与文件名大小写。

## 已完成静态检查

- HTML、CSS、JS 入口文件存在。
- 48 条明确静态素材路径存在且大小写一致。
- 21 个动态布置对象素材存在。
- 12 个商店图标存在。
- 4 个邮件奖励素材存在。
- 国内与日本相册素材存在。
- HTML 共 126 个 ID，无重复。
- JavaScript 直接查询的 DOM ID 均存在；`mealTable` 是允许缺失的可选节点。
- 没有外部网络请求、绝对网站路径、`file://` 依赖或 ES Module 依赖。
- 没有混入 `.cs`、`.csproj`、`.ps1`、`tmp/`、`tools/` 或源素材 `assets/`。

## 仍需浏览器验证

- 首次进入、任务、专注计时、商店、旅行、邮件、相册和布置流程。
- 页面刷新后的 `localStorage` 存档。
- Android 浏览器的 JSON 存档下载与文件导入。
- 添加到主屏幕后安全区域、横竖屏和返回键行为。
- 图片首次加载速度与移动网络流量。

## 注意

当前副本是普通静态网站，并未添加 Service Worker。浏览器清除网站数据会同时清除 `localStorage` 存档；断网离线启动也尚未保证。

## 降低公开发现概率

- 仓库使用不明显、不可猜测的名称。
- 不分享 GitHub Pages 地址。
- 不添加 GitHub Topics。
- 不发布 GitHub Release。
- 不在个人主页置顶仓库。
- `index.html` 已加入 `noindex / nofollow / noarchive / nosnippet / noimageindex`。
- `robots.txt` 已禁止普通搜索引擎抓取全部路径。

这些措施只用于降低被搜索引擎和普通访客发现的概率，不构成访问控制。公开仓库、提交历史和 GitHub Pages 地址仍可被知道准确链接的人访问。
