<div align="center">

# Echora

**与念真聊天的小站。** 原本挂在博客下面的 `chat/`，2026-11 搬出来独立成一个仓库。

<p>
  <a href="https://yen-chiu.github.io/Echora/"><img src="https://img.shields.io/badge/Live-Echora-6366f1?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Live" /></a>
  <a href="https://yenchiu.com"><img src="https://img.shields.io/badge/Blog-yenchiu.com-a855f7?style=for-the-badge&logo=jekyll&logoColor=white" alt="Blog" /></a>
  <img src="https://img.shields.io/badge/Vue-2.x-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white" alt="Vue" />
  <img src="https://img.shields.io/badge/build-none-22c3aa?style=flat-square" alt="No build" />
  <img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square" alt="MIT" />
</p>

</div>

线上地址：<https://yen-chiu.github.io/Echora/>

## 现在有什么

打开任意一页，右上角的四个方块按钮会拉出一个「手机桌面」式的抽屉。抽屉是**念真的小站**：她住在这里，每一格都是她的一间屋子。

| 模块 | 地址 | 是什么 |
| --- | --- | --- |
| 与念真聊天 | `/` | 脚本化对话，她按 `assets/dialog.json` 里的剧本回你 |
| 念真 · AI | `/ai.html` | 填自己的 API Key，接任何 OpenAI 兼容接口；带人格、流式输出、本地工具与联网搜索 |
| 三个夜晚 | `/stories.html` | 三幕对话故事的入口（`/story.html`、`/story-s2.html`、`/story-s3.html`），按「幕」分站 |
| 异次元通讯 | `/play.html?a=miko` | 搬进来的网页版：原版与「次元复苏」的剧情、词条、图鉴、动态 |
| 生命线 | `/play.html?a=lifeline` | 搬进来的网页版：和坠毁在陌生星球的泰勒用消息保持联系 |
| 凌晨两点十七分 | `/game.html` | 一个即时通讯式的短篇剧情，25 个节点、4 个结局，约 12 分钟 |
| 致谢 | `/credits.html` | 这个小站站着的开源项目，以及各自帮了什么忙 |

抽屉里的图标有两种来源：有现成画的（念真、两个网页版游戏）就用 `img/apps/` 里的图片，没有合适图片的模块回落到 `js/shell.js` 里那套内联 SVG 字形。要给某个模块换图，在 `APPS` 的对应项里加一个 `icon: 'img/apps/xxx.webp'` 即可，字形会自动让位。

这些模块共用一套设计令牌（`css/shell.css`），支持浅色 / 深色 / 跟随系统，抽屉里可以切换；背景还有「自动 / 闲 / 萤火」三档氛围。

## 目录

```
index.html / ai.html / stories.html / story*.html / play.html / game.html / credits.html
css/        main.min.css、enhance、shell、ambient
js/         shell.js（壳层与抽屉）、index-min.js（聊天）、enhance、ambient、sw-update
lib/        zepto、vue（无构建，直接引用）
apps/       miko-web、lifeline-web（两个网页版游戏的移植）
assets/     dialog.json、persona（念真的设定与素材）、stories
img/        头像、图标、贴纸、背景
skills/     写作与人格相关的资料
```

没有构建步骤：原生 HTML / CSS / JS，`lib/` 里的库直接引用，改完提交即可。

## 跑起来

因为全是相对路径，随便起个静态服务器就行：

```bash
python -m http.server 8788
# 或者 npx serve .
```

然后打开 <http://localhost:8788/>。直接双击 `index.html` 也行，只是少数脚本里的 fetch 会受 `file://` 限制。

## 从旧仓库搬过来

- 旧位置：`blog-v2/chat/`（站内路径 `/blog-v2/chat/`），以及快照仓库 `yen-chiu/Chat`。
- 本仓库现在是唯一的开发源头；旧位置保留一份旧版并冻结，页面顶部会挂一条「已迁移到 Echora」的横幅，名字仍叫 `chat` 以作区分。
- 旧地址 `yenchiu.com/chat/` 在 2026-11 迁到根域后没有一起搬，现在是 404；要看旧版请去 `/blog-v2/chat/`。

## 许可

- 代码：MIT（见 [LICENSE](LICENSE)）。
- 角色、对话剧本、图片与故事文本：原创内容，保留所有权利（见 [CONTENT-LICENSE.md](CONTENT-LICENSE.md)）。转载或二次使用请先问一声。
