# AGENTS.md

本仓库是《Web前端开发技术》实验2 的纯静态 HTML 项目，无需构建、无第三方依赖。

## 项目结构

| 文件 | 说明 |
| --- | --- |
| `index.html` | 首页，包含两个实验页面的导航链接 |
| `exp_2_1.html` | 实验 2.1：3 号标题「天下兴亡，匹夫有责」、红色分隔线、350px 图片 |
| `exp_2_2.html` | 实验 2.2：标题「天安门」、背景色 `#FFFFEE`、红色分隔线、512px 图片 |
| `image-ex-2-1-tianxia.jpg` | 实验 2.1 配图 |
| `image-ex-2-2-tiananmen.jpg` | 实验 2.2 配图 |

## 本地运行

在项目根目录启动静态服务器：

```bash
python3 -m http.server 45217
```

然后访问 http://127.0.0.1:45217/ 查看页面。也可以用浏览器直接打开各 `.html` 文件。

## 提交前必改

把 `exp_2_1.html` 与 `exp_2_2.html` 末尾的学号、姓名占位符改成自己的：

```html
<p class="sign">学号：__________　姓名：__________</p>
```

## Cursor Cloud specific instructions

- 环境配置由仓库内的 `.cursor/environment.json`（repository-managed）提供，随分支/代码走，无需 `install` 步骤。
- 该配置在 `terminals` 中以 `python3 -m http.server 45217` 启动静态服务器，并暴露端口 `45217`。
- 验证环境是否可用的方法：
  - 命令行检查各资源返回 `200`：
    ```bash
    for p in "" index.html exp_2_1.html exp_2_2.html \
             image-ex-2-1-tianxia.jpg image-ex-2-2-tiananmen.jpg; do
      curl -s -o /dev/null -w "%{http_code} /$p\n" "http://127.0.0.1:45217/$p"
    done
    ```
  - 涉及页面/样式改动时，用浏览器访问上述地址，确认中文文本正常显示、两张图片正常加载（无破损图标）后再收尾。
