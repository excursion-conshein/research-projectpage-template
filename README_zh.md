# Excursion ConsHein 研究项目展示页 (ECRP)

[English Version](README.md) | 中文版

本教程将指导您如何创建一个专业的研究项目展示页面，采用模块化设计，易于维护和扩展。

**免责声明：本项目模板仅用于研究和学习目的，不涉及任何商业用途。**

**本项目中所引用的内容出自卡耐基梅隆大学 AirLab 在 IROS 2025 的最新研究展示。**

**本项目不针对其研究内容，仅作为页面的教程案例，不代表任何研究机构的立场或观点。**

**如果对该研究项目感兴趣，欢迎浏览项目主页：[pipe-planner.github.io](https://pipe-planner.github.io)**

## 项目概述

ECRP 模板采用纯HTML/CSS/JavaScript开发，具有以下特点：
- **模块化设计**：每个功能模块独立开发，便于维护
- **响应式布局**：支持桌面端和移动端自适应
- **配置驱动**：通过JSON配置文件管理内容，无需修改代码
- **现代化UI**：简洁美观的界面设计

## 项目结构

```
research-project-template/
├── configs/              # 配置文件目录
│   ├── signboard.json    # 顶部标志栏配置
│   ├── info.json         # 项目基本信息配置
│   └── main.json         # 主要内容配置
├── images/               # 图片资源目录
│   ├── signboard/        # 标志图片目录
│   ├── main/             # 主要内容图片目录
│   ├── video/            # 视频文件目录
│   └── favicon/          # 网页图标目录
├── src/                  # 源代码目录
│   ├── font.css          # 字体样式文件
│   ├── signboard.js      # 顶部标志栏模块
│   ├── info-button.js    # 信息按钮模块
│   ├── authors.js        # 作者信息模块
│   ├── info.js           # 项目信息模块
│   ├── main.js           # 主要内容模块
│   ├── mobile.js         # 移动端适配模块
│   └── copyright.js      # 页脚版权模块
├── font/                 # 字体资源目录
│   ├── Excursion.ttf     # Excursion 字体文件
│   ├── Nunito.ttf        # Nunito 字体文件
│   ├── Oxanium.ttf       # Oxanium 字体文件
│   └── Poppins.ttf       # Poppins 字体文件
└── index.html            # 主页面文件
```

## 快速开始

### 1. 环境准备

您只需要一个现代的Web浏览器和本地Web服务器。可以使用以下方式启动本地服务器：

```bash
# 使用Python内置服务器
python -m http.server 8000

# 或使用Node.js的http-server
npx http-server -p 8000
```

### 2. Fork项目模板

Fork是GitHub中复制他人仓库到您自己账户下的操作，这样可以基于现有模板进行修改而不会影响原项目。

#### 2.1 Fork步骤

1. **访问项目仓库**
   - 打开浏览器，访问项目模板的GitHub仓库页面
   - 点击页面右上角的 **Fork** 按钮

2. **选择目标账户**
   - 如果您有多个GitHub账户或组织，选择要将项目Fork到的目标账户
   - 通常选择您的个人账户即可

3. **等待Fork完成**
   - 系统会自动将整个项目复制到您的账户下
   - 完成后您会看到与原项目相同的仓库，但在您的账户下

#### 2.2 克隆到本地

Fork完成后，需要将仓库克隆到本地进行修改：

```bash
# 克隆您的Fork仓库（替换YOUR_USERNAME为您的GitHub用户名）
git clone https://github.com/YOUR_USERNAME/research-project-template.git

# 进入项目目录
cd research-project-template
```

#### 2.3 配置远程仓库

为了保持与原项目的同步，建议添加上游仓库：

```bash
# 添加上游仓库（原项目仓库）
git remote add upstream https://github.com/original-author/research-project-template.git

# 查看远程仓库配置
git remote -v
```

### 3. 配置GitHub Pages

#### 3.1 个性化配置

在配置GitHub Pages之前，先进行个性化配置：

1. **修改配置文件**
   - 编辑 `configs/` 目录下的JSON配置文件
   - 替换为您自己的项目信息、作者信息等

2. **替换图片资源**
   - 替换 `images/` 目录下的图片为您自己的项目图片
   - 保持文件名结构以便配置文件正确引用

3. **测试本地效果**
   ```bash
   # 启动本地服务器测试
   python -m http.server 8000
   
   # 在浏览器中访问 http://localhost:8000
   ```

#### 3.2 提交和推送更改

完成配置后，将更改推送到您的GitHub仓库：

```bash
# 添加所有更改到暂存区
git add .

# 提交更改
git commit -m "个性化项目配置"

# 推送到您的GitHub仓库
git push origin main
```

#### 3.3 启用GitHub Pages

现在配置GitHub Pages来托管您的项目页面：

1. **进入仓库设置**
   - 在您的GitHub仓库页面，点击 **Settings** 选项卡
   - 在左侧菜单中找到 **Pages** 部分

2. **配置发布源**
   - 在 **Source** 部分，选择 **Deploy from a branch**
   - 选择 **main** 分支（或您的默认分支）
   - 选择 **/(root)** 文件夹

3. **启用GitHub Pages**
   - 点击 **Save** 按钮
   - 系统会开始构建您的页面

4. **访问您的页面**
   - 构建完成后，页面顶部会显示您的站点URL
   - 格式通常为：`https://YOUR_USERNAME.github.io/research-project-template`
   - 点击链接访问您的项目展示页面

#### 3.4 自定义域名（可选）

如果您想使用自定义域名，可以按照以下步骤配置：

1. **在仓库设置中配置域名**
   - 在GitHub Pages设置页面，找到 **Custom domain** 部分
   - 输入您的自定义域名（如：`www.your-domain.com`）
   - 点击 **Save**

2. **配置DNS解析**
   - 登录您的域名提供商管理后台
   - 添加DNS记录指向GitHub Pages服务器：
     - 记录类型：`CNAME`
     - 主机记录：`www`（或`@`表示根域名）
     - 记录值：`YOUR_USERNAME.github.io`

3. **启用HTTPS**
   - 在GitHub Pages设置中，勾选 **Enforce HTTPS**
   - 等待证书生效（通常需要几分钟到几小时）

### 4. 基础配置

#### 4.1 顶部标志栏配置

编辑 `configs/signboard.json` 文件：

```json
{
    // 实验室和学院的 logo 文件需要保存在 image/signboard/ 目录下
    "lab": {
        "logoSrc": "实验室 logo 文件名",
        "url": "实验室网址"
    },
    "college": {
        "logoSrc": "学院 logo 文件名",
        "url": "学院网址"
    }
}
```

#### 4.2 项目信息配置

编辑 `configs/info.json` 文件：

```json
{
    "top-title": "您的项目标题",
    "conference": "会议名称和年份",
    "institution": {
        "1": "机构1",
        "2": "机构2",
        // 可以添加更多机构
    },
    "authors": {
        "作者姓名": {
            "homepage": "作者主页",
            "affiliation": "1",    // 与上方的institution中的 key 对应
            "equal_or_not": true   // 如果没有相同贡献，就删去此行，在页面中的 Equal Contributions 将不会显示
        }
    },
    "info-button": {
        // 说明一下，如果以下信息有什么是没有的，就删去对应的行，相应的按钮也会隐藏
        "arxiv": "论文的 arXiv 链接",
        "code": "项目的代码仓库链接",
        "video": "项目的视频链接",
        "demo": "项目的演示链接",
        "related_research":{
            "相关研究1": "相关研究1的链接",
            "相关研究2": "相关研究2的链接",
            // 可以添加更多相关研究
        }
    }
}
```

#### 4.3 主要内容配置

编辑 `configs/main.json` 文件，

本文档中支持多种内容模块堆叠拼接，因此可以尽情发挥您的创作能力，组合出符合您项目需求的展示页面。

json中的每个对象都对应着一个模块，模块的类型由对象中的 key 确定。大括号对应着一个容器，容器之间通过白色/浅灰色交替展现。每个容器中可以包含多个模块。

本模板严格按照 json 中的顺序进行展示，真正做到所想即所得。

每个模块的配置项都有其特定的含义，下面是支持的每个模块的详细配置项：

- 视频模块，包括视频文件路径（videoSrc、videoLink 等）、视频描述（description）
- 图文模块，包括图片路径（image）、标题（title）、内容描述（content）
- BibTeX引用模块，包括引用内容（bibtex）
- 按钮交互模块，通过 button 触发，然后依次添加按钮(button_{数字})，每个按钮包括按钮名称（button_name），以及上述其他所有模块的配置项

注意，如果具有多项类型相同的模块，则可以通过{模块}_{数字}的方式区分彼此，防止冲突。

目前支持多模块的类型有： description、image、title、content、button_{数字}

下面是简单的一个示例。

```json
[
    {
        "videoSrc": "视频文件名/链接，支持本地视频和在线视频，且宽度为 1000px",
        // 本地视频需存放在 images/video/ 目录下，videoLink也是一样
        "description": "项目简介描述，宽度跟随上面的 videoSrc",
        "title": "Abstract",
        "content": "项目详细内容..."
    },
    {
        "videoLink": "视频文件名/链接，支持本地视频和在线视频，且宽度为 800px",
        "description": "项目简介描述，宽度跟随上面的 videoLink",
    },
    {
        "title": "模块标题",
        "image": "图片文件名，支持本地图片，且宽度为 800px",
        // 本地图片需存放在 images/main/ 目录下
        "content": "模块内容描述..."
    },
    // 不同的模块是可以按照不同的方式堆叠的，没有谁必须在上面或者谁必须在下面，根据自己的安排来堆叠即可
    // 例如，我想做一个图文模块，先写标题，再展示图文，然后紧跟标题，和下一段图文模块……
    {
        "title_1": "模块标题1",
        "image_1": "图片1",
        "content_1": "模块内容1",
        "title_2": "模块标题2",
        "image_2": "图片2",
        "content_2": "模块内容2",
    },

    // 接着是按钮模块，需要先创建 button 容器，然后再依次添加按钮，例如……
    {
        "title": "结果展示",
        "button": {
            "button_1": {
                "button_name": "按钮名称",
                "image": "图片文件名，支持本地图片，且宽度为 800px"
            },
            "button_2": {
                "button_name": "按钮名称",
                "content": "内容"
            },
            "button_3": {
                "button_name": "按钮名称",
                "image": "图片",
                "content": "内容"
            }
        }
    },
    // 至于按钮能不能嵌套按钮？
    // 不好意思，作者没想好，不过我觉得这只是一个展示页面，没必要这么复杂吧

    // 最后是引用模块，引用模块建议在最后，因为引用模块的高度是固定的，不能根据内容自适应高度
    {
        "bibtex": "@article{example,
            title={Example Article},
            author={Author, A. and Another, B.},
            journal={Example Journal},
            year={2023},
            volume={1},
            number={1},
            pages={1-10}
        }"
    }

]
```

#### 4.4 网页图标配置

将网页图标文件（如 favicon.ico）放入 `images/favicon/` 目录下。

在 `index.html` 中引入图标：

```html
<link rel="icon" href="images/favicon/favicon.ico" type="image/x-icon">
```


### 5. 模块详解

#### 5.1 顶部标志栏模块 (signboard.js)

- **功能**：显示实验室和机构的标志
- **特点**：固定在页面顶部，响应式设计
- **配置**：通过 `signboard.json` 配置标志图片和链接

#### 5.2 信息按钮模块 (info-button.js)

- **功能**：显示论文相关的链接按钮
- **支持的按钮类型**：arXiv、代码库、视频、演示等
- **样式**：统一的按钮样式，悬停效果

#### 5.3 作者信息模块 (authors.js)

- **功能**：显示项目作者信息
- **特点**：支持作者主页链接、机构标识、同等贡献标记
- **布局**：响应式网格布局

#### 5.4 项目信息模块 (info.js)

- **功能**：显示项目标题、会议信息等
- **特点**：大标题显示，支持副标题
- **样式**：现代化的字体和颜色设计

#### 5.5 主要内容模块 (main.js)

- **功能**：显示项目的主要内容
- **支持的内容类型**：
  - 视频模块
  - 图文模块
  - 按钮交互模块
  - BibTeX引用模块
- **布局**：模块化堆叠，自适应宽度

#### 5.6 移动端适配模块 (mobile.js)

- **功能**：提供移动端的响应式适配
- **适配内容**：
  - 标志栏垂直堆叠
  - 字体大小调整
  - 容器高度自适应
  - 触摸友好的交互

#### 5.7 页脚版权模块 (copyright.js)

- **功能**：显示页脚版权信息
- **特点**：支持自定义链接和样式
- **内容**：版权声明和项目链接

### 6. 自定义样式

#### 6.1 字体配置

在 `index.html` 中可以配置Google Fonts：

```html
<link href="https://fonts.googleapis.com/css2?family=Google+Sans&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@400;500;700&display=swap" rel="stylesheet">
```
当然也可以自定义字体，只需要在 `font/` 目录下放入字体文件，然后在 `src/font.css` 中引入即可，例如：

```css
@font-face {
    font-family: 'Excursion';
    src: url('font/Excursion.ttf') format('truetype');
}
```

目前支持的自定义字体有：
- Excursion
- Nunito
- Oxanium
- Poppins

#### 6.2 颜色主题

每个模块都有独立的CSS样式，可以通过修改相应的JavaScript文件中的样式字符串来自定义颜色主题。

#### 6.3 响应式断点

移动端适配使用以下断点：
- **768px以下**：平板和手机设备
- **480px以下**：小屏手机设备

### 7. 部署指南

#### 7.1 静态部署

1. 将所有文件上传到Web服务器
2. 确保图片路径正确
3. 配置正确的MIME类型

#### 7.2 GitHub Pages维护

如果您已经按照前面的快速开始指南配置了GitHub Pages，这里有一些维护相关的信息：

##### 7.2.1 保持与原项目同步

如果原项目模板有更新，您可以将这些更新合并到您的Fork中：

```bash
# 获取上游仓库的最新更改
git fetch upstream

# 切换到您的本地主分支
git checkout main

# 合并上游仓库的更改
git merge upstream/main

# 推送更新到您的GitHub仓库
git push origin main
```

##### 7.2.2 故障排除

**常见问题及解决方案：**

1. **GitHub Pages构建失败**
   - 检查文件路径是否正确
   - 确保没有语法错误（特别是JSON配置文件）
   - 查看仓库的Actions页面了解详细错误信息

2. **样式不显示**
   - 确保所有文件都已正确推送
   - 检查文件路径大小写（GitHub Pages区分大小写）
   - 清除浏览器缓存后重试

3. **自定义域名不生效**
   - 检查DNS配置是否正确
   - 等待DNS传播完成（通常需要24-48小时）
   - 确认域名解析到了正确的GitHub服务器

#### 7.3 其他部署方式

除了GitHub Pages，您还可以选择其他部署方式：

##### 7.3.1 静态服务器部署

1. 将所有文件上传到任何支持静态文件的Web服务器
2. 确保图片路径正确
3. 配置正确的MIME类型

##### 7.3.2 其他托管平台

- **Netlify**：支持拖拽部署，自动HTTPS
- **Vercel**：优秀的性能和边缘网络
- **GitLab Pages**：类似GitHub Pages的GitLab解决方案

### 8. 最佳实践

#### 8.1 图片优化

- 使用WebP格式减少文件大小
- 压缩图片以提高加载速度
- 为不同设备提供不同分辨率的图片

#### 8.2 性能优化

- 压缩JavaScript和CSS文件
- 使用CDN加速字体和静态资源
- 启用浏览器缓存

#### 8.3 内容组织

- 保持配置文件的结构清晰
- 使用有意义的文件命名
- 定期备份重要文件

### 9. 故障排除

#### 9.1 常见问题

**Q: 页面样式不显示**
A: 检查CSS样式是否正确加载，确保JavaScript文件路径正确

**Q: 图片无法显示**
A: 检查图片路径是否正确，确保图片文件存在

**Q: 移动端显示异常**
A: 检查viewport设置，确保移动端适配模块正确加载

#### 9.2 调试技巧

- 使用浏览器开发者工具检查元素
- 查看控制台错误信息
- 逐步加载模块进行测试

### 10. 扩展功能

#### 10.1 添加新模块

1. 在 `src/` 目录创建新的JavaScript文件
2. 在 `index.html` 中添加模块引用
3. 根据需要创建对应的配置文件

#### 10.2 多语言支持

可以通过创建多套配置文件来实现多语言支持，根据用户语言偏好加载不同的配置。

#### 10.3 主题切换

可以添加主题切换功能，让用户在明暗主题之间切换。

## 总结

本教程提供了一个完整的研究项目展示页面制作指南。通过模块化设计和配置驱动的方式，您可以轻松创建专业的研究项目展示页面。模板具有良好的可扩展性和维护性，适合各种学术研究项目的展示需求。

如果你在使用过程中遇到问题，可以通过以下方式联系我们：
- Email: Conshein_Yuanxing@outlook.com
- GitHub: [Excursion-ConsHein](https://github.com/Excursion-ConsHein)

祝您可以创建属于自己心仪的研究项目展示页面！
