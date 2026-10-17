# 桪言 · Nan-Muxun

一个像 Word 一样写作的 Markdown 编辑器，采用柔和的墨绿色界面，支持可视化编辑、Markdown 源码切换以及 PDF / Markdown 导出。

[打开在线网站](https://moyan-markdown-nanmu.silver-kid-1458.chatgpt.site/)

## 功能

- 多文档本地草稿，支持自动保存、重命名、删除和恢复最近删除的文档。
- 正文与标题样式、字体、文字颜色、对齐、列表、引用和分隔线。
- 插入表格、代码块与本地照片；照片支持等比例缩放、对齐和移动。
- 导入 Markdown，切换可视化编辑与源码编辑。
- 导出 `.md` 和不附加网址、日期等页眉页脚的 PDF。

## 本地运行

这是一个纯静态项目，无需安装 npm 依赖，也无需构建。使用 Python 3 启动：

```sh
git clone https://github.com/Nanmuxxx/Nan-Muxun.git
cd Nan-Muxun
python3 -m http.server 8000 --directory dist
```

然后打开 <http://localhost:8000>。

## 项目结构

```text
dist/
  index.html       页面结构与工具栏
  style.css        界面、编辑区与打印排版样式
  app.js           编辑、草稿、导入和导出逻辑
  vendor/          随项目提供的第三方浏览器库
.openai/
  hosting.json     原有 Sites 托管配置
```

部署到静态网站托管服务时，将 `dist/` 设置为网站根目录。

## 数据与导出说明

- 草稿保存在当前浏览器的 localStorage 中，不会上传到 GitHub，也不会在不同设备、浏览器或域名之间自动同步。重要文档请及时导出备份。
- 照片会压缩后嵌入文档；浏览器本地存储容量有限。
- PDF 通过 html2pdf.js 生成，当前为图像形式，正文不可直接选择或搜索。
- Markdown 中的字体、颜色、对齐和图片尺寸等样式使用 HTML 保留，显示效果取决于阅读器对 HTML 的支持。

## 第三方依赖

`dist/vendor/` 包含 marked、Turndown、DOMPurify 和 html2pdf.js，保留其文件中的原始版权说明。各依赖适用各自的许可证。
