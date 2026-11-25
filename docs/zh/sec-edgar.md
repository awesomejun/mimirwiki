---
title: "SEC EDGAR"
subtitle: "美国证券交易委员会的电子申报与公开信息披露系统"
canonical_url: https://mimirwiki.com/zh/wiki/sec-edgar
language: zh
page_class: anchor
revision_sha256: 5d312e5775c140ac36fa94749cfe6e817a08d7e3f9c5270b548c0dc935709533
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/sec-edgar.md
  txt: https://mimirwiki.com/zh/wiki/sec-edgar.txt
  json: https://mimirwiki.com/zh/wiki/sec-edgar.json
  jsonld: https://mimirwiki.com/zh/wiki/sec-edgar.jsonld
translations:
  en: https://mimirwiki.com/wiki/sec-edgar
  ko: https://mimirwiki.com/ko/wiki/sec-edgar
  ja: https://mimirwiki.com/ja/wiki/sec-edgar
  es: https://mimirwiki.com/es/wiki/sec-edgar
---

# SEC EDGAR

> EDGAR（Electronic Data Gathering, Analysis, and Retrieval）是美国证券交易委员会（SEC）用于提交 Form 10-K、10-Q 和 8-K 等证券披露文件的主要系统。其公开数据库可免费检索，每位申报人由中央索引键（CIK）唯一标识。data.sec.gov 的 JSON API 无需 API 密钥，自动化访问速率限制为每秒 10 次请求。

EDGAR（Electronic Data Gathering, Analysis, and Retrieval，电子数据收集、分析与检索系统）是美国证券交易委员会（SEC）的主要系统，公司及其他申报人通过该系统提交依据《1933 年证券法》、《1934 年证券交易法》、《1939 年信托契约法》和《1940 年投资公司法》要求披露的文件。公众可免费访问 EDGAR 公开数据库。EDGAR 为每位申报人分配一个中央索引键（Central Index Key，CIK），并为每份已受理的申报文件分配一个受理编号（accession number）。SEC 还通过 data.sec.gov 上的 REST API 以 JSON 格式发布申报历史及提取的 XBRL 财务数据，这些 API 无需身份验证或 API 密钥。

**别名:** EDGAR, Electronic Data Gathering, Analysis, and Retrieval, SEC EDGAR 数据库, EDGAR 申报系统, data.sec.gov

## 关键事实

- **运营机构:** 美国证券交易委员会（EDGAR 业务办公室） [1]
- **申报人标识符:** 中央索引键（CIK），在 API URL 中以 0 补齐至 10 位数字 [2]
- **请求速率限制:** 每位用户每秒 10 次请求 (截至 2026-11-21) [3]
- **API 身份验证:** 无，不需要 API 密钥 (截至 2026-11-21) [2]
- **全文检索范围:** 2001 年以来的电子申报文件 (截至 2026-11-21) [6]

## 事实摘要

- **全称:** Electronic Data Gathering, Analysis, and Retrieval [1]
- **运营机构:** 美国证券交易委员会（SEC） [1]
- **管理部门:** EDGAR 业务办公室（EDGAR Business Office） [1]
- **申报人标识符:** 中央索引键（CIK） [3]
- **申报文件标识符:** 受理编号（accession number），例如 0001193125-15-118890 [3]
- **公众访问:** 免费 [1]
- **数据 API:** 返回 JSON 的 data.sec.gov REST API：submissions、company concept、company facts、frames [2]
- **API 身份验证:** 无需验证（截至 2026-11-21） [2]
- **速率限制:** 每秒 10 次请求（截至 2026-11-21） [3]
- **申报受理时间:** 工作日美国东部时间上午 6:00 至晚上 10:00 [3]
- **全文检索范围:** 2001 年以来的电子申报文件 [6]
- **申报人登录:** 带有多因素认证的 Login.gov 个人账户凭据 [7]

## SEC EDGAR 的定义与申报主体

SEC 将 EDGAR（Electronic Data Gathering, Analysis, and Retrieval）系统定位为公司及其他主体依据《1933 年证券法》、《1934 年证券交易法》、《1939 年信托契约法》和《1940 年投资公司法》提交文件的主要系统。[1] SEC 一份最后审阅日期为 2025 年 11 月 28 日的页面显示，该系统每日处理约 4,700 份申报文件，每年向公众传输 3,000 TB 数据，并且平均每年新增 40,000 名申报人。[1] EDGAR 业务办公室（EDGAR Business Office）是该系统的业务负责部门，负责系统治理、战略规划与申报人支持。[1]

