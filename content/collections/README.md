# 集合页（/products/switches/collections/...）说明

sitemap 中共 20 个集合/子集合 URL（完整清单见 `data/site-urls.json` 与 `data/collections.json`）。

集合页与产品目录页（`/products/switches?page=1..8`）为**同一套产品卡片列表 UI**，无独有正文；
每张卡片包含：产品图（width-640 rendition）、名称、SKU、规格标签（PoE / Downlink Ports / Uplink Ports）、价格（US$）、
`Compare` / `View details` / `Request quote` 三个操作。

已核实的集合页头部计数（逐字）：

- ENOS Data Center Switches：`Browse: Back to Switches` · `14 products`
- ENOS BinaryStar Switches：`Browse: Back to Switches` · `9 products`
- ENOS Enterprise & ISP Switches：`Browse: Back to Switches` · `55 products`
- SMB/SME Switches：`Browse: Back to Switches` · `4 products`
- 总目录 /products/switches：`Browse: All product lines` · `72 products` · 分页 `1 / 8` ～ `8 / 8`

目录/集合页共用 UI 字符串（逐字）：

```
Search products

SearchSearch

GridList

Sort

Featured

72 products

Compare

View details    Request quote
```

每个产品卡片的全部字段（名称、SKU、价格、规格标签、图片 URL、详情/报价链接）已 100% 结构化收录于
`data/products.json`；每个产品的完整详情（Highlights、全部规格、软件特性、资源 PDF、系列对比表）在
`content/products/*.md`。
