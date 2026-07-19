# 摄影展 · Photography Exhibition

单文件摄影作品展网站，可直接部署到 GitHub Pages。

## 预览

用浏览器打开 `index.html` 即可本地预览。

## 部署到 GitHub Pages

### 方法一：命令行

```bash
cd ~/Desktop/photo-exhibition

# 初始化 git
git init
git add index.html README.md
git commit -m "Initial commit: photography exhibition"

# 创建 GitHub 仓库后（替换成你的用户名和仓库名）
git remote add origin https://github.com/你的用户名/你的仓库名.git
git branch -M main
git push -u origin main
```

然后去 GitHub 仓库 → Settings → Pages → Branch 选 `main` → Save。

### 方法二：GitHub 网页直接上传

1. 在 GitHub 新建仓库，仓库名随意（比如 `photo-exhibition`）
2. 把 `index.html` 和 `README.md` 直接拖进 GitHub 网页
3. Settings → Pages → Branch 选 `main` → Save

几分钟后访问 `https://你的用户名.github.io/仓库名/` 即可。

## 替换成自己的照片

编辑 `index.html`，找到 `<script>` 标签里的 `PHOTOS` 数组，把 `seed` 值换成自己图片的路径：

```javascript
// 原来（占位图）
{ seed: 'mountain-dawn', cat: '自然呼吸', title: '晨光 · 山脉' }

// 换成你自己的照片
{ src: 'photos/mountain.jpg', cat: '自然呼吸', title: '晨光 · 山脉' }
```

然后把 `<img>` 标签里的 `CDN(p.seed, ...)` 改成 `p.src`。

## 文件结构

```
photo-exhibition/
├── index.html    # 唯一需要的文件（CSS/JS 全部内联）
└── README.md
```

## 依赖

- Google Fonts（Inter + JetBrains Mono）
- picsum.photos（占位图，替换后不需要）
