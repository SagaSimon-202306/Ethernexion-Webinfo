# 产品详情页标准模板块（全站一致，逐字记录一次）

每个产品详情页都包含以下两个模板块，文字完全相同（仅链接指向对应产品 slug）。为避免 72 个文件重复，此处逐字保存一次。

## Request a quote

```
## Request a quote

We will route this inquiry with product context to our sales team.

Contact salesContact a distributor

Country *

Company *

On behalf of a companyPersonal inquiry

Select Personal inquiry if you are not contacting on behalf of a company.

Contact name *

Telephone No

—

Optional. Dial code follows Country.

Email *

Message *

Submit inquiry
```

## Related products

每页展示 4 张相关产品卡片（图片 + SKU + 名称 + View / Quote 链接），卡片内容取自产品目录（见 `data/products.json` 与各产品文件）。

## 页面操作条（每页均有）

```
[View all specifications](<product-url>#specifications)

[Request a quote](<product-url>#quote)

[Contact a distributor](<product-url>?quote_tab=partner#quote)·Compare· [Datasheet](<product-url>#resources)· [Back to category](https://www.ethernexion.com/products/switches)
```

## 页脚价格条（每页均有）

```
<产品全名>

<SKU>

US$ <价格>

[Request a quote](<product-url>#quote)
```

## Specifications / Software specifications 小节引导语（每页相同）

```
## Specifications

Physical interfaces, power, cooling, and mechanical details for this SKU.

## Software specifications

Operating system, protocol stack, and management capabilities for this SKU.

[Software downloads](<product-url>#resources)

## Compare models

Specifications that differ between models in this series.

Product Series

N models in this series — select one to view its specs and pricing.
```
