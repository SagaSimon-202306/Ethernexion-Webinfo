# assets/ — 图片与二进制资源说明

## 现状

本仓库以**文本方式完整保存了全站所有图片与文件的 URL 清单**（共 344 个去重 URL，见 `data/image-urls.txt`），
但**图片二进制文件本体未能入库**，原因：

- 本次抓取所用沙箱环境的出站网络受白名单限制（仅 GitHub/PyPI/npm 等），
  对 `www.ethernexion.com`（含 `:8001` 媒体端口）的直接 TCP/TLS 连接被拦截（`curl` 返回 `SSL_ERROR_SYSCALL`）。
- 页面文本通过代理式抓取工具获取，故文字内容 100% 完整；图片只能记录 URL。
- 尝试用 GitHub Actions 在云端 runner 镜像站点，但当前 GitHub App 凭据缺少 `workflows` 权限，无法推送 workflow 文件。

## 如何补齐图片（任选其一）

1. **本地一键下载**（推荐，在无网络限制的机器上运行）：

   ```bash
   cd assets
   wget -x -nH --cut-dirs=0 -i ../data/image-urls.txt
   # 或保留主机名分目录：
   wget -x -i ../data/image-urls.txt
   ```

2. **GitHub Actions**：将下述内容存为 `.github/workflows/mirror-assets.yml`（需具备 workflow 写权限的账号推送），手动触发即可把图片提交进仓库：

   ```yaml
   name: Mirror assets
   on: workflow_dispatch
   permissions: { contents: write }
   jobs:
     mirror:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v4
         - run: |
             cd assets
             wget -x --tries=2 --timeout=20 -i ../data/image-urls.txt || true
         - run: |
             git config user.name bot && git config user.email bot@users.noreply.github.com
             git add -A assets && git commit -m "assets: site images" || true
             git push
   ```

## URL 规律

- 原图（webp/png 原始上传）：`https://www.ethernexion.com:8001/media/original_images/<name>.<ext>`
- 站内渲染图（Wagtail rendition）：`https://www.ethernexion.com/media/images/<name>.width-{200|640|1200}.png`
- 静态图标：`https://www.ethernexion.com/images/...`
- Next.js 优化器：`https://www.ethernexion.com/_next/image?url=<编码后的 8001 原图地址>&w=96&q=75`
- 产品资源 PDF：`https://www.ethernexion.com/api/product-resource-file?category_slug=switches&resource_id=<ID>&resource_scope=<scope>&product_slug=<slug>`（清单见 `data/resources.json`）
- 登录才能下载的文件（ENOS 手册、UniCloud 安装包）：见 `data/resources.json` 的 `login_gated_downloads`。
