# 古老的占卜术

占卜类学习与成果文章的发布站。Markdown 写作，GitHub Pages 自动渲染为网页。

线上地址：<https://13734795725zhao-rgb.github.io/ancient-divination/>

---

## 写一篇新文章

1. 在 `_posts/` 下新建文件，命名规则 **必须**是 `年-月-日-英文短名.md`，例如：
   `2026-11-20-tarot-major-arcana.md`
   > 文件名只用小写字母、数字和连字符，不要用中文——中文文件名会让网址变成一长串乱码。

2. 文件开头写 front matter（三条横线之间）：

   ```yaml
   ---
   title: 塔罗大阿卡纳的二十二个原型
   date: 2026-11-20
   summary: 一句话摘要，会显示在首页列表标题下方。
   ---
   ```

   - `title` 会显示为文章标题和页面标题
   - `summary` 可省略；省略时首页自动截取正文前 72 字

3. 正文从第四条 `---` 之后开始写，正常使用 Markdown 语法（标题、列表、引用、表格、代码块都支持）。

4. 提交：

   ```bash
   git add .
   git commit -m "新文章：塔罗大阿卡纳"
   git push
   ```

5. 等 1–2 分钟，GitHub 自动构建，首页列表会自动出现新条目，无需手动改任何链接。

---

## 可用的 Markdown 元素

| 语法 | 效果 |
| --- | --- |
| `## 二级标题` | 小节标题 |
| `> 引用` | 楷体引文块，左侧朱砂细线 |
| `**加粗**` | 强调 |
| `- 列表` / `1. 列表` | 无序 / 有序列表 |
| `[文字](网址)` | 链接，带下划线动效 |
| `` `代码` `` | 行内代码 |
| 表格 | 三线表，自动对齐 |

Markdown 正文无需加 HTML。若确需插图，把图片放进 `assets/img/`，然后写：

```markdown
![图片说明](/ancient-divination/assets/img/your-image.png)
```

> 注意路径前缀 `/ancient-divination` 是仓库名，换仓库名时要一起改。

---

## 目录结构

```
.
├── _config.yml          # 站点配置：标题、副标题、仓库地址
├── index.md             # 首页「缘起」段落的正文，直接改这里的文字
├── _layouts/
│   ├── default.html     # 全站骨架：报头、页脚、纸纹
│   ├── home.html        # 首页：首屏 + 缘起 + 文章列表
│   └── post.html        # 文章页模板
├── _posts/              # 所有文章放这里
└── assets/
    ├── css/style.css    # 全部样式，配色与字体在文件顶部的 :root 里
    └── img/             # 配图
```

## 改样式

- 配色、字体、版心宽度：`assets/css/style.css` 顶部的 `:root` 变量
- 站点名称、副标题、仓库链接：`_config.yml`
- 首页介绍文字：`index.md`
- 首页首屏那句导语：`_layouts/home.html` 里的 `.hero__dek`

## 本地预览（可选）

需要 Ruby 环境：

```bash
gem install bundler jekyll
jekyll serve --baseurl ""
```

然后访问 <http://localhost:4000>。不装也行，直接 push 看线上效果。

## 发布设置

仓库 **Settings → Pages → Build and deployment**：

- Source 选 `Deploy from a branch`
- Branch 选 `main`，目录选 `/ (root)`
- 保存后等待首次构建完成

---

*示例文章 `_posts/2026-11-13-kai-pian.md` 可直接删除或替换为自己的开篇。*
