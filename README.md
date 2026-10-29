# RCA-inspired Editorial UI Skill

把 RCA 官网的编辑式排版方法整理成可复用的 UI skill：不等宽五列网格、手机两列、Source Sans 3、黑白错位过渡、克制的强调色与留白。

这是独立的设计学习项目，**并非 RCA 官方设计系统，也不代表 RCA 的授权或背书**。原站观察日期为 2026-10-28；此版本在两个网站案例测试及用户反馈后于 2026-10-29 整理。

## 包含什么

- [正式 Skill](skills/rca-editorial-ui/SKILL.md)：给 Codex / 支持 `SKILL.md` 的助手使用。
- [实现规则](skills/rca-editorial-ui/references/implementation.md)：字体、网格、配色、三列图片、阶梯边界、动效和检查方法。
- [原站观察](skills/rca-editorial-ui/references/source-observations.md)：实测值和来源，区别于本项目的适配决定。
- [中文设计笔记](docs/design-notes.zh-CN.md)：这些布局如何工作，以及测试中形成的设计判断。
- [验证与适用范围](docs/validation.md)：已验证的行为与验证边界。

## 默认选择

| 项目 | 默认规则 |
|---|---|
| 桌面网格 | `16.74% / 22.173% / 22.173% / 22.173% / 16.74%` |
| 手机／窄屏 | 两列骨架，主文字与图片可跨两列 |
| 容器 | 最大 1440px，左右留白 20px / 60px |
| 字体 | Source Sans 3，主要字重 400 / 600 |
| 字号 | 选定角色后统一 ×0.9；原站值另表保留 |
| 普通横图 | 默认桌面三列，保留完整画面 |
| 配色 | 纯黑、纯白、中性灰；原版橙 `#ff5d1c` |
| 蓝色变体 | 只将强调色改为 `#0070f0`，不染色背景和灰色 |
| 转场 | 贴合网格的章节阶梯或有意义的媒体跨越 |
| 信息密度 | 一段一个主要意思，详情保持可达 |

这些是经过案例测试的默认选择，不是所有网站必须遵守的定律。用户具体内容和明确要求优先。

## 使用

下载本仓库，将整个 `skills/rca-editorial-ui/` 文件夹放入助手使用的 skills 目录，保留 `references/`。

Codex 的用户级目录通常是 `~/.codex/skills/`；设置了 `CODEX_HOME` 时使用其 `skills/` 子目录。如已有同名技能，先比较并备份自己的版本。本仓库本身不会自动安装或修改其他配置。

示例请求：

```text
使用 $rca-editorial-ui，把我提供的作品内容做成作品集。
保留纯黑白和原版橙色，普通横图占三列，手机两列，字号使用 0.9。
```

```text
使用 $rca-editorial-ui 重做这个动画项目网站。
只把橙色强调色改为 #0070f0，背景、文字灰度和图片原色保持不变。
保留制作资料，未完成的阶段如实标注。
```

```text
使用 $rca-editorial-ui 检查这页的排版：
重点看网格线与内容是否对齐、黑白过渡是否贴合网格、同屏信息是否太满。
这次只给修改建议，不改文件。
```

## 来源与发布范围

研究参考 [Royal College of Art 官网](https://www.rca.ac.uk/)，具体观察及来源链接见上述文档。字体来源为 [Adobe Source Sans](https://github.com/adobe-fonts/source-sans)，许可证见其 [OFL 文件](https://github.com/adobe-fonts/source-sans/blob/release/LICENSE.md)。

发布包包含原创整理的规则、解释和短实现示例，不包含 RCA 标志、照片、视频、整站源码、字体二进制文件，也不包含案例网站中的个人资料或项目素材。截图和源码快照未随包发布。

用途是独立 UI 学习与设计研究。本次发布未另行选择开源许可证；仓库公开状态不用于宣称第三方素材已获得再分发或商用授权。
