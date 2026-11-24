---
title: "NPPES 与国家医疗服务提供者标识符（NPI）"
subtitle: "向美国医疗服务提供者分配 10 位数字标识符并在 NPI 注册库中公开的联邦系统"
canonical_url: https://mimirwiki.com/zh/wiki/nppes-npi-registry
language: zh
page_class: anchor
revision_sha256: 11f358bf3703cd6595daf9169ac6e8106ac2ed1d174fc0390da98c27926fdd90
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/nppes-npi-registry.md
  txt: https://mimirwiki.com/zh/wiki/nppes-npi-registry.txt
  json: https://mimirwiki.com/zh/wiki/nppes-npi-registry.json
  jsonld: https://mimirwiki.com/zh/wiki/nppes-npi-registry.jsonld
translations:
  en: https://mimirwiki.com/wiki/nppes-npi-registry
  ko: https://mimirwiki.com/ko/wiki/nppes-npi-registry
  ja: https://mimirwiki.com/ja/wiki/nppes-npi-registry
---

# NPPES 与国家医疗服务提供者标识符（NPI）

> NPPES 是美国医疗保险和医疗补助服务中心（CMS）用于分配国家医疗服务提供者标识符（NPI）的系统，NPI 是遵循 HIPAA 标准的 10 位医疗服务提供者标识符。其公开数据可在 NPI 注册库中搜索、通过只读 API 查询，或以月度和周度文件形式下载。拥有 NPI 并不代表医疗服务提供者的执业执照或资质已获确认。

全国医疗计划与提供者编号系统（National Plan and Provider Enumeration System，NPPES）是美国医疗保险和医疗补助服务中心（Centers for Medicare & Medicaid Services，CMS）向医疗服务提供者分配国家医疗服务提供者标识符（National Provider Identifier，NPI）的系统。NPI 是依据 1996 年《健康保险流通与责任法案》（Health Insurance Portability and Accountability Act of 1996，HIPAA）采用的医疗服务提供者标准唯一健康标识符，它是一个 10 位数字标识符，第 10 位为校验位，号码本身不编码任何有关医疗服务提供者的信息。CMS 通过 NPI 注册库搜索网站、只读 API 以及可下载文件，发布每条 NPPES 记录中依法可公开的部分。CMS 明确表示，颁发 NPI 并不保证或验证医疗服务提供者持有执业执照或相关资质。

**别名:** NPPES, National Plan and Provider Enumeration System, NPI, National Provider Identifier, NPI Registry, NPPES NPI Registry, NPI 注册库, 国家医疗服务提供者标识符

## 关键事实

- **标识符格式:** 10 位数字，末位为 Luhn 校验位 [4]
- **运营机构:** 美国医疗保险和医疗补助服务中心（CMS） [6]
- **公开 API 版本:** 2.1（版本 1.0 与 2.0 已停用） (截至 2026-11-21) [5]
- **API 结果上限:** 每次请求 200 条记录，使用 skip 参数时每次搜索最多 1,200 条 (截至 2026-11-21) [5]
- **批量文件更新频率:** 每月发布全量替换文件，每周发布增量文件 (截至 2026-11-21) [8]

## 事实摘要

- **全称:** National Plan and Provider Enumeration System [6]
- **运营机构:** 美国医疗保险和医疗补助服务中心（CMS） [6]
- **颁发标识符:** 国家医疗服务提供者标识符（NPI） [1]
- **标识符格式:** 10 位数字，第 10 位为校验位 [3]
- **校验位算法:** Luhn 公式（模 10“double-add-double”） [4]
- **法律依据:** HIPAA 行政简化规定，45 CFR Part 162 Subpart D [2]
- **最终规则:** 69 FR 3434，发布于 2004-01-23 [2]
- **实体类型:** 类型 1（个人）、类型 2（机构） [10]
- **公开查询:** NPI 注册库，npiregistry.cms.hhs.gov [6]
- **API:** 只读 JSON API，版本 2.1（截至 2026-11-21） [5]
- **批量数据:** 月度全量替换文件、周度增量文件、月度停用文件，均为版本 2（截至 2026-11-21） [7]
- **专业代码集:** 医疗服务提供者分类代码（Health Care Provider Taxonomy），由全国统一理赔委员会（NUCC）维护 [11]

## 国家医疗服务提供者标识符（NPI）格式与校验位

