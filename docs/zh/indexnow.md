---
title: "IndexNow"
subtitle: "用于网站向搜索引擎通知 URL 新增、更新与删除的开放 HTTP 协议"
canonical_url: https://mimirwiki.com/zh/wiki/indexnow
language: zh
page_class: anchor
revision_sha256: c729e1f56ef50aceeb786adeddf485c24e7bf570075d666ce3a2f756eeb232f7
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/indexnow.md
  txt: https://mimirwiki.com/zh/wiki/indexnow.txt
  json: https://mimirwiki.com/zh/wiki/indexnow.json
  jsonld: https://mimirwiki.com/zh/wiki/indexnow.jsonld
translations:
  en: https://mimirwiki.com/wiki/indexnow
  ko: https://mimirwiki.com/ko/wiki/indexnow
  ja: https://mimirwiki.com/ja/wiki/indexnow
  es: https://mimirwiki.com/es/wiki/indexnow
---

# IndexNow

> IndexNow 是 Microsoft Bing 与 Yandex 于 2021 年 10 月推出的开放 HTTP 协议，用于向搜索引擎通知新增、更新或删除的 URL。网站通过托管文本密钥文件验证所有权，截至 2026-11-23，可通过 GET 提交单个 URL，或通过 POST 单次提交最多 10,000 个 URL。任一参与端点均会将收到的提交内容共享给所有其他参与方。

IndexNow 是一种开放 HTTP 通知协议，允许网站所有者在主机上的 URL 新增、更新或删除时通知参与其中的搜索引擎。Microsoft Bing 与 Yandex 于 2021 年 10 月 18 日发布了该协议，其在 IndexNow.org 上公布的规范由赞助方 Microsoft Corporation、Yandex N.V. 和 Seznam.cz, a.s. 采用知识共享署名-相同方式共享 4.0（CC BY-SA 4.0）许可协议授权。网站通过在主机上托管 UTF-8 文本密钥文件来验证域名所有权，并向任意参与端点发送单 URL 的 HTTP GET 请求或最多包含 10,000 个 URL 的 JSON POST 批量请求，接收端点会将提交的 URL 自动共享给所有其他参与搜索引擎。截至 2026-11-23，indexnow.org/searchengines.json 的官方注册表列出了 7 个参与端点：Bing、Yandex、Seznam、Naver、Yep、Internet Archive 和 Amazonbot。

**别名:** IndexNow 协议, IndexNow API, IndexNow.org

## 关键事实

- **发布日期:** 2021-10-18 [6]
- **创建者:** Microsoft Bing、Yandex [6]
- **规范许可协议:** 知识共享署名-相同方式共享 4.0（CC BY-SA 4.0） (截至 2026-11-23) [5]
- **批量提交上限:** 每次 HTTP POST 请求最多 10,000 个 URL (截至 2026-11-23) [2]
- **注册端点:** searchengines.json 中共 7 个（Bing、Yandex、Seznam、Naver、Yep、Internet Archive、Amazonbot） (截至 2026-11-23) [4]

## 事实摘要

- **类型:** 开放 HTTP URL 通知协议 [1]
- **发布日期:** 2021-10-18 [6]
- **创建者:** Microsoft Bing、Yandex [6]
- **规范赞助方:** Microsoft Corporation、Yandex N.V.、Seznam.cz, a.s. (截至 2026-11-23) [5]
- **许可协议:** 知识共享署名-相同方式共享 4.0（CC BY-SA 4.0） (截至 2026-11-23) [5]
- **提交方式:** HTTP GET（1 个 URL）与 HTTP POST JSON（最多 10,000 个 URL） (截至 2026-11-23) [2]
- **全局端点:** https://api.indexnow.org/indexnow (截至 2026-11-23) [3]
- **验证方式:** 托管在网站上的 UTF-8 文本密钥文件（8 至 128 个字符） (截至 2026-11-23) [2]
- **URI 编码标准:** RFC 3986 [2]
- **注册搜索引擎:** searchengines.json 中共 7 项（Bing、Yandex、Seznam、Naver、Yep、Internet Archive、Amazonbot） (截至 2026-11-23) [4]
- **费用:** 免费 (截至 2026-11-23) [8]

