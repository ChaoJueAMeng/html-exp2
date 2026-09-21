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

## 在线访问（GitHub Pages）

实验2 页面在子路径：

- 实验2 首页：https://chaojueameng.github.io/html-exp2/
- 实验 2.1：https://chaojueameng.github.io/html-exp2/exp_2_1.html
- 实验 2.2：https://chaojueameng.github.io/html-exp2/exp_2_2.html

https://chaojueameng.github.io/ 会跳转到萌实验室 https://chaojueameng.github.io/meng-lab/，不是本实验。静态文件托管在 [ChaoJueAMeng.github.io](https://github.com/ChaoJueAMeng/ChaoJueAMeng.github.io) 的 `html-exp2/` 目录。更新本仓库 `main` 后，可在该仓库 Actions 中手动运行 **Sync html-exp2**，或等待每日自动同步。

## 本地打开

用浏览器直接打开 `exp_2_1.html` / `exp_2_2.html` 即可。也可以在本目录启动本地服务：

```bash
python3 -m http.server 45217
```

然后访问 http://127.0.0.1:45217/