通过 NPPES 分配的国家医疗服务提供者标识符（NPI）在联邦法规中被定义为 10 位数字标识符，其中第 10 位为校验位，且不包含任何关于医疗服务提供者的语义信息。[3] CMS 将 NPI 描述为无语义信息（intelligence-free）的编号：数字本身不编码提供者所在州或医疗专业等信息。[1]

一份日期为 2004 年 1 月 23 日的 CMS 需求文档规定，NPI 由 9 位数字标识符加 1 位校验位组成，且最初颁发的 NPI 首位数字为 1 或 2，以避免与其他发卡机构标识符冲突。[4] 校验位采用模 10“double-add-double”的 Luhn 公式计算。当 NPI 在标准健康识别卡上用作发卡机构标识符时，前面会加上前缀 80840（其中 80 表示健康医疗应用，840 表示美国），校验位始终按存在该前缀的情况计算。对于未书写前缀的 NPI，可在 Luhn 求和结果中加上常数 24 来实现等效计算。[4] 在 CMS 的计算示例中，9 位标识符 123456789 计算得出的校验位为 3，完整 NPI 为 1234567893。[4]

CMS 文档中的格式规则汇总如下。[4]

| 属性 | 数值 |
| --- | --- |
| 长度 | 10 位数字 |
| 结构 | 9 位标识符加 1 位校验位 |
| 初始颁发首位数字 | 1 或 2 |
| 校验位算法 | Luhn 公式（模 10“double-add-double”） |
| 发卡机构前缀 | 80840 |
| 省略前缀时相加的常数 | 24 |

## 必须获取并使用国家医疗服务提供者标识符（NPI）的主体

所有受覆盖医疗服务提供者（covered health care provider）均须获取国家医疗服务提供者标识符（NPI）。NPI 最终规则将该术语定义为：在与美国卫生与公众服务部部长已采纳标准的交易相关的情况下，以电子形式传输任何健康信息的医疗服务提供者。[2] 根据 45 CFR 162.410，受覆盖提供者必须在标准交易中使用其 NPI 表明身份，应任何在标准交易中需要该编号的实体要求披露其 NPI，并在必填数据发生变更后的 30 天内报告变更。[3] 健康保险计划（health plan）和医疗信息清算机构（health care clearinghouse）必须在标准交易中使用已获分配 NPI 的提供者的 NPI，且健康保险计划不得要求已拥有 NPI 的提供者再申请另一个 NPI。[3]

不属于受覆盖实体的医疗服务提供者也可以申请 NPI。[3] 该法规还要求作为受覆盖提供者的机构确保其作为成员、雇员或承包商的处方开具者（即便其本人并非受覆盖实体）从 NPPES 获取 NPI。[3] 最终规则序言列举了注册护士、牙科卫生员和技术人员作为示例，说明提供医疗服务但未必开展受覆盖交易的人员同样有资格获取 NPI。[2]

NPI 最终规则于 2004 年 1 月 23 日发布，并于 2005 年 5 月 23 日生效，医疗服务提供者自该日起可开始申请。受覆盖提供者、医疗信息清算机构以及除小型健康保险计划之外的健康保险计划须在 2007 年 5 月 23 日前合规，小型健康保险计划的合规期限为 2008 年 5 月 23 日。[2] 最终规则序言将 NPI 描述为持久标识符：对个人而言，其旨在永久有效；对机构而言，所有权、名称、地址或分类代码发生变更后无需申请新的 NPI。[2] 已停用的 NPI 不会重新分配给任何其他医疗服务提供者。[3]

## NPPES 实体类型：类型 1 与类型 2 NPI

NPPES 在 NPI 申请时根据所选的两种实体类型之一分配每个国家医疗服务提供者标识符（NPI）。实体类型 1 涵盖提供医疗服务的个人，例如医师、牙医、护士、脊骨神经科医生、药剂师和物理治疗师。实体类型 2 涵盖提供医疗服务或供应医疗用品的机构，例如医院、家庭护理机构、救护车公司、联合诊所、健康维护组织（HMO）、耐用医疗设备供应商和药房。[10]

CMS-10114 申请表指出，独资经营者属于实体类型 1 个人，仅可获取一个 NPI；而成立公司的个人可同时以个人身份持有类型 1 NPI 并为公司持有类型 2 NPI。[10] 机构还可以为子部门（subpart）单独获取 NPI，申请表将子部门描述为机构型提供者的组成部分，这些部分可能位于不同地点或提供不同类型的医疗服务。[3][10] 在 NPI 注册库 API 中，这两种类型以 `NPI-1` 和 `NPI-2` 的值显示。[5]

