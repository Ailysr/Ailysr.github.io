# Blog 图片管理指南

## 📁 文件夹结构

```
blog/
├── images/                    # 存放所有博客图片
│   ├── aircraft-structure-analysis.jpg
│   ├── historical-vs-modern.png
│   ├── fea-stress-analysis.gif
│   └── ...
├── files/                     # 存放下载文件
│   ├── sample-ansys-models.zip
│   ├── matlab-scripts.zip
│   └── ...
├── 2025-01-05-article.md      # Markdown 源文件
└── 2025-01-05-article.html    # HTML 发布文件
```

## 🖼️ 图片使用方法

### 1. 在 Markdown 中引用图片

```markdown
# 基本语法
![替代文字](images/图片文件名.jpg)

# 带标题的图片
![Aircraft Analysis](images/aircraft-analysis.jpg)
*图1: 飞机结构分析示例*

# 指定尺寸（需要 HTML）
<img src="images/diagram.png" alt="示意图" width="500">
```

### 2. 支持的图片格式

- **JPG/JPEG**: 照片，复杂图像
- **PNG**: 图表，截图，透明背景
- **GIF**: 动画演示
- **SVG**: 矢量图，图表
- **WebP**: 现代格式，更小文件

### 3. 图片命名规范

```
# 推荐命名格式
文章日期-描述性名称.扩展名

# 示例
2025-01-05-evtol-structure.jpg
2025-01-10-safety-flowchart.png
2025-01-15-ansys-screenshot.png
```

## 📊 图片优化建议

### 文件大小控制
- **照片**: 压缩到 200KB 以下
- **截图**: PNG 格式，1MB 以下
- **图表**: SVG 优先，PNG 备选

### 分辨率建议
- **宽度**: 最大 800px（博客内容区域）
- **高度**: 根据内容调整
- **DPI**: 网页用 72-96 DPI

## 🛠️ 图片处理工具

### 在线工具
- **TinyPNG**: 压缩 PNG/JPG
- **Squoosh**: Google 的图片优化工具
- **Canva**: 制作图表和设计

### 桌面软件
- **GIMP**: 免费图像编辑
- **Paint.NET**: Windows 轻量级编辑器
- **Photoshop**: 专业图像处理

## 🔗 Markdown 转 HTML 工具

### 推荐工具

1. **Pandoc** (命令行)
```bash
pandoc article.md -o article.html --standalone
```

2. **Typora** (所见即所得编辑器)
   - 直接导出为 HTML
   - 支持数学公式和图表

3. **VS Code + 插件**
   - Markdown Preview Enhanced
   - 可以直接导出 HTML

4. **在线转换器**
   - StackEdit
   - Dillinger

## 📝 工作流程建议

### 方案一：Markdown 优先
1. 用 Markdown 写作
2. 添加图片引用
3. 用工具转换为 HTML
4. 手动调整 HTML 样式（如果需要）
5. 更新 blog.html 中的文章列表

### 方案二：混合方式
1. 用 Markdown 写主要内容
2. 复杂布局部分用 HTML
3. 图片用相对路径引用
4. 保持两个版本同步

## 🎨 图片在 HTML 中的高级用法

```html
<!-- 响应式图片 -->
<img src="images/diagram.jpg" 
     alt="结构图" 
     style="max-width: 100%; height: auto;">

<!-- 图片说明 -->
<figure>
  <img src="images/analysis.jpg" alt="分析结果">
  <figcaption>图1: 有限元分析结果</figcaption>
</figure>

<!-- 图片画廊 -->
<div class="image-gallery">
  <img src="images/img1.jpg" alt="图片1">
  <img src="images/img2.jpg" alt="图片2">
</div>
```

## 💡 最佳实践

1. **始终提供替代文字**：对屏幕阅读器友好
2. **使用描述性文件名**：便于管理和SEO
3. **优化图片大小**：提高页面加载速度
4. **版权注意**：使用自己的图片或确保有使用权限
5. **备份重要图片**：定期备份到云端或其他位置

## 🚀 推荐的完整工作流

1. **写作**：用 Markdown 编写文章
2. **图片**：创建/收集图片，放入 `images/` 文件夹
3. **预览**：用 Typora 或 VS Code 预览效果
4. **转换**：用 Pandoc 或其他工具转换为 HTML
5. **发布**：上传文件到 GitHub，更新博客索引
