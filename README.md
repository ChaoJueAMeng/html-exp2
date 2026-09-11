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

**改 HTML 之后不会自动上线**，除非已经把 GitHub 接到 Cloudflare。临时 `wrangler deploy --temporary` 只是一次性发布，和 Git 没有关系。

### 推荐：在 Cloudflare 里连接这个 GitHub 仓库

连上之后，向 `main` 推送就会自动构建并部署：

1. 打开 [Workers 和 Pages](https://dash.cloudflare.com/?to=/:account/workers-and-pages)
2. 选中 Worker `html-exp2`（没有就先 **导入仓库** 创建，名称必须和 `wrangler.jsonc` 里的 `html-exp2` 一致）
3. **设置 → Builds → Connect**，授权 GitHub，选择仓库 `ChaoJueAMeng/html-exp2`
4. 生产分支填 `main`，部署命令用 `npx wrangler deploy`
5. 保存后再往 `main` 推一次，就会自动更新线上页面

也可以走 GitHub Actions：把 `CLOUDFLARE_API_TOKEN`、`CLOUDFLARE_ACCOUNT_ID` 加到仓库 Secrets，合并本仓库的 `deploy.yml` 后，推送 `main` 同样会自动部署。

如果浏览器报 `ERR_SSL_VERSION_OR_CIPHER_MISMATCH`（不受支持的协议），说明这个 `workers.dev` 子域还没有签出 HTTPS 证书。`workers.dev` 已加入 HSTS 预加载，手机和电脑都会强制走 HTTPS，证书缺失时页面就打不开。换一个已签发证书的子域重新部署即可。

### 本地手动部署

```bash
npx wrangler login
npm run deploy
```