医疗服务提供者可通过三种方式申请 NPI：通过 NPPES 在线申请、通过经提供者许可批量提交申请数据的电子文件交换（Electronic File Interchange）机构申请，或将纸质表格 CMS-10114 邮寄至 NPI 编号机构（NPI Enumerator）。[12] 申请时必须填写一项主要医疗服务提供者分类代码（Healthcare Provider Taxonomy code），最多可报告 15 个分类代码。[9] 该分类代码集由全国统一理赔委员会（National Uniform Claim Committee，NUCC）维护，每个代码均为 10 位字母数字字符串，按提供者大类、分类和专业领域三个层级组织。[11]

## NPI 注册库搜索与 NPPES API（版本 2.1）

位于 npiregistry.cms.hhs.gov 的 NPI 注册库被 CMS 描述为包含所有有效国家医疗服务提供者标识符（NPI）记录的免费目录。它展示 CMS 认为具有公共相关性的 NPI 记录部分，包括提供者姓名或名称、专业（分类代码）和执业地址。[6] 记录可按 NPI 号码、NPI 类型、分类代码描述、提供者或机构名称、授权官员（Authorized Official）姓名、城市、州、国家和邮政编码进行搜索。搜索仅返回前 2,100 条匹配结果。自 2024 年 6 月 25 日起，NPPES 限制了每小时可完成的注册库查询次数，但搜索页面未公布具体的每小时限额，同一页面同时说明批量查询必须使用数据分发文件。[6]

NPPES API 是一个以 JSON 格式返回注册库数据的只读接口，每天从 NPPES 获取最新数据。[5] 截至 2026-11-21，唯一受支持的版本是 2.1：CMS 声明版本 1.0 和 2.0 已停用，不带版本参数的请求不再有效，并将版本 2.1 的计划淘汰日期列为“TBD”（待定）。其端点为 `https://npiregistry.cms.hhs.gov/api/?version=2.1`。[5] API 帮助页面记录的请求限制如下。[5]

| 项目 | 截至 2026-11-21 的数值 |
| --- | --- |
| 支持版本 | 2.1 |
| 默认 `limit` | 10 |
| 最大 `limit` | 每次请求 200 条结果 |
| 最大 `skip` | 1,000 条记录 |
| 单组条件可获取的最大记录数 | 分 6 次请求共 1,200 条 |
| 响应格式 | JSON |

版本 2.1 文档列出的搜索参数包括 `number`、`enumeration_type`、`taxonomy_description`、`first_name`、`last_name`、`organization_name`、`city`、`state`、`postal_code`、`country_code`、`limit` 和 `skip`，文档列表中不包含 API 密钥或身份验证参数。名称和邮政编码字段在输入至少两个字符后支持末尾通配符。[5] JSON 响应包含一个地址数组（addresses，第一项为主要执业地点，第二项为邮寄地址）、一个最多 15 项的分类代码数组（taxonomies）、一个最多 50 项的其他标识符数组（other identifiers），以及用于存储其他名称、端点和附加执业地点的数组。[5]

## NPPES 可下载数据分发文件

NPPES 数据也以可下载文件的形式发布。CMS 自 2007 年 9 月起，以两种形式公开依据《信息自由法》（Freedom of Information Act，FOIA）可披露的 NPPES 医疗服务提供者数据：每日更新的只读查询数据库 NPI 注册库，以及可下载文件。CMS 对查看或下载这些数据不收取任何费用。[8] 系统生成三类文件：月度全量替换 NPI 文件、周度增量 NPI 文件和全量替换 NPI 停用文件。周度文件仅包含特定一周的数据，包括新分配的 NPI、更新内容以及新停用的 NPI，旨在与最新月度文件配合使用。[8]

月度下载包是一个 ZIP 压缩文件，内含自述文档（readme）、代码值文档、标题文件以及所有字段值均以双引号括起的逗号分隔数据文件。CMS 提示该数据文件超过 4 GB，且不提供有关下载或使用该文件的服务台或技术支持。[8] 自 2018 年 6 月 18 日起，每个压缩包还附带三个参考文件：其他名称（Other Name）、执业地点（Practice Location）和端点（Endpoint）。[8] 对于已停用的 NPI，文件仅披露其 NPI 号码和停用日期。[8]