SEC 规定，无论是外国公司还是美国本土公司，均须通过 EDGAR 以电子方式提交注册声明、定期报告及其他表格，且任何人均可免费访问和下载这些信息。[3] 除公司申报文件外，公开数据库还收录共同基金、交易所交易基金（ETF）、变额年金以及个人提交的信息。[1] EDGAR 在每周一至周五的工作日受理新申报，时间为美国东部时间上午 6:00 至晚上 10:00。部分在美国东部时间下午 5:30 之后（股权变动表格 Form 3、4 和 5 为晚上 10:00 之后）开始提交的文件，将在下一个工作日对外发布。[3]

SEC 于 1983 年开始研发电子信息披露系统，并于 1992 年 7 月 15 日向自愿参与的申报人开放正式运行的 EDGAR 系统。1993 年 2 月 23 日发布的规则强制要求实行电子申报，分阶段过渡自 1993 年 4 月 26 日启动；要求外国发行人通过 EDGAR 申报的规则则于 2002 年 11 月 4 日生效。[9] SEC 的数据访问指南页面说明，EDGAR 始于 1994/1995 年，其索引文件列出了自 1994 年第三季度以来的所有公开申报文件。[3]

## EDGAR 标识符：CIK 与受理编号

当申报人注册向 SEC 提交文件时，EDGAR 会为其分配一个唯一的数字标识符，即中央索引键（Central Index Key，CIK）。CIK 编号始终专属于该申报人，不会被回收复用。[3] 申报人包括公司、基金和个人；若公司或基金更名，同一个 CIK 可能会关联多个名称。[3] 在 data.sec.gov 的 API URL 中，CIK 写作 10 位数字，不足位数在前端补 0。[2]

每份已受理的申报文件都会获得一个受理编号（accession number），这是由 EDGAR 自动分配的唯一标识符。以 SEC 给出的示例 0001193125-15-118890 为例，前 10 位数字是提交该文件的主体（可能是发行公司本身，也可能是第三方申报代理机构）的 CIK，接下来两位数字是年份，最后一组数字是该 CIK 提交申报的顺序计数。该计数通常（但并非总是）在每个日历年初重置。[3] 两种标识符的格式汇总如下。[2][3]

| 标识符 | SEC 文档中的书写形式 | 标识对象 |
| --- | --- | --- |
| 中央索引键（CIK） | API URL 中为 `CIK##########`，前端补 0 至 10 位 | 申报人：公司、基金或个人 |
| 受理编号（accession number） | `0001193125-15-118890`：提交方 CIK、两位年份、顺序计数 | 单份已受理的申报文件 |

申报文件存储在由这两种标识符共同构成的路径下。在 SEC 的示例路径 `/Archives/edgar/data/1122304/000119312515118890/` 中，第一级目录为 CIK 目录，第二级目录为去除连字符后的受理编号，该路径格式适用于 2000 年 5 月 26 日之后提交的文件。CIK 目录和受理编号目录支持目录浏览，但上级目录 `/Archives/edgar/data/` 不可浏览。[3] SEC 还发布了一个关联股票代码、CIK 和公司名称的文件 `company_tickers.json`，并会定期更新，但不保证其准确性或覆盖范围。[3]

## 常见 EDGAR 表格类型

EDGAR 通过表格类型（form type）识别每份申报文件，表格类型后附加“/A”（例如 10-K/A）表示修订文件。[5] 下表列出了 SEC 在申报文件检索指南及 Form D 说明中介绍的部分常见表格类型。[5][11]

| 表格类型 | 说明 |
| --- | --- |
| 10-K | 包含经审计年度财务报表的年度报告 |
| 10-Q | 包含未经审计季度财务报表的季度报告 |
| 8-K | 重大事件或信息的临时报告，在下一份定期报告发布前向公众披露 |
| S-1 | 面向公众公开发行和出售证券的注册声明，常用于首次公开募股（IPO） |
| 4 | 公司内部人士实益所有权变动声明，须在交易后两个工作日内提交 |
| 20-F | 外国私人发行人的年度报告或注册声明 |
| D | 依据 D 条例（Regulation D）进行的豁免证券发行通知 |