## IndexNow 简介与起源

IndexNow 是一种免费、开放的 HTTP 协议，允许网站所有者在网站上的 URL 新增、更新或删除时通知参与其中的搜索引擎和网络爬虫。[1][8] 在没有推送通知的情况下，搜索引擎依赖周期性抓取来检测网站变动，由于爬虫不会频繁重访每一个 URL，这一过程可能需要数天甚至数周。[1][6] 在内容发生变化时发送通知，可使搜索引擎优先抓取这些 URL，并减少对未变动页面的探索性抓取，从而降低服务器负载。[1][6][8]

Microsoft Bing 与 Yandex 于 2021 年 10 月 18 日发布了 IndexNow。[6] 根据 2026-11-23 查阅的 IndexNow.org 服务条款，IndexNow.org 的赞助方为 Microsoft Corporation、Yandex N.V. 和 Seznam.cz, a.s.。[5] 赞助方将 IndexNow.org 上发布的协议规范著作权以知识共享署名-相同方式共享 4.0（CC BY-SA 4.0）许可协议授权，不授予其他任何知识产权，且服务条款受加利福尼亚州法律管辖。[1][5]

IndexNow 的一项核心要求是跨引擎共享：采用该协议的搜索引擎均同意，提交至任一参与端点的所有 URL 都会自动共享给所有其他参与的搜索引擎。[2][3][6] 因此，网站所有者只需向单个参与端点发送每条 URL 通知即可。[3]

## IndexNow 提交方式与 HTTP 状态码

IndexNow 支持两种 HTTP 提交方式，用于向搜索引擎通知新增、更新或删除的 URL：单 URL 的 HTTP GET 请求与多 URL 的 HTTP POST JSON 请求。[2] 这两种方式均可通过任意 HTTP 客户端、浏览器、脚本或 `curl`、`wget` 等命令行工具发起。[2][3]

通过 HTTP GET 提交单个 URL 时，网站向 `https://<searchengine>/indexnow?url={url-changed}&key={your-key}` 发送请求；当密钥文件未放置在网站根目录时，可附带可选的 `keyLocation` 参数。[2][3] 提交的 URL 必须依据 RFC 3986 进行 URL 转义和编码，例如将 `:` 编码为 `%3A`，`/` 编码为 `%2F`，`?` 编码为 `%3F`，`=` 编码为 `%3D`，`&` 编码为 `%26`。[2][3]

在单次请求中提交多个 URL 时，网站需向 `/indexnow` 发送带有 `Content-Type: application/json; charset=utf-8` 请求头的 `HTTP POST` 请求，并在 JSON 请求体中包含 `host`、`key`、可选的 `keyLocation` 以及 `urlList`。[2][3] 截至 2026-11-23，每次 POST 请求最多支持 10,000 个 URL，且可在同一主机下混合包含 `http` 与 `https` URL。[2][3] 单次负载超过 10,000 个 URL 可能导致请求失败或返回 HTTP 422。[3] 网站还可以提交重定向的 URL（HTTP 301、HTTP 302 或 meta refresh）以及返回 HTTP 404 或 HTTP 410 的已删除 URL，以便搜索引擎更新或移除过时条目。[3]

截至 2026-11-23，IndexNow.org 为提交请求记录了 6 种 HTTP 响应状态码。[2][3][7]

| HTTP 状态码 | 状态 | 文档说明的含义 |
| --- | --- | --- |
| 200 | OK | 单个 URL 或 URL 批次提交成功；仅确认接收 |
| 202 | Accepted | 已收到 URL，密钥所有权验证待完成（常见于首次请求） |
| 400 | Bad Request | 请求格式无效 |
| 403 | Forbidden | 密钥无效（例如缺少密钥文件，或文件中未包含该密钥） |
| 422 | Unprocessable Entity | URL 不属于该主机、密钥不符合规范要求，或负载超出限制 |
| 429 | Too Many Requests | 请求频率被标记为过高或疑似垃圾提交 |