截至 2026-11-21，NPI 文件页面仅提供版本 2 文件。NPPES 已于 2026 年 3 月 3 日起终止对月度和周度文件版本 1 的支持，版本 2 扩展了名字（First Name）和法定企业名称（Legal Business Name）字段的字符长度上限。[7] 2026-11-21 当天，该页面列出了日期为 2026 年 11 月 9 日的月度文件（1,079.11 MB 的 ZIP 压缩包）、同日期的月度停用更新文件，以及涵盖 2026 年 11 月 2 日至 8 日和 11 月 9 日至 15 日的周度更新文件。[7]

## NPPES 与 NPI 注册库不予核验的内容

NPPES 与 NPI 注册库不核验医疗服务提供者的执业执照或资质。注册库搜索页面、API 帮助页面和 NPI 文件页面均载有相同的 CMS 声明：“Issuance of an NPI does not ensure or validate that the Health Care Provider is Licensed or Credentialed.”（颁发 NPI 并不保证或验证该医疗服务提供者持有执业执照或资质。）[5][6][7] 注册库与可下载文件中的数据均由医疗服务提供者本人、其代理人或机构授权官员向 NPPES 申报，CMS 要求提供者自行更正错误信息。[8]

NPPES 中若干看似资质证明的字段同样由提供者自行填报。针对个人提供者公开的数据项包括执业执照号和发证州代码。[9] 分类代码由提供者自主选择，且 NUCC 声明执业许可范围不属于分类代码集的管辖范畴。[11] NPI 号码本身也不包含有关专业或所在地的任何信息。[1]

部分 NPPES 数据永不公开。社会安全号码（SSN）、美国国税局（IRS）个人纳税人识别号（ITIN）以及出生日期被认定不属于 FOIA 规定的可披露范围，因此不予发布。[9] 反之，持有有效 NPI 的医疗服务提供者无法选择退出公开或隐藏其记录。[8] 2004 年最终规则序言还指出，编号系统不会维护各类 NPI 之间的关联关系，也不会收录所有权和公司注册信息。[2]

## 常见问题

### 什么是 NPI 号码？

国家医疗服务提供者标识符（NPI）是美国依据 HIPAA 为医疗服务提供者制定的标准唯一标识符。它是一个 10 位数字，末位为校验位，不包含有关提供者的编码信息，由美国医疗保险和医疗补助服务中心（CMS）的编号系统 NPPES 负责分配。 [1][3][6]

### 拥有 NPI 是否意味着医疗服务提供者持有执业执照？

不是。CMS 在 NPI 注册库上明确指出，颁发 NPI 并不保证或验证医疗服务提供者持有执业执照或相关资质。NPPES 数据由提供者自行申报，分类代码也由提供者自主选择。 [6][8][11]

### NPI 校验位是如何计算的？

第 10 位是采用 Luhn 公式（模 10“double-add-double”）计算的校验位，计算时假定号码前带有前缀 80840。当未书写该前缀时，需在 Luhn 求和结果中加上常数 24。在 CMS 示例中，123456789 得出校验位 3，从而构成 NPI 1234567893。 [4]

### 类型 1 NPI 与类型 2 NPI 有什么区别？

实体类型 1 NPI 颁发给提供医疗服务的个人，包括仅可获取一个 NPI 的独资经营者。实体类型 2 NPI 颁发给医院、联合诊所、药房等机构及其子部门。 [10]

### NPI 注册库 API 有哪些限制？

截至 2026-11-21，该 API 仅支持版本 2.1，每次请求最多返回 200 条结果，且 skip 参数最多可跳过 1,000 条记录，因此每组搜索条件最多可获取 1,200 条记录。CMS 指引批量用户改用可下载的数据分发文件。 [5][6]

### NPPES 公开数据的更新频率是多少？

CMS 说明 NPI 注册库每日更新，API 也每天从 NPPES 获取数据。可下载的全量替换文件每月发布一次，增量文件每周发布一次。 [5][8]

## 可引用的句子

- 国家医疗服务提供者标识符（NPI）是一个 10 位数字标识符，第 10 位为校验位。 [3]
- NPI 校验位采用 Luhn 公式按号码前带有前缀 80840 的方式计算。 [4]
- CMS 声明颁发 NPI 并不保证或验证医疗服务提供者持有执业执照或资质。 [6]
- 截至 2026-11-21，NPPES NPI 注册库 API 仅支持版本 2.1。 [5]
- 截至 2026-11-21，NPPES NPI 注册库 API 每次请求最多返回 200 条结果。 [5]
- NPPES 每月发布一次全量替换 NPI 文件，每周发布一次增量 NPI 文件。 [8]
- NPI 最终规则于 2004 年 1 月 23 日刊载于《联邦公报》第 69 FR 3434 页。 [2]
- NPPES 保存的社会安全号码、IRS 个人纳税人识别号和出生日期不向公众公开。 [9]