EDGAR 上的 Form D 是 D 条例要求向 SEC 提交的豁免发行通知，必须在首次出售证券后的 15 天内提交。根据 SEC 一份最后审阅日期为 2026 年 4 月 24 日的页面，SEC 不对开设或维护 EDGAR 账户以及提交 Form D 通知或其修订文件收取费用。[11] 公司在提交 Form D 之前，必须先拥有 EDGAR 账户及相应的 CIK。[11]

多种 EDGAR 表格类型中的财务报表也以结构化数据形式提供。data.sec.gov 的 XBRL API 涵盖 Form 10-Q、10-K、8-K、20-F、40-F 和 6-K 及其变体，SEC 表示其于 2009 年首次要求采用 XBRL。[2] SEC 将 XBRL 描述为一种基于 XML 的财务报表报告格式，既可作为独立的 XML 文件提交，也可以内联 XBRL（inline XBRL）形式嵌入 HTML 报告中提交。[2]

## data.sec.gov API、XBRL 框架与 SEC 公平访问规则

SEC 在 data.sec.gov 上托管了以 JSON 格式提供 EDGAR 数据的 RESTful API。截至 2026-11-21，这些 API 无需身份验证或 API 密钥，涵盖每位申报人的申报历史以及财务报表中的 XBRL 数据。[2] 官方文档列出的端点如下。[2]

| 端点 | 返回内容 |
| --- | --- |
| `https://data.sec.gov/submissions/CIK##########.json` | 单个主体的申报历史，附带当前名称、曾用名、交易所及股票代码等元数据 |
| `https://data.sec.gov/api/xbrl/companyconcept/CIK##########/us-gaap/AccountsPayableCurrent.json` | 单家公司针对单一概念的全部 XBRL 披露数据 |
| `https://data.sec.gov/api/xbrl/companyfacts/CIK##########.json` | 通过单次调用返回单家公司的全部公司概念数据 |
| `https://data.sec.gov/api/xbrl/frames/us-gaap/AccountsPayableCurrent/USD/CY2019Q1I.json` | 针对所请求日历期间，每个报告主体返回一条事实数据 |

submissions 端点返回至少一年的申报记录或最近 1,000 份申报记录（以较多者为准），并指向包含更早期申报的附加文件。frames 端点接受的期间格式为年度数据 `CY####`、季度数据 `CY####Q#` 或时点数据 `CY####Q#I`，并返回各主体中最贴合该日历期间的事实数据。XBRL 端点仅汇总使用非自定义分类标准（如 us-gaap、ifrs-full、dei 或 srt）且适用于整个申报主体的事实数据。[2] 这些 API 随申报文件发布实时更新，典型处理延迟为申报历史不到 1 秒、XBRL 数据不到 1 分钟；两套数据的批量压缩包（`submissions.zip` 和 `companyfacts.zip`）于每晚美国东部时间凌晨 3:00 左右重新发布。[2]

对 EDGAR 的自动化访问须遵守 SEC 的公平访问（fair access）规则。截至 2026-11-21，最大请求速率为每秒 10 次请求，且 SEC 要求自动化客户端在请求头中声明用户代理。其示例 `User-Agent` 值由公司名称后接管理员联系电子邮箱地址组成。[3] 该速率限制按每位用户计算，与使用的机器数量无关，且 SEC 保留封禁发送过量请求的 IP 地址的权利。[4] data.sec.gov 不支持 CORS，SEC 同时声明无法为脚本化下载流程的开发或调试提供技术支持。[2]

## EDGAR Next 申报人访问与账户管理改革

EDGAR Next 是 SEC 于 2024 年 9 月 27 日通过的关于 EDGAR 申报人访问及账户管理的规则与表格修订案的名称。[8] 该修订案要求申报人授权特定个人管理其 EDGAR 账户，并要求代表申报人行事的个人出示从 Login.gov 获取的个人账户凭据。修订案还更新了 EDGAR 访问申请表 Form ID，并引入了可选 API，供申报人提交文件、检索信息及执行账户管理任务。[8] 所有修订于 2025 年 3 月 24 日生效，同日起必须遵守修订后的 Form ID，全部修订内容的全面合规截止日期为 2025 年 9 月 15 日。[8]

