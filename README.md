# 叙述 — 个人博客

读书写作主题的个人博客，纯静态 HTML，支持 Markdown 渲染、标签分类、夜间模式。

## 在线访问

- CloudStudio 预览：https://dfb0a1c77bd8419fb6b882ea5bc6a124.app.codebuddy.work
- GitHub Pages（配置后）：https://你的用户名.github.io/仓库名/

## 部署到 GitHub Pages

### 1. 创建仓库

去 [github.com](https://github.com) 新建仓库，名字随意（比如 `blog`）。

### 2. 上传文件

把这个 `github-deploy` 文件夹里的所有内容上传到仓库根目录：

```
仓库根目录/
├── docs/
│   └── index.html        ← 博客主文件
└── .github/
    └── workflows/
        └── deploy-pages.yml  ← 自动部署脚本
```

### 3. 开启 Pages

仓库 Settings → Pages → Source 选 **GitHub Actions** → 保存。

### 4. 等待上线

推送代码后 1-2 分钟，GitHub Actions 会自动部署。部署完成后在 Settings → Pages 能看到网址。

### 5. 以后更新文章

改 `docs/index.html` 里的 `POSTS` 数组，push 上去自动更新。

## 自定义域名（可选）

在 `docs/` 目录创建 `CNAME` 文件，写入你的域名，然后在域名服务商添加 CNAME 记录指向 `你的用户名.github.io`。

## 本地预览

```bash
cd docs
python -m http.server 3000
# 浏览器打开 http://localhost:3000
```