## IndexNow API 密钥规则与域名所有权验证

IndexNow 要求手动提交 URL 的网站所有者在目标主机上托管一个 UTF-8 编码的文本密钥文件，以证明对该主机的所有权。[2][3] 截至 2026-11-23，密钥长度必须为 8 至 128 个字符，且仅可包含小写 ASCII 字母（`a-z`）、大写 ASCII 字母（`A-Z`）、数字（`0-9`）和连字符（`-`）。[2][3] IndexNow 文档将这些字符称为十六进制字符，同时明确允许使用 `a-z`、`A-Z`、`0-9` 和 `-`。[2] 密钥可通过 GUID 或 UUID 生成器、命令行工具，或 Bing Webmaster Tools 中提供的在线生成器生成。[3][6][7]

IndexNow 定义了两种用于验证所有权的密钥文件托管方式。[2]

- 方式 1（根目录）：在主机根目录下托管名为 `{your-key}.txt` 的 UTF-8 文件（例如 `https://www.example.com/{your-key}.txt`），文件内容仅包含密钥字符串。[2][3] 规范将方式 1 列为推荐方案，其适用范围覆盖整个主机上的 URL。[2][3]
- 方式 2（子路径目录）：在同一主机上无需登录即可公开访问的文件夹中托管一个或多个 UTF-8 文本密钥文件，并在每次提交时通过 GET 的 `keyLocation` 查询参数或 POST 的 JSON 字段提供密钥文件 URL。[2][3] 在方式 2 下，密钥文件所在目录决定了有效 URL 的范围：例如，位于 `http://example.com/catalog/key12457EDd.txt` 的密钥文件仅适用于以 `http://example.com/catalog/` 开头的 URL，而 `http://example.com/help/` 或 `http://example.com/image/` 下的 URL 对该密钥无效。[2]

当网站提交 URL 时，参与搜索引擎会抓取密钥文件以验证主机所有权，并在所有者更改密钥前持续认可该密钥。[2] 若要在不中断服务的情况下轮换 API 密钥，网站所有者只需将现有密钥文件替换为新的 `{key}.txt` 文件，并开始使用新密钥提交 URL，即可触发自动重新验证。[3] 使用原生管理 IndexNow 提交的内容管理系统（CMS）、托管服务商或 CDN 的网站无需手动创建密钥文件。[3]

## IndexNow 参与搜索引擎与端点

IndexNow 在 `https://www.indexnow.org/searchengines.json` 发布了参与搜索引擎和爬虫的机器可读 JSON 注册表。[4] 截至 2026-11-23，`searchengines.json` 列出了 7 个参与方，每个参与方均映射到一个 `meta.json` 端点。[4] 同一日期，IndexNow.org 首页列出了 5 个支持的搜索引擎（Microsoft Bing、Naver、Seznam.cz、Yandex 和 Yep），而 IndexNow FAQ 列出了 6 个具名服务的提交端点以及全局端点 `https://api.indexnow.org/indexnow`。[1][3]

| 注册表键名（`searchengines.json`） | 元数据 URL（`searchengines.json`） | 提交端点（`indexnow.org/faq`） |
| --- | --- | --- |
| `bing` | `https://www.bing.com/indexnow/meta.json` | `https://www.bing.com/indexnow` |
| `yandex` | `https://www.yandex.com/indexnow/meta.json` | `https://yandex.com/indexnow` |
| `seznam` | `https://search.seznam.cz/indexnow/meta.json` | `https://search.seznam.cz/indexnow` |
| `naver` | `https://searchadvisor.naver.com/indexnow/meta.json` | `https://searchadvisor.naver.com/indexnow` |
| `yep` | `https://indexnow.yep.com/indexnow/meta.json` | `https://indexnow.yep.com/indexnow` |
| `internetarchive` | `https://web-static.archive.org/indexnow/meta.json` | FAQ 端点列表中未列出 |
| `amazonbot` | `https://indexnow.amazonbot.amazon/indexnow/meta.json` | `https://indexnow.amazonbot.amazon/indexnow` |