SEC 一份最后审阅日期为 2025 年 12 月 22 日的 EDGAR Next 页面指出，在 EDGAR 上提交文件必须符合 EDGAR Next 要求，且过渡注册（enrollment）通道已关闭。申报人必须已完成 EDGAR Next 注册，或在 2025 年 3 月 24 日及之后获得 Form ID 申请批准；尚无访问权限的申报人需在 EDGAR Filer Management 网站上提交 Form ID 进行申请。[7] 登录三个 EDGAR 网站（EDGAR Filer Management、EDGAR Online Forms 和 EDGAR Filing）中的任意一个，均须使用 Login.gov 个人账户凭据及多因素认证，旧有登录方式已停用。[7] 申报人端 API 与公开的 data.sec.gov API 分开编写文档，相关指南涵盖了申报人 API 令牌和用户 API 令牌的使用。[2]

## EDGAR 申报文件不能证明的事项

SEC EDGAR 上存在某份申报文件，并不代表 SEC 已核实其内容。SEC 公司财务部（Division of Corporation Finance）以抽查方式审阅申报文件，并明确表示其审阅流程“并非对披露内容完整性和准确性的保证”（is not a guarantee that the disclosure is complete and accurate）：确保披露完整准确的责任在于公司及参与编制申报文件的相关方。[10] 根据《2002 年萨班斯-奥克斯利法案》（Sarbanes-Oxley Act of 2002），每家报告公司至少每三年会接受公司财务部某种程度的审阅。该部门同时补充称，其既不评估交易的优劣，也不判断某项投资是否适合特定投资者。[10]

EDGAR 申报文件同样不构成注册或批准的证明。SEC 的投资者教育网站 Investor.gov 指出，向 SEC 提交文件并不意味着个人或机构已在 SEC 注册，且 SEC 不颁发注册证书。[12] 该页面同时说明，提交 Form D 并不代表个人或机构已在 SEC 注册或获得许可。[12]

EDGAR 的公开检索工具也存在覆盖范围限制。全文检索仅覆盖 2001 年以来以电子方式提交的申报文件，包括附件（exhibits）等随附文档。[6] 部分文件目前仍以纸质形式提交，无法通过 EDGAR 获取；此外，SEC 工作人员可在文件受理后应申报人请求予以删除或更正，例如文件误以其他申报人名义提交或与先前提交重复的情况。[3]

## 常见问题

### 什么是 CIK 编号？

中央索引键（Central Index Key，CIK）是申报人注册向 SEC 提交文件时由 EDGAR 分配的唯一数字标识符。CIK 编号不会被回收复用，在 data.sec.gov API 中以 0 补齐至 10 位数字表示。 [3][2]

### 使用 SEC EDGAR API 需要 API 密钥吗？

不需要。截至 2026-11-21，SEC 明确表示 data.sec.gov API 无需身份验证或 API 密钥。自动化请求限制为每秒 10 次，SEC 要求客户端在请求头中声明用户代理。 [2][3]

### SEC 会核实 EDGAR 上申报文件的准确性吗？

SEC 公司财务部对申报文件进行选择性审阅，并明确声明其审阅流程并不保证披露内容完整准确。确保披露完整准确的责任归属于公司及参与编制申报文件的相关方。 [10]

### EDGAR 中的申报文件可以追溯到什么时候？

SEC 表示 EDGAR 始于 1994/1995 年，其索引文件列出了自 1994 年第三季度以来的公开申报文件。全文检索覆盖 2001 年以来以电子方式提交的文件。 [3][6]

### 什么是 EDGAR Next？

EDGAR Next 是 SEC 于 2024 年 9 月 27 日通过的一套关于申报人访问和账户管理的规则与表格修订案。该修订案于 2025 年 3 月 24 日生效，全面合规截止日期为 2025 年 9 月 15 日，目前登录 EDGAR 必须使用带有多因素认证的 Login.gov 个人账户凭据。 [8][7]

### Form 10-K、10-Q 和 8-K 有什么区别？

Form 10-K 是包含经审计财务报表的年度报告，Form 10-Q 是包含未经审计财务报表的季度报告。Form 8-K 则是临时报告，用于在下一份定期季度报告或年度报告发布前披露重大事件或信息。 [5]

## 可引用的句子

