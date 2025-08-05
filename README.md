# Notion-Blog

一个基于 Next.js + Notion API 的静态博客系统（ NotionNext ），支持多种主题和部署方案。

## 项目结构

```
Notion-Blog/
├── blog.config.js                 # 博客主配置文件
├── components/                     # 全局组件
│   ├── ui/                        # UI组件库
│   │   └── dashboard/             # 仪表板组件
│   ├── Ackee.js                   # 分析组件
│   ├── AdBlockDetect.js           # 广告拦截检测
│   ├── AISummary.js               # AI摘要组件
│   └── ...                        # 其他全局组件
├── conf/                          # 配置文件目录
│   ├── ad.config.js               # 广告配置
│   ├── ai.config.js               # AI配置
│   ├── analytics.config.js        # 分析配置
│   └── ...                        # 其他配置文件
├── hooks/                         # 自定义React Hooks
│   ├── useAdjustStyle.js          # 样式调整Hook
│   └── useWindowSize.ts           # 窗口尺寸Hook
├── lib/                           # 核心库文件
│   ├── cache/                     # 缓存管理
│   │   ├── cache_manager.js       # 缓存管理器
│   │   ├── local_file_cache.js    # 本地文件缓存
│   │   └── memory_cache.js        # 内存缓存
│   ├── config.js                  # 核心配置
│   ├── db/                        # 数据库相关
│   │   └── getSiteData.js         # 获取站点数据
│   ├── font.js                    # 字体配置
│   ├── global.js                  # 全局配置
│   ├── lang/                      # 多语言支持
│   │   ├── en-US.js              # 英文
│   │   ├── fr-FR.js              # 法文
│   │   ├── ja-JP.js              # 日文
│   │   └── ...                    # 其他语言
│   ├── notion/                    # Notion API相关
│   │   ├── convertInnerUrl.js     # 内部URL转换
│   │   ├── CustomNotionApi.ts     # 自定义Notion API
│   │   ├── getAllCategories.js    # 获取所有分类
│   │   └── ...                    # 其他Notion相关功能
│   ├── plugins/                   # 插件系统
│   │   ├── aiSummary.js           # AI摘要插件
│   │   ├── algolia.js             # Algolia搜索插件
│   │   ├── busuanzi.js            # 不蒜子统计插件
│   │   └── ...                    # 其他插件
│   └── utils/                     # 工具函数
│       ├── formatDate.js          # 日期格式化
│       ├── index.js               # 工具函数入口
│       ├── pageId.js              # 页面ID处理
│       └── ...                    # 其他工具函数
├── pages/                         # Next.js页面
│   ├── _app.js                    # 应用入口
│   ├── _document.js               # 文档模板
│   ├── api/                       # API路由
│   │   ├── auth/                  # 认证相关API
│   │   ├── cache.js               # 缓存API
│   │   ├── subscribe.js           # 订阅API
│   │   └── user.ts                # 用户API
│   ├── archive/                   # 归档页面
│   ├── auth/                      # 认证页面
│   ├── category/                  # 分类页面
│   ├── dashboard/                 # 仪表板页面
│   ├── page/                      # 文章页面
│   ├── search/                    # 搜索页面
│   ├── sign-in/                   # 登录页面
│   ├── sign-up/                   # 注册页面
│   └── tag/                       # 标签页面
├── public/                        # 静态资源
│   ├── css/                       # 样式文件
│   ├── images/                    # 图片资源
│   │   ├── heo/                   # Heo主题图片
│   │   ├── starter/               # Starter主题图片
│   │   └── themes-preview/        # 主题预览图片
│   ├── js/                        # JavaScript文件
│   ├── svg/                       # SVG图标
│   ├── videos/                    # 视频文件
│   └── webfonts/                  # 网页字体
├── styles/                        # 全局样式
│   ├── globals.css                # 全局样式
│   ├── notion.css                 # Notion样式
│   └── prism-theme.css            # 代码高亮主题
└── themes/                        # 主题系统
    ├── commerce/                  # 商务主题
    ├── example/                   # 示例主题
    ├── fukasawa/                  # Fukasawa主题
    ├── game/                      # 游戏主题
    ├── gitbook/                   # GitBook主题
    ├── heo/                       # Heo主题
    ├── hexo/                      # Hexo主题
    ├── landing/                   # 落地页主题
    ├── magzine/                   # 杂志主题
    ├── matery/                    # Matery主题
    ├── medium/                    # Medium主题
    ├── movie/                     # 电影主题
    ├── nav/                       # 导航主题
    ├── next/                      # Next主题
    ├── nobelium/                  # Nobelium主题
    ├── photo/                     # 照片主题
    ├── plog/                      # Plog主题
    ├── proxio/                    # Proxio主题
    ├── simple/                    # 简约主题
    ├── starter/                   # 启动主题
    ├── typography/                # 排版主题
    └── theme.js                   # 主题配置
```

## 核心功能

### 1. 多主题支持
项目内置20+种精美主题，包括：
- **Next**: 现代化设计风格
- **Medium**: 简洁阅读体验
- **Hexo**: 传统博客风格
- **Fukasawa**: 日式简约风格
- **Heo**: 个性化主题
- **Commerce**: 商务风格
- **Game**: 游戏化界面
- **GitBook**: 文档风格
- **Landing**: 落地页风格
- **Magazine**: 杂志风格
- **Movie**: 电影风格
- **Photo**: 摄影风格
- **Typography**: 排版风格
- **Simple**: 极简风格
- **Starter**: 启动模板

### 2. 插件系统
- **AI摘要**: 自动生成文章摘要
- **Algolia搜索**: 强大的搜索功能
- **不蒜子统计**: 访问量统计
- **评论系统**: 支持多种评论插件
- **广告系统**: 广告位管理

### 3. 多语言支持
- 中文 (zh-CN)
- 英文 (en-US)
- 法文 (fr-FR)
- 日文 (ja-JP)
- 韩文 (ko-KR)
- 俄文 (ru-RU)
- 土耳其文 (tr-TR)

### 4. 缓存系统
- **内存缓存**: 快速访问
- **本地文件缓存**: 持久化存储
- **缓存管理器**: 统一缓存控制

### 5. Notion集成
- **API集成**: 与Notion API深度集成
- **内容转换**: 自动转换Notion内容格式
- **分类管理**: 自动获取和管理分类
- **内部链接**: 智能处理内部链接

## 技术栈

- **框架**: Next.js
- **样式**: Tailwind CSS
- **渲染**: React-notion-x
- **评论**: Twikoo, Giscus, Gitalk, Cusdis, Utterances
- **图标**: Fontawesome
- **部署**: Vercel, Netlify, 自托管

# 原 NotionNext 项目链接
https://github.com/tangly1024/NotionNext