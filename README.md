# Omarchy Anime Themes 动漫主题包

为 [Omarchy](https://omarchy.org/)（Arch + Hyprland 发行版）打造的热门动漫 IP 主题，
全部 4K 壁纸，透明状态栏实测可读。持续扩充中，欢迎 PR 你喜欢的 IP。

![themes](docs/preview-grid.png)

> 姊妹仓库：[omarchy-genshin-themes](https://github.com/jasper-nan/omarchy-genshin-themes)（原神主题包，11 角色）

## 主题一览

| 主题 | IP | 模式 | 主配色 |
|---|---|---|---|
| `attack-on-titan` | 进击的巨人 | 深色 | 深橄榄墨绿 + 自由之翼绿 + 血色/墙岩金 |
| `detective-conan` | 名侦探柯南 | 深色 | 午夜藏青 + 柯南蓝 + 领结红/侦探金 |
| `demon-slayer` | 鬼灭之刃 | 深色 | 市松墨绿 + 日之呼吸火焰 + 羽织绿 |

每个主题包含：

- `colors.toml` — 完整调色板（18 语义色 + 4 层背景），顶部有设计思路注释
- `icons.theme` — 配套 Yaru 图标色
- `backgrounds/` — 4 张 3840×2160 壁纸（社区主图 + 2 备选 + 纯渐变），
  `omarchy theme bg next` 循环切换

## 安装

```bash
git clone https://github.com/jasper-nan/omarchy-anime-themes.git
cd omarchy-anime-themes
./install.sh                 # 复制到 ~/.config/omarchy/themes/

omarchy theme list           # 确认出现
omarchy theme set "Demon Slayer"
```

> 也可以只复制单个主题：`cp -r themes/demon-slayer ~/.config/omarchy/themes/`

## 透明栏可读性

每张壁纸顶部叠有 260px 的主题底色渐变暗带（底部 150px）。即使
`shell.json` 里 `"transparent": true`（文字直接压壁纸），Omarchy 的
`omarchy-bar-text-color` 采样也永远命中深色区。全库壁纸实测对比度
14.2:1 ~ 15.2:1（WCAG AAA 标准 7:1）。

## 改配色 / 重制壁纸

1. 编辑 `themes/<slug>/colors.toml`（各键含义见文件内注释）
2. 已有 4K 原图放 `themes/<slug>/src/wallpaper.img`，运行
   `bin/compose-wallpapers.sh themes/<slug> <slug> direct` 重制
3. `omarchy theme set <主题名>` 重新应用

## 致谢与版权声明

- 配色、脚本以 [MIT](LICENSE) 开源
- 壁纸素材来自 Wallhaven 社区分享，版权属于原作者与对应 IP 权利方
  （谏山创/讲谈社、青山刚昌/小学馆、吾峠呼世晴/集英社等）。
  本项目为非商业粉丝作品，与任何权利方无关联。若权利方要求，将立即下架相关素材。