- EDGAR 是 Electronic Data Gathering, Analysis, and Retrieval 的缩写。 [1]
- EDGAR 分配的 CIK 编号专属于该申报人，不会被回收复用。 [3]
- 截至 2026-11-21，SEC 的 data.sec.gov API 无需身份验证或 API 密钥。 [2]
- 截至 2026-11-21，SEC 对自动化访问 EDGAR 的最大请求速率限制为每秒 10 次请求。 [3]
- EDGAR 全文检索覆盖 2001 年以来以电子方式提交的申报文件。 [6]
- SEC 于 2024 年 9 月 27 日通过了 EDGAR Next 规则与表格修订案。 [8]
- SEC 公司财务部声明，其申报文件审阅流程并非对披露内容完整性和准确性的保证。 [10]
- Form D 必须在首次出售证券后的 15 天内提交。 [11]

## 时间线

- 1992-07-15: 正式运行的 EDGAR 系统向自愿参与的申报人开放。 [9]
- 1993-02-23: SEC 发布公告，通过要求实行电子申报的临时规则。 [9]
- 1993-04-26: 申报人向 EDGAR 系统的分阶段过渡启动。 [9]
- 1994-12-19: SEC 第 33-7122 号公告将临时 EDGAR 规则确立为最终规则，并适用于所有美国本土注册人。 [9]
- 1999-06-28: EDGAR 开始受理以 HTML 格式提交的正式申报文件。 [9]
- 2002-11-04: 要求外国发行人通过 EDGAR 提交 SEC 申报文件的规则生效。 [9]
- 2024-09-27: SEC 通过关于申报人访问和账户管理的 EDGAR Next 规则与表格修订案。 [8]
- 2025-03-24: EDGAR Next 修订案生效，并强制要求遵守修订后的 Form ID。 [8]
- 2025-09-15: 强制要求全面遵守所有 EDGAR Next 规则与表格修订案。 [8]

## 来源

1. SEC.gov | About EDGAR. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/about-edgar (访问于 2026-11-21; tier 1: government or public registry)
2. SEC.gov | EDGAR Application Programming Interfaces (APIs). U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-application-programming-interfaces (访问于 2026-11-21; tier 1: government or public registry)
3. SEC.gov | Accessing EDGAR Data. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data (访问于 2026-11-21; tier 1: government or public registry)
4. SEC.gov | Developer Resources. U.S. Securities and Exchange Commission. https://www.sec.gov/about/developer-resources (访问于 2026-11-21; tier 1: government or public registry)
5. SEC.gov | Using EDGAR to Research Investments. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/using-edgar-research-investments (访问于 2026-11-21; tier 1: government or public registry)
6. SEC.gov | EDGAR Full Text Search FAQ. U.S. Securities and Exchange Commission. https://www.sec.gov/edgar/search/efts-faq.html (访问于 2026-11-21; tier 1: government or public registry)
7. SEC.gov | EDGAR Next: Improving Filer Access and Account Management. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/improving-edgar/edgar-next-improving-filer-access-account-management (访问于 2026-11-21; tier 1: government or public registry)
8. SEC.gov | SEC Adopts Improvements to EDGAR System to Enhance Security, Filer Access, and Account Management. U.S. Securities and Exchange Commission. 发布于 2024-09-27. https://www.sec.gov/newsroom/press-releases/2024-155 (访问于 2026-11-21; tier 1: government or public registry)
9. Electronic Filing and EDGAR (October 2006). U.S. Securities and Exchange Commission. 发布于 2006-10-03. https://www.sec.gov/info/edgar/regoverview.htm (访问于 2026-11-21; tier 1: government or public registry)
10. SEC.gov | Filing Review Process. U.S. Securities and Exchange Commission. https://www.sec.gov/divisions/corpfin/cffilingreview.htm (访问于 2026-11-21; tier 1: government or public registry)
11. SEC.gov | What is Form D?. U.S. Securities and Exchange Commission. https://www.sec.gov/resources-small-businesses/capital-raising-building-blocks/what-form-d (访问于 2026-11-21; tier 1: government or public registry)
12. False Claims of SEC Registration | Investor.gov. U.S. Securities and Exchange Commission, Investor.gov. https://www.investor.gov/protect-your-investments/fraud/types-fraud/false-claims-sec-registration (访问于 2026-11-21; tier 1: government or public registry)

## 引用本页

Mimirwiki. "SEC EDGAR." 版本 5d312e57, 2026-11-21. https://mimirwiki.com/zh/wiki/sec-edgar
