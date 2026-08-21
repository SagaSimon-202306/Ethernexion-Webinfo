# Ethernexion-Webinfo

**www.ethernexion.com 全站信息存档** · 抓取日期：2026-08-22 · 覆盖 sitemap 全部 116 个 URL

> 目标：把 EtherNexion 官网的所有文字、型号、规格、价格、图片地址、资源文件信息完整入库，供后续程序化调用。

## 目录结构

```
├── README.md                    ← 本文件
├── content/                     ← 页面全文（Markdown，逐字保存，含 YAML frontmatter：url/title/抓取日期）
│   ├── pages/                   ← 14 个静态页：首页、ENOS、UniCloud、SONiC、About、Support、
│   │                               Solutions、News 索引、Partners、Partner Apply、Community、
│   │                               Cloud、Privacy、Terms、Cookies、Site map、Downloads
│   ├── products/                ← 全部 72 个交换机 SKU 详情页（每 SKU 一个文件）
│   │   ├── _page-template-blocks.md    ← 全站产品页共用模板块（报价表单等，逐字存一次）
│   │   └── _series-*-compare.md        ← 各系列共用的 Compare models 对比表 / Highlights /
│   │                                      Software specs / Resources（S3700/S5100/S5200/
│   │                                      S5300/S5400/S7100/S7200，逐字存一次，避免 72 份重复）
│   ├── collections/             ← 集合页结构说明（其产品卡片数据已在 data/products.json）
│   ├── news/                    ← 全部 12 篇新闻/博客全文（含发布日期、封面图 URL）
│   └── solutions/               ← 3 个解决方案页全文（Campus / SMBs / Hyperscale & AI）
├── data/                        ← 结构化 JSON / 清单
│   ├── site-urls.json           ← sitemap.xml 全部 URL 分类清单（静态页/集合/产品/新闻/方案）
│   ├── products.json            ← 72 SKU 索引：URL、标题、SKU 编码、美元标价、系列、集合、图片 URL
│   ├── collections.json         ← 产品集合层级 + 系列分组（S2100…S9400）
│   ├── resources.json           ← 全部产品资源 PDF 元数据（resource_id/大小/SHA256 前缀/下载 URL 模板）
│   │                               + 需登录下载的文件清单（ENOS 手册、UniCloud 安装包）
│   ├── company-info.json        ← 公司信息：法人/地址/办公室/邮箱/电话/高管/平台/合作伙伴名录/技术栈线索
│   └── image-urls.txt           ← 全站 344 个去重图片与文件 URL（一行一个）
└── assets/
    └── README.md                ← 图片二进制未入库的原因 + 一条命令补齐的方法
```

## 覆盖范围

| 类别 | 数量 | 状态 |
|---|---|---|
| 静态页面（含法律页） | 17 | ✅ 全文逐字 |
| 产品详情页（交换机 SKU） | 72/72 | ✅ 全文（Highlights、全部规格表、软件特性、资源 PDF、系列对比、价格、SKU） |
| 产品集合/子集合页 | 20 | ✅ 结构+计数（卡片数据并入 products.json） |
| 新闻/博客文章 | 12/12 | ✅ 全文逐字 |
| 解决方案页 | 3/3 | ✅ 全文逐字 |
| 价格 & SKU 编码 | 72/72 | ✅ 全部收录（美元标价） |
| 图片/文件 URL | 344 | ✅ 清单收录（二进制见 assets/README.md 说明） |

## 快速调用示例

```python
import json
products = json.load(open('data/products.json'))['products']
# 找所有 PoE++ 90W 且价格 < $3000 的型号
for p in products:
    print(p['sku'], p['price_usd'], p['url'])
```

## 已知站点数据备注（抓取时原样保留）

- 站点存在少量原文拼写/数据问题（如 "Singpore"、"LightLlink"、"aieflow"、S5148G-4X2Q-EI 详情页 Key specs 下行口写作 2.5G/10G Base-T 等），本存档一律**按原文保留**并在对应文件标注。
- ENOS / Solutions 等页面部分按钮链接指向测试域 `test.hohunet.cn`（原样记录于 company-info.json）。
- `/downloads` 为客户端动态渲染页，静态抓取无正文；各产品资源清单已从产品页收录至 `data/resources.json`。
- `/products/gateway`、`/products/wifi` 为空目录（页面原文提示见 collections.json）。