## 时间线

- 2004-01-23: 美国卫生与公众服务部发布 NPI 最终规则（69 FR 3434），采纳国家医疗服务提供者标识符作为医疗服务提供者的标准唯一健康标识符。 [2]
- 2005-05-23: NPI 最终规则生效，医疗服务提供者可开始申请 NPI。 [2]
- 2006-05-01: 用于批量编号的电子文件交换（Electronic File Interchange）流程正式启用。 [9]
- 2007-05-23: 受覆盖医疗服务提供者、医疗信息清算机构以及小型健康保险计划以外的健康保险计划的合规截止日期。 [2]
- 2007-05-30: CMS 在《联邦公报》发布 NPPES 数据分发通告（CMS-6060-N）。 [9]
- 2008-05-23: 小型健康保险计划的合规截止日期。 [2]
- 2018-06-18: ZIP 格式的 NPPES 下载文件开始包含 Other Name、Practice Location 和 Endpoint 三个参考文件。 [8]
- 2024-06-25: NPPES 开始限制每小时可完成的 NPI 注册库查询次数。 [6]
- 2026-03-03: NPPES 终止对月度和周度可下载文件版本 1 的支持。 [7]

## 来源

1. National Provider Identifier Standard (NPI) | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/regulations-and-guidance/administrative-simplification/nationalprovidentstand (访问于 2026-11-21; tier 1: government or public registry)
2. HIPAA Administrative Simplification: Standard Unique Health Identifier for Health Care Providers. Federal Register, Department of Health and Human Services. 发布于 2004-01-23. https://www.federalregister.gov/documents/2004/01/23/04-1149/hipaa-administrative-simplification-standard-unique-health-identifier-for-health-care-providers (访问于 2026-11-21; tier 1: government or public registry)
3. 45 CFR Part 162 Subpart D: Standard Unique Health Identifier for Health Care Providers. Electronic Code of Federal Regulations (eCFR). https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-162/subpart-D (访问于 2026-11-21; tier 1: government or public registry)
4. Requirements for National Provider Identifier (NPI) and NPI Check Digit. Centers for Medicare & Medicaid Services. 发布于 2004-01-23. https://www.cms.gov/Regulations-and-Guidance/Administrative-Simplification/NationalProvIdentStand/Downloads/NPIcheckdigit.pdf (访问于 2026-11-21; tier 1: government or public registry)
5. NPPES NPI Registry: NPPES API Help. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/api-page (访问于 2026-11-21; tier 1: government or public registry)
6. NPPES NPI Registry: Search NPI Records. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/search (访问于 2026-11-21; tier 1: government or public registry)
7. NPI Files. Centers for Medicare & Medicaid Services. https://download.cms.gov/nppes/NPI_Files.html (访问于 2026-11-21; tier 1: government or public registry)
8. Data Dissemination | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/data-dissemination (访问于 2026-11-21; tier 1: government or public registry)
9. HIPAA Administrative Simplification: National Plan and Provider Enumeration System Data Dissemination. Federal Register, Centers for Medicare & Medicaid Services. 发布于 2007-05-30. https://www.federalregister.gov/documents/2007/05/30/07-2651/hipaa-administrative-simplification-national-plan-and-provider-enumeration-system-data-dissemination (访问于 2026-11-21; tier 1: government or public registry)
10. CMS-10114 National Provider Identifier (NPI) Application/Update Form. Centers for Medicare & Medicaid Services. https://www.cms.gov/Medicare/CMS-Forms/CMS-Forms/downloads/CMS10114.pdf (访问于 2026-11-21; tier 1: government or public registry)
11. National Uniform Claim Committee - Provider Taxonomy. National Uniform Claim Committee. https://www.nucc.org/index.php/code-sets-mainmenu-41/provider-taxonomy-mainmenu-40 (访问于 2026-11-21; tier 3: official site)
12. How to Apply | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/how-apply (访问于 2026-11-21; tier 1: government or public registry)

## 引用本页

Mimirwiki. "NPPES 与国家医疗服务提供者标识符（NPI）." 版本 11f358bf, 2026-11-24. https://mimirwiki.com/zh/wiki/nppes-npi-registry