2025 年 5 月 19 日，Microsoft AI Bing 首席产品经理 Fabrice Canel 和 Krishna Madhavan 在 Bing Webmaster Blog 上宣布，Amazon 计划于 2025 年 6 月中旬开始采用 IndexNow，以检测网页内容变化并减少不必要的抓取。[9] 截至 2026-11-23，Amazon 的 `amazonbot` 端点已同时列入 `searchengines.json` 和 IndexNow FAQ。[3][4]

根据 IndexNow.org 公布的要求，参与 IndexNow 的搜索引擎必须将提交的 URL 自动共享给所有其他参与搜索引擎，在至少一个市场中具备显著影响力或与搜索市场紧密相关，并对 URL 提交作出显著贡献。[2]

## IndexNow 的 CMS、插件与 Cloudflare Crawler Hints 集成

IndexNow 已集成至内容管理系统（CMS）、第三方 SEO 插件和[内容分发网络](https://mimirwiki.com/zh/wiki/content-delivery-network)（CDN）中，使网站能够自动发出 URL 变更通知。[3][7]

2021 年 11 月 30 日，[Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare) 与 Microsoft Bing 及 Yandex 合作，在 Cloudflare Crawler Hints 中加入 IndexNow 支持，并向所有 Cloudflare 客户免费全面开放 Crawler Hints。[10] Cloudflare 客户只需在 Cloudflare 控制台 Cache 选项卡下的 Configuration 区域中启用单项设置，即可在网站内容变更时由 Cloudflare 自动发送 IndexNow 信号。[10] 在 2021 年 11 月 30 日的公告中，Cloudflare 报告称约 45% 的互联网流量来自网络爬虫和机器人，且一项针对主要搜索爬虫流量的全年研究显示，53% 的爬虫访问请求的是自上次访问以来未发生变化的页面。[10] 截至该日期，已有超过 60,000 个独立 Cloudflare 网站启用了 Crawler Hints，并向 Bing 发送了约 10 亿条变更提示。[10] 截至 2026-11-23，IndexNow.org 和 Bing Webmaster Tools 均将 Cloudflare Crawler Hints 列为原生 CDN 集成方案，而 2021 年 10 月的发布博文亦提及 Akamai 计划集成 IndexNow。[3][6][7]

截至 2026-11-23，IndexNow.org 和 Bing Webmaster Tools 列出了 16 个通过原生集成或插件与扩展支持 IndexNow 的 CMS 平台：WordPress、Shopify、Wix、GoDaddy、Duda、XenForo、Milestone、Joomla!、Drupal、Bitrix24、PrestaShop、MODX、Shopware、OpenCart、Typo3 和 Umbraco。[3][7] Bing Webmaster Tools 列出的具体第三方插件包括：适用于 WordPress 的 IndexNow plugin、Yoast、RankMath、AIOSEO 和 SEOPress；适用于 Shopify 的 InstaIndex；适用于 Joomla! 的 Aimy Sitemap PRO 和 JSitemap；以及适用于 Bitrix24 的 ReIndex 和 TurboIndex。[7]

在 2021 年 10 月发布时，Microsoft Bing 发布了开源代码以协助 WordPress 及其他 CMS 平台接入 IndexNow，报告了 Wix、Duda、Botify、Oncrawl、Onely 和 Yext 的集成计划，并表示此前使用 Bing Webmaster URL 提交 API 的大型网站（包括 eBay、LinkedIn、MSN、GitHub 和 Bizapedia）计划迁移至 IndexNow。[6] 2025 年 5 月 19 日，Microsoft Bing 报告 Shopify 以及数字营销与 CMS 服务商 Milestone Inc. 已集成 IndexNow。[9] 网站所有者可通过 Bing Webmaster Tools 门户查看已提交 URL 的接收情况。[7]

## IndexNow 协议限制、未参与范围及与站点地图的关系

IndexNow 作为一种自愿性的 URL 通知信号运行，其实际适用范围受限于搜索引擎参与情况、抓取配额、提交限制以及赞助方条款。[2][3][4][5][7]

IndexNow 的覆盖范围仅限于已在协议中注册的服务。截至 2026-11-23，`indexnow.org/searchengines.json` 列出了 7 个参与端点：Bing、Yandex、Seznam、Naver、Yep、Internet Archive 和 Amazonbot。[4] 由于 URL 自动共享仅在参与搜索引擎之间生效，未出现在该注册表中的搜索引擎不会通过该协议接收 IndexNow 通知。[2][4] 根据 IndexNow.org 服务条款，各赞助方保留不经通知即修改规范、随时在任何产品或服务中使用或停用 IndexNow 的权利，且不承担读取或收录已提交 URL 的义务。[5]

从 IndexNow 端点收到 HTTP `200` 响应仅确认该端点已收到提交的 URL 或 URL 列表。[2] IndexNow FAQ 与 Bing Webmaster Tools 均明确指出，提交 URL 并不保证抓取或收录。[3][7] 搜索引擎会根据自身的抓取配额、调度逻辑和质量信号评估每个提交的 URL，且通过 IndexNow 触发的每次抓取均会计入网站的抓取配额。[3][7]

IndexNow 同时对批量大小和请求频率施加限制。截至 2026-11-23，单次 POST 请求的上限为 10,000 个 URL，过多或重复的提交可能触发 HTTP `429` 速率限制。[2][3] IndexNow FAQ 建议仅在内容发生实质性变更时提交，在重新提交同一 URL 前至少等待 5 分钟，并对评论、评价或论坛帖子等用户生成内容采取增量提交策略（例如，第 1 至 20 条每条提交，至 100 条每 5 条提交一次，至 1,000 条每 10 条提交一次）。[3]

IndexNow 旨在作为 [XML 站点地图](https://mimirwiki.com/zh/wiki/sitemaps)的补充，面向网站启用该协议后新增、更新或删除的 URL。[3][7] IndexNow FAQ 指出，除站点迁移或改版等重大变更外，网站应避免追溯提交较早的变更或一次性提交整个站点，并应继续维护带有准确 `lastmod` 时间戳的 XML 站点地图，以提供完整的 URL 清单并支持对低频更新页面的发现。[3]

## 常见问题

### 什么是 IndexNow？

IndexNow 是 Microsoft Bing 与 Yandex 于 2021 年 10 月 18 日推出的免费开放 HTTP 协议，允许网站所有者在 URL 新增、更新或删除时通知参与其中的搜索引擎。向任一参与端点提交 URL 后，该通知会自动共享给所有其他参与的搜索引擎。 [1][2][6][8]

### 哪些搜索引擎参与了 IndexNow？

截至 2026-11-23，indexnow.org/searchengines.json 的官方注册表列出了 7 个参与端点：Bing、Yandex、Seznam、Naver、Yep、Internet Archive 和 Amazonbot。未列入该注册表的搜索引擎不会通过 IndexNow 接收 URL 通知。 [2][4]

### 单次 IndexNow 请求最多可以提交多少个 URL？

截至 2026-11-23，IndexNow 支持每次 HTTP GET 请求提交 1 个 URL，或单次 UTF-8 JSON HTTP POST 请求最多提交 10,000 个 URL。在单次 POST 负载中提交超过 10,000 个 URL 可能导致请求失败或返回 HTTP 422（Unprocessable Entity）。 [2][3]

### IndexNow 如何验证网站所有权？

手动配置时，网站所有者需创建一个 8 至 128 个字符（包含 a-z、A-Z、0-9 和连字符）的 API 密钥，并将其托管在网站根目录下的 UTF-8 文本文件 {your-key}.txt 中。此外，也可以将密钥文件托管在可公开访问的子文件夹中，并在 keyLocation 参数中提供其 URL，此时仅该目录下的 URL 为有效提交范围。 [2][3]

### 收到 IndexNow 返回的 HTTP 200 响应是否保证抓取或收录？

不能。HTTP 200 响应仅确认搜索引擎已收到提交的单个 URL 或 URL 批次。搜索引擎仍会应用各自的抓取配额、调度逻辑和质量信号，由此触发的每次抓取均会计入网站的抓取配额。 [2][3][7]

### IndexNow 会取代 XML 站点地图吗？

不会。IndexNow 官方文档明确指出，网站应将 IndexNow 与 XML 站点地图配合使用。IndexNow 用于向搜索引擎通知近期的 URL 新增、更新与删除，而包含 lastmod 值的 XML 站点地图则用于提供完整的站点 URL 清单，并帮助发现较旧或不常更新的页面。 [3]

## 可引用的句子

- Microsoft Bing 与 Yandex 于 2021 年 10 月 18 日发布了 IndexNow 协议。 [6]
- IndexNow.org 上发布的 IndexNow 协议规范由赞助方 Microsoft Corporation、Yandex N.V. 和 Seznam.cz, a.s. 采用知识共享署名-相同方式共享 4.0 许可协议授权。 [5]
- 截至 2026-11-23，IndexNow 在单次 HTTP POST JSON 请求中最多支持提交 10,000 个 URL。 [2][3]
- 截至 2026-11-23，IndexNow API 密钥长度必须为 8 至 128 个字符，仅限使用小写字母、大写字母、数字和连字符。 [2][3]
- 截至 2026-11-23，indexnow.org/searchengines.json 列出了 7 个参与端点：Bing、Yandex、Seznam、Naver、Yep、Internet Archive 和 Amazonbot。 [4]
- 2021 年 11 月 30 日，Cloudflare 宣布在 Crawler Hints 中支持 IndexNow，并向 Cloudflare 客户免费全面开放 Crawler Hints。 [10]
- IndexNow 端点返回的 HTTP 200 响应仅确认已收到提交的 URL，并不保证抓取或收录。 [2][3][7]

## 时间线

- 2021-10-18: Microsoft Bing 与 Yandex 发布 IndexNow URL 通知协议。 [6]
- 2021-11-30: Cloudflare 在 Crawler Hints 中新增 IndexNow 支持，并向所有 Cloudflare 客户免费全面开放 Crawler Hints。 [10]
- 2025-05-19: Microsoft Bing 报告 Shopify 与 Milestone Inc. 已支持 IndexNow，并宣布 Amazon 计划于 2025 年 6 月中旬开始采用 IndexNow。 [9]

## 来源

1. Home | IndexNow.org. IndexNow. https://www.indexnow.org/ (访问于 2026-11-23; tier 3: official site)
2. Documentation | IndexNow.org. IndexNow. https://www.indexnow.org/documentation (访问于 2026-11-23; tier 3: official site)
3. FAQ | IndexNow.org. IndexNow. https://www.indexnow.org/faq (访问于 2026-11-23; tier 3: official site)
4. IndexNow Participating Search Engines JSON. IndexNow. https://www.indexnow.org/searchengines.json (访问于 2026-11-23; tier 3: official site)
5. Terms | IndexNow.org. IndexNow. https://www.indexnow.org/terms (访问于 2026-11-23; tier 3: official site)
6. IndexNow – Instantly Index your web content in Search Engines |.... Microsoft Bing Webmaster Blog. 发布于 2021-10-18. https://blogs.bing.com/webmaster/2021/10/IndexNow-Instantly-Index-your-web-content-in-Search-Engines/ (访问于 2026-11-23; tier 3: official site)
7. How to add IndexNow to your website | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow/getstarted (访问于 2026-11-23; tier 3: official site)
8. Why IndexNow | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow (访问于 2026-11-23; tier 3: official site)
9. IndexNow Drives Smarter and Faster Content Discovery | Bing.... Microsoft Bing Webmaster Blog. 发布于 2025-05-19. https://blogs.bing.com/webmaster/2025/5/IndexNow-Drives-Smarter-and-Faster-Content-Discovery/ (访问于 2026-11-23; tier 3: official site)
10. Cloudflare Supports IndexNow via one-click Integration | Bing.... Microsoft Bing Webmaster Blog. 发布于 2021-11-30. https://blogs.bing.com/webmaster/2021/11/Cloudflare-Supports-IndexNow-via-one-click-Integration/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "IndexNow." 版本 c729e1f5, 2026-11-23. https://mimirwiki.com/zh/wiki/indexnow
