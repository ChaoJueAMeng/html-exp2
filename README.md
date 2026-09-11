# 实验2：格式化文本与图像

按《Web前端开发技术》实验要求完成的两个静态页面。

## 文件说明

| 文件 | 内容 |
| --- | --- |
| `exp_2_1.html` | 3 号标题「天下兴亡，匹夫有责」，红色分隔线，图片宽 350px |
| `exp_2_2.html` | 页面标题「天安门」，背景色 `#FFFFEE`，h2 居中，红色分隔线，图片宽 512px |
| `image-ex-2-1-tianxia.jpg` | 实验 2.1 配图 |
| `image-ex-2-2-tiananmen.jpg` | 实验 2.2 配图 |

两个页面都在 `<head>` 中插入了实验要求的样式：段落 24px、首行缩进 2em、正文左对齐，页面内容水平居中。

## 提交前必改

把两个 HTML 文件末尾的学号、姓名改成自己的：

```html
<p class="sign">学号：__________　姓名：__________</p>
```

## 本地打开

用浏览器直接打开 `exp_2_1.html` / `exp_2_2.html` 即可。也可以在本目录启动本地服务：

```bash
python3 -m http.server 45217
```

然后访问 http://127.0.0.1:45217/

本地预览 Cloudflare 部署效果：

```bash
npm install
npm run dev
```

## 部署到 Cloudflare（免费 `workers.dev` 域名）

Cloudflare 不提供免费的 `.com` 之类注册域名，但每个账号都有免费的 `*.workers.dev` 子域名。本仓库用 Workers 静态资源托管，部署后地址形如：

`https://html-exp2.<你的子域>.workers.dev`

### 第一次部署（无需事先注册）

未登录时可用临时账号立刻上线，命令会打印 **站点 URL** 和 **认领链接**（认领链接相当于所有权凭证，60 分钟内有效，不要发到公开仓库或群聊）：

```bash
npx wrangler deploy --temporary
```

打开认领链接，登录或注册 Cloudflare，即可把临时账号和这个站点收成自己的永久账号。

### 已有 Cloudflare 账号

1. 在 [Cloudflare Dashboard](https://dash.cloudflare.com/) 创建 API Token（权限包含 `Workers Scripts Edit` 和 `Account Settings Read`）
2. 把 Token 和 Account ID 配到环境变量，或写入 GitHub Secrets：`CLOUDFLARE_API_TOKEN`、`CLOUDFLARE_ACCOUNT_ID`
3. 部署：

```bash
npx wrangler login
npm run deploy
```

`main` 分支推送后，`.github/workflows/deploy.yml` 也会自动部署。
