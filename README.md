# 项目作品集 · 杨千钎

一个纯静态的个人项目作品集，包含 4 个项目：

| 项目 | 形式 | 入口 |
|---|---|---|
| TAAC 2026 | 案例 + GitHub + 讲解视频 | `index.html#taac` |
| AFAC 2026 | 案例 + GitHub | `index.html#afac` |
| 百度 BMO 黑客松 | 案例 + 3 张产品截图 + GitHub | `index.html#bmo` |
| 秋招辅助 | 虚构示例数据的交互 Demo | `tracker-demo.html` |
| 演示版 | 16:9 翻页演示，支持键盘方向键 | `deck.html` |

---

## 本地预览

直接双击 `index.html` 可以看，但用本地服务器更接近线上环境：

```bash
cd "03_竞赛项目/项目展示"
python3 -m http.server 8000
```

然后打开：

- 作品集：http://localhost:8000/
- 演示版：http://localhost:8000/deck.html
- 秋招辅助 Demo：http://localhost:8000/tracker-demo.html

---

## 部署到 GitHub Pages

### 1. 在 GitHub 新建一个空仓库

建议仓库名：

- `portfolio` → 线上地址 `https://<用户名>.github.io/portfolio/`
- 或 `<用户名>.github.io` → 线上地址 `https://<用户名>.github.io/`

创建时不要勾选 README、.gitignore 或 license，保持空仓库。

### 2. 推送本地文件

```bash
cd "03_竞赛项目/项目展示"
git init
git add .
git commit -m "Add project portfolio"
git branch -M main
git remote add origin https://github.com/<用户名>/<仓库名>.git
git push -u origin main
```

### 3. 打开 Pages

GitHub 仓库 → **Settings** → **Pages** → **Build and deployment**

- Source：`Deploy from a branch`
- Branch：`main`
- Folder：`/ (root)`
- 点击 **Save**

等 1–2 分钟，打开 Pages 页面显示的地址。

### 4. 检查线上版本

- 首页四个项目都能滚动到
- TAAC / AFAC / BMO 的 GitHub 链接能打开
- 秋招辅助 Demo 的四个标签页能切换
- 手机宽度下没有横向滚动条

---

## 文件说明

```text
项目展示/
├── index.html                 # 作品集主页
├── deck.html                  # 16:9 翻页演示版
├── tracker-demo.html          # 秋招辅助静态 Demo（虚构数据）
├── README.md
├── .nojekyll                  # 让 GitHub Pages 跳过 Jekyll 处理
└── assets/
    └── bmo/                   # BMO 产品截图（3 张）
        ├── bmo-01.jpg
        ├── bmo-02.jpg
        └── bmo-03.jpg
```

`index.html` 和 `tracker-demo.html` 都是自包含的 HTML/CSS/JS，没有 CDN、没有后端依赖；图片是本地相对路径。

---

## 内容边界

- **TAAC / AFAC / BMO**：使用公开 GitHub 仓库和本人材料里的数据；团队项目中已标出个人分工。
- **AFAC 分数**：页面写的是 Qwen-only 合规设置下的内部验证峰值 70.91，并明确说明 76.45 不作为成绩展示。
- **秋招辅助 Demo**：只用虚构公司名和示例分数，不连接 SQLite、不调用 DeepSeek、不需要 API key。
- **BMO 截图**：截图里的成员姓名已做模糊处理；未打码原图放在部署目录外的 `_原始截图暂不发布/`。
- **不发布**：真实 `backend/app.db`、`backend/.env`、`_凭证勿外传` 以及任何真实投递记录都不要上传。

---

## 以后怎么改

- 换项目文案：直接改 `index.html` 里对应的 `<article class="project">`。
- 换 BMO 截图：替换 `assets/bmo/` 下图片，保持文件名不变即可。
- 改 Demo 示例数据：编辑 `tracker-demo.html` 里的 `jobs` 数组。

---

## 更新记录

- 2026-10：建立作品集，加入 4 个项目、BMO 截图和秋招辅助交互 Demo。
