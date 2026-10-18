# JavRanking PopClip Extension

[![PopClip](https://img.shields.io/badge/PopClip-Extension-blue?logo=apple&style=flat-square)](https://www.popclip.app)
[![macOS](https://img.shields.io/badge/macOS-11.0%2B-black?style=flat-square)](https://www.apple.com/macos/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![JavRanking](https://img.shields.io/badge/Site-JavRanking.cc-orange?style=flat-square)](https://javranking.cc)

[JavRanking](https://javranking.cc) 官方 PopClip 划词搜索扩展。在 macOS 任何地方用鼠标选中文本（番号、影星、片商、关键词），一键直达 JavRanking 搜索结果页。

---

## ✨ 核心特性

- ⚡️ **划词即搜**：选中文本后点击 JavRanking 按钮，立即跳转 `https://javranking.cc/zh-hans/search/?q=xxxx`。
- 🎯 **智能清洗**：自动剔除首尾空白、换行符与制表符（`cleanQuery`），防止特殊空格破坏搜索。
- ⌥ **Option 键精准搜索**：按住键盘 `⌥ Option` 键点击扩展，PopClip 会自动用双引号包裹关键词，进行精准全字匹配。
- 🌐 **双语支持**：默认进入简体中文搜索，在 PopClip 偏好设置中可随时切换为英文（`en`）版。
- 🎨 **品牌矢量自适应图标**：基于 JavRanking 官方标志性「**J + 冲榜向上箭头 ↑**」手工绘制的精密 SVG 矢量，原生适配 macOS 深色模式（纯白）与浅色模式（暗灰）。

---

## 🚀 极速安装

### 方法一：选中文本一键安装（PopClip Snippet - 最推荐 ⭐️）

> **仅需 1 秒**：请直接使用鼠标**划选完整包裹**下方代码块，PopClip 会在屏幕上方自动弹出「安装扩展 JavRanking」弹窗，点击即可完成安装！

```yaml
#popclip
name: JavRanking
icon: svg:<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g fill="currentColor"><path d="M9.1 5.8h3.25v9.8a4.5 4.5 0 0 1-9 0v-1.1h3.2v1.1a1.3 1.3 0 0 0 2.55 0V5.8z"/><path d="M17.1 3.2l3.7 5.4h-2.4v11.6h-2.6V8.6h-2.4z"/></g></svg>
url: https://javranking.cc/{popclip option locale}/search/?q=***
cleanQuery: true
options:
  - identifier: locale
    label: Language / 语言版本
    type: multiple
    defaultValue: zh-hans
    values:
      - zh-hans
      - en
    valueLabels:
      - 简体中文
      - English
```

*(如果只需纯粹的固定中文搜索，也可划选下面这个极简版 snippet 安装：)*

```yaml
#popclip
name: JavRanking
icon: svg:<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g fill="currentColor"><path d="M9.1 5.8h3.25v9.8a4.5 4.5 0 0 1-9 0v-1.1h3.2v1.1a1.3 1.3 0 0 0 2.55 0V5.8z"/><path d="M17.1 3.2l3.7 5.4h-2.4v11.6h-2.6V8.6h-2.4z"/></g></svg>
url: https://javranking.cc/zh-hans/search/?q=***
cleanQuery: true
```

---

### 方法二：下载打包文件双击安装（`.popclipextz`）

1. 在本项目 Releases 或根目录下载 [**`JavRanking.popclipextz`**](JavRanking.popclipextz)。
2. 在 Mac Finder 中双击下载好的 `.popclipextz` 文件。
3. PopClip 会弹出确认安装对话框，点击确认即可安装完毕。

---

### 方法三：开发者源码安装（`.popclipext`）

1. 克隆本项目：
   ```bash
   git clone https://github.com/javranking/javranking-popclip-extension.git
   ```
2. 在 Finder 中打开目录，双击其中的 `JavRanking.popclipext` 文件夹，PopClip 会直接加载安装。

---

## 🎨 图标设计与官方生态考量

在设计本扩展时，我们深度研读了 PopClip 官方最新的 [Icons 开发规范](https://www.popclip.app/dev/icons.md)。

### 1. 为什么选择自制 SVG 图标？复不复杂？

* **完全不复杂，且体验是最好的**：
  PopClip 允许直接在扩展中引用本地 `icon.svg` / `icon.png`，甚至在 Snippet 代码片段中直接嵌入内联 `svg:<svg>...</svg>`。
* **品牌辨识度极高**：
  JavRanking 拥有辨识度鲜明的品牌视觉——**加粗的大写字母 J** 与 **冲榜向上箭头 ↑**（象征品质进阶与排行榜首位）。
* **原生视觉契约**：
  采用 `fill="currentColor"` 单色遮罩绘制，无论用户系统处于 macOS **Dark Mode**（自动呈现纯白高亮）还是 **Light Mode**（自动呈现深灰微弱反光），都能达到与系统自带剪切、拷贝、放大镜完全一致的原生触感。

### 2. 其他官方备选图标参考

如果你希望在本地二次定制换用其他风格，可以直接修改 `icon` 字段：

| 图标标识符 | 来源体系 | 视觉效果与语义 |
| :--- | :--- | :--- |
| `icon.svg` 或 `svg:<svg...` *(当前采用)* | **JavRanking 官方定制** | 经典 J↑ 品牌标志，原生自适应黑白主题 |
| `preserve-color file:icon-color.png` | **JavRanking 彩色包** | 品牌原色（白 J + 橙色发光箭头 `#FF7A00`） |
| `iconify:fluent:video-search-24-regular` | **Iconify 库** | 胶卷/视频窗口 + 放大镜搜索组合 |
| `symbol:film.stack` | **macOS SF Symbols** | 堆叠电影胶卷，macOS 原生多媒体质感 |
| `square filled JR` | **PopClip 文本修饰符** | 实心方块背景嵌入字母「JR」 |

---

## 🔒 官方目录（PopClip Directory）提审说明

根据 PopClip 官方 [Submission Agreement](https://www.popclip.app/extensions/submit#submission-agreement) 的明确条款：

> **Some content is off limits.**  
> *Extensions relating to gambling, **adult content** or illegal file sharing will not be published.*  
> （与博彩、**成人内容**或非法文件共享相关的扩展将**不会被发布**至官方目录。）

因此，本扩展**无需且无法**提交至官方 Extensions Directory。PopClip 客户端本身是完全开放的本地生产力工具，用户通过上述任意一种本地/代码片段方式安装，均可享受到完整的体验。

---

## 📄 许可证

本项目基于 [MIT 许可证](LICENSE) 开源。欢迎 Star 与 Fork！
