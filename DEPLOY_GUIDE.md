# GitHub Pages 部署指南

## 📁 当前文件结构

```
cost-calculator-site/
├── index.html      ← 计算器主页（GitHub Pages 入口）
├── README.md       ← 仓库说明
├── .nojekyll       ← 告诉 GitHub 不用 Jekyll 处理
└── DEPLOY_GUIDE.md ← 本文档（部署后可删除）
```

---

## 🚀 一步步操作

### 第一步：配置 Git 用户信息（如果还没配过）

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱@example.com"
```

### 第二步：在 GitHub 上创建仓库

1. 打开 https://github.com/new
2. Repository name 填：`cost-calculator`（或你喜欢的名字）
3. 选择 **Public**（免费账号 GitHub Pages 需要公开仓库）
   - 如果需要私有仓库，需要 GitHub Pro（$4/月）
4. **不要**勾选 "Add a README file"
5. 点击 **Create repository**

### 第三步：推送代码

创建仓库后，GitHub 会显示推送命令。在终端中执行：

```bash
cd /Users/june/Desktop/workbuddy/cost-calculator-site

# 提交代码
git add -A
git commit -m "初始版本：国际异动成本计算器"

# 关联远程仓库（把 YOUR_USERNAME 替换为你的 GitHub 用户名）
git remote add origin https://github.com/YOUR_USERNAME/cost-calculator.git

# 推送
git push -u origin main
```

> 💡 如果提示输入密码，GitHub 现在需要用 **Personal Access Token** 代替密码。
> 获取方式：GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token → 勾选 `repo` 权限。

### 第四步：开启 GitHub Pages

1. 打开你的仓库页面：`https://github.com/YOUR_USERNAME/cost-calculator`
2. 点击 **Settings**（齿轮图标）
3. 左侧菜单找到 **Pages**
4. Source 选择 **Deploy from a branch**
5. Branch 选择 **main**，文件夹选择 **/ (root)**
6. 点击 **Save**

### 第五步：访问你的在线计算器 🎉

等待 1-2 分钟后，访问：

```
https://YOUR_USERNAME.github.io/cost-calculator/
```

把这个链接分享给同事即可！

---

## 🔄 后续更新流程

每次你修改了计算器，只需要：

```bash
# 1. 把最新的 HTML 复制过来
cp /Users/june/Desktop/workbuddy/国际异动成本计算器.html /Users/june/Desktop/workbuddy/cost-calculator-site/index.html

# 2. 提交并推送
cd /Users/june/Desktop/workbuddy/cost-calculator-site
git add -A
git commit -m "更新：简要说明改了什么"
git push
```

推送后 1-2 分钟，所有人刷新页面就能看到最新版本。

---

## ❓ 常见问题

**Q: 能不能用私有仓库？**
A: 可以，但需要 GitHub Pro 账号（$4/月）才能在私有仓库上使用 GitHub Pages。

**Q: 国内访问慢怎么办？**
A: GitHub Pages 在国内可能不太快。可以考虑：
- 用 Cloudflare Pages 代替（免费，国内更快）
- 或者用 Gitee Pages（国内平台）

**Q: 怎么绑定自定义域名？**
A: Settings → Pages → Custom domain，填入你的域名，然后在域名 DNS 添加 CNAME 记录指向 `YOUR_USERNAME.github.io`。
