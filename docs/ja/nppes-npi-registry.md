---
title: "NPPESと全米医療提供者識別子（NPI）"
subtitle: "米国の医療提供者に10桁の識別番号を付与し、NPIレジストリで公開する連邦システム"
canonical_url: https://mimirwiki.com/ja/wiki/nppes-npi-registry
language: ja
page_class: anchor
revision_sha256: 3416bcbdfc7673d98d729a9812956548ca6cee1ab795d6a19f2933047e528ab3
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/nppes-npi-registry.md
  txt: https://mimirwiki.com/ja/wiki/nppes-npi-registry.txt
  json: https://mimirwiki.com/ja/wiki/nppes-npi-registry.json
  jsonld: https://mimirwiki.com/ja/wiki/nppes-npi-registry.jsonld
translations:
  en: https://mimirwiki.com/wiki/nppes-npi-registry
  ko: https://mimirwiki.com/ko/wiki/nppes-npi-registry
  zh: https://mimirwiki.com/zh/wiki/nppes-npi-registry
  es: https://mimirwiki.com/es/wiki/nppes-npi-registry
---

# NPPESと全米医療提供者識別子（NPI）

> NPPESは、米国メディケア・メディケイド・サービス・センター（CMS）が医療提供者向けの10桁のHIPAA標準識別子である全米医療提供者識別子（NPI）を付与するシステムである。公開データはNPIレジストリでの検索、読み取り専用APIによる照会、および月次・週次ファイルのダウンロードで利用できる。NPIの保有は、医療提供者が免許や資格を有していることの確認にはならない。

NPPES（National Plan and Provider Enumeration System）は、米国のメディケア・メディケイド・サービス・センター（Centers for Medicare & Medicaid Services、CMS）が医療提供者に全米医療提供者識別子（National Provider Identifier、NPI）を付与するためのシステムである。NPIは1996年医療保険の携行性と責任に関する法律（Health Insurance Portability and Accountability Act of 1996、HIPAA）に基づき採用された医療提供者向けの標準固有識別子であり、10桁目をチェックディジットとする10桁の数字で構成され、番号自体には医療提供者に関する情報は符号化されていない。CMSは各NPPESレコードのうち公開対象となる部分を、NPIレジストリ検索サイト、読み取り専用API、およびダウンロード可能なファイルを通じて公開している。CMSは、NPIの発行が医療提供者の免許や資格を保証または検証するものではないと明記している。

**別名:** NPPES, National Plan and Provider Enumeration System, NPI, National Provider Identifier, NPI Registry, NPPES NPI Registry, NPIレジストリ, 全米医療提供者識別子

## 主要な事実

- **識別子の形式:** 10桁の数字（最終桁はルーン・チェックディジット） [4]
- **運営機関:** メディケア・メディケイド・サービス・センター（CMS） [6]
- **公開APIバージョン:** 2.1（バージョン1.0および2.0は廃止） (時点 2026-11-21) [5]
- **API取得上限:** 1リクエストあたり200件、skip使用時は1検索あたり1,200件 (時点 2026-11-21) [5]
- **一括ファイル更新頻度:** 完全置換ファイルは月次、差分ファイルは週次 (時点 2026-11-21) [8]

## ファクトシート

- **正式名称:** National Plan and Provider Enumeration System [6]
- **運営機関:** メディケア・メディケイド・サービス・センター（CMS） [6]
- **発行識別子:** 全米医療提供者識別子（NPI） [1]
- **識別子の形式:** 10桁の数字（10桁目はチェックディジット） [3]
- **チェックディジット方式:** ルーン（Luhn）公式（モジュラス10「double-add-double」） [4]
- **法的根拠:** HIPAA行政簡素化規定、45 CFR Part 162 Subpart D [2]
- **最終規則:** 69 FR 3434（2004-01-23公示） [2]
- **エンティティ種別:** タイプ1（個人）、タイプ2（組織） [10]
- **公開検索サイト:** NPIレジストリ（npiregistry.cms.hhs.gov） [6]
- **API:** 読み取り専用JSON API、バージョン2.1（2026-11-21現在） [5]
- **一括データ:** 月次完全置換ファイル、週次差分ファイル、月次無効化ファイル（いずれもバージョン2、2026-11-21現在） [7]
- **専門分野コード体系:** 医療提供者分類コード（Health Care Provider Taxonomy）、全米統一請求委員会（NUCC）が管理 [11]

## 全米医療提供者識別子（NPI）の形式とチェックディジット

NPPESを通じて付与される全米医療提供者識別子（NPI）は、連邦規則において10桁目をチェックディジットとする10桁の数値識別子であり、医療提供者に関する意味情報（インテリジェンス）を持たないものと定義されている。[3] CMSはNPIを「意味情報を持たない（intelligence-free）」番号であると説明しており、医療提供者が居住する州や専門診療科といった情報は数字に符号化されていない。[1]

2004年1月23日付のCMS要件文書は、NPIが9桁の数字に続いて1桁のチェックディジットで構成されること、および他のカード発行者識別子との衝突を避けるため当初は先頭桁が1または2の番号として発行されることを定めている。[4] チェックディジットは、モジュラス10の「double-add-double」方式によるルーン（Luhn）公式で算出される。NPIを標準健康識別カードのカード発行者識別子として使用する際は、先頭にプレフィックス80840（80は医療・健康分野、840は米国を示す）が付与され、チェックディジットは常にこのプレフィックスが存在するものとして計算される。プレフィックスを付けずにNPIを記述する場合は、ルーン合計に定数24を加算することで同じ計算を行う。[4] CMSの計算例では、9桁の識別子123456789からチェックディジット3が得られ、NPIは1234567893となる。[4]

CMS文書に定められた形式規則は以下の通りである。[4]

| 項目 | 値 |
| --- | --- |
| 桁数 | 数字10桁 |
| 構成 | 9桁の識別子と1桁のチェックディジット |
| 初期発行時の先頭桁 | 1または2 |
| チェックディジット方式 | ルーン（Luhn）公式（モジュラス10「double-add-double」） |
| カード発行者プレフィックス | 80840 |
| プレフィックス省略時の加算定数 | 24 |

## 全米医療提供者識別子（NPI）の取得・使用義務対象

全米医療提供者識別子（NPI）は、すべての適用対象医療提供者（covered health care provider）が取得しなければならない。NPI最終規則は、保健福祉省長官が標準を採択した取引に関連して健康情報を電子的に送信する医療提供者を適用対象医療提供者と位置づけている。[2] 45 CFR 162.410に基づき、適用対象医療提供者は標準取引において自己を識別するためにNPIを使用すること、標準取引のためにNPIを必要とする機関からの要請に応じてNPIを開示すること、および必須登録情報の変更から30日以内に変更を届け出ることが義務づけられている。[3] 医療保険者（health plan）および医療情報クリアリングハウス（health care clearinghouse）は、NPIが付与されたすべての医療提供者について標準取引でそのNPIを使用しなければならず、医療保険者は既にNPIを持つ医療提供者に対して別のNPIを取得するよう要求することはできない。[3]

適用対象事業体（covered entity）ではない医療提供者もNPIを取得することができる。[3] さらに規則は、適用対象医療提供者である組織に対し、所属メンバー、従業員、または契約者である処方者が自ら適用対象事業体でない場合であっても、NPPESからNPIを取得させるよう義務づけている。[3] 最終規則の前文では、必ずしも適用対象取引を行わないものの医療を提供する者として、正看護師、歯科衛生士、技師などを例示し、これらもNPIの取得資格を有すると説明している。[2]

NPI最終規則は2004年1月23日に公示され、医療提供者が申請を開始できる初日である2005年5月23日に発効した。適用対象医療提供者、医療情報クリアリングハウス、および小規模医療保険者を除く医療保険者の遵守期限は2007年5月23日、小規模医療保険者の遵守期限は2008年5月23日であった。[2] 最終規則の前文はNPIを永続的な識別子と位置づけている。個人にとっては永久的な番号として意図されており、組織についても所有権、名称、所在地、または分類コードの変更に伴って新たなNPIを取得する必要はない。[2] 無効化されたNPIが他の医療提供者に再割り当てされることはない。[3]

## NPPESのエンティティ種別：タイプ1 NPIとタイプ2 NPI

NPPESは、すべての全米医療提供者識別子（NPI）をNPI申請時に選択される2種類のエンティティ種別のいずれかで付与する。エンティティタイプ1は、医師、歯科医師、看護師、カイロプラクター、薬剤師、理学療法士など、医療を提供する個人を対象とする。エンティティタイプ2は、病院、在宅医療機関、救急搬送会社、グループ診療所、医療維持機構（HMO）、耐久医療機器供給業者、薬局など、医療の提供または医療用品の供給を行う組織を対象とする。[10]

CMS-10114申請書では、個人事業主（sole proprietorship）はエンティティタイプ1の個人に該当し取得できるNPIは1つのみである一方、法人化した個人は個人としてタイプ1 NPIを、法人としてタイプ2 NPIをそれぞれ保有できると明記されている。[10] また組織は、サブパート（subpart）ごとに個別のNPIを取得することもできる。申請書はサブパートを、異なる所在地にあったり異なる種類の医療を提供したりする組織医療提供者の構成単位と説明している。[3][10] NPIレジストリAPIでは、これら2つの種別は `NPI-1` および `NPI-2` の値として表現される。[5]

医療提供者がNPIを申請する方法は3つある。NPPESのオンライン申請を利用する方法、医療提供者の同意を得て申請データを一括提出する電子ファイル交換（Electronic File Interchange）組織を通じた方法、および紙の申請書CMS-10114をNPI付番機関（NPI Enumerator）へ郵送する方法である。[12] 主たる医療提供者分類コード（Healthcare Provider Taxonomy code）の記載は必須であり、最大15件の分類コードを登録できる。[9] 分類コード体系は全米統一請求委員会（National Uniform Claim Committee、NUCC）が管理しており、各コードは10文字の英数字で構成され、提供者グループ、分類、専門領域の3階層に整理されている。[11]

## NPIレジストリ検索とNPPES API（バージョン2.1）

npiregistry.cms.hhs.govで提供されているNPIレジストリは、CMSにより有効な全米医療提供者識別子（NPI）レコードすべての無料ディレクトリとして位置づけられている。NPIレコードのうちCMSが公的関連性を有すると判断した部分、すなわち医療提供者の氏名・名称、専門分野（分類コード）、診療場所の住所などが表示される。[6] レコードはNPI番号、NPI種別、分類コード説明、医療提供者名または組織名、権限ある担当者（Authorized Official）名、市区町村、州、国、郵便番号で検索できる。検索結果は一致したレコードのうち最初の2,100件までしか返されない。2024年6月25日以降、NPPESは1時間あたりに完了できるレジストリ検索の回数を制限しているが、検索ページに具体的な時間あたり上限数は記載されておらず、同ページでは一括照会にはデータ配布ファイルを使用するよう案内している。[6]

NPPES APIはレジストリデータをJSON形式で返す読み取り専用インターフェースであり、NPPESから毎日データを取得している。[5] 2026-11-21時点でサポートされているのはバージョン2.1のみである。CMSはバージョン1.0および2.0を廃止し、バージョン指定フラグのないリクエストは動作しなくなったと述べており、バージョン2.1の廃止予定日は「TBD（未定）」としている。エンドポイントは `https://npiregistry.cms.hhs.gov/api/?version=2.1` である。[5] APIヘルプページに記載されているリクエスト制限は以下の通りである。[5]

| 項目 | 2026-11-21時点の値 |
| --- | --- |
| サポート対象バージョン | 2.1 |
| `limit` のデフォルト値 | 10 |
| `limit` の最大値 | 1リクエストあたり200件 |
| `skip` の最大値 | 1,000レコード |
| 1組の検索条件での最大取得件数 | 6回のリクエストにわたり1,200件 |
| レスポンス形式 | JSON |

バージョン2.1のドキュメントに記載されている検索パラメータには、`number`、`enumeration_type`、`taxonomy_description`、`first_name`、`last_name`、`organization_name`、`city`、`state`、`postal_code`、`country_code`、`limit`、`skip` が含まれ、APIキーや認証パラメータは記載されていない。名称および郵便番号のフィールドでは、2文字以上の入力に続けて末尾ワイルドカードを使用できる。[5] JSONレスポンスには、先頭要素が主たる診療場所、2番目の要素が郵送先住所となるaddresses配列、最大15件のtaxonomies配列、最大50件のother identifiers配列のほか、その他の名称、エンドポイント、追加の診療場所を格納する配列が含まれる。[5]

## NPPESダウンロード用データ配布ファイル

NPPESのデータはダウンロード可能なファイルとしても公開されている。CMSは2007年9月より、情報自由法（Freedom of Information Act、FOIA）に基づき開示可能なNPPES医療提供者データを2つの形式、すなわち毎日更新される照会専用データベースのNPIレジストリとダウンロード用ファイルで公開している。CMSはデータの閲覧やダウンロードに料金を課していない。[8] 提供されるファイルは、月次の完全置換NPIファイル、週次の差分NPIファイル、および完全置換NPI無効化ファイルの3種類である。週次ファイルには新規付与されたNPI、更新情報、新規無効化されたNPIなど該当週のデータのみが含まれ、最新の月次ファイルと組み合わせて使用することが前提となっている。[8]

月次ダウンロードファイルはZIPアーカイブであり、readme文書、コード値文書、ヘッダーファイル、およびすべての値が二重引用符で囲まれたカンマ区切りデータファイルが収められている。CMSはデータファイルのサイズが4 GBを超えると注記しており、ダウンロードや利用に関するヘルプデスクや技術サポートは提供していない。[8] 2018年6月18日以降、各アーカイブにはOther Name（その他名称）、Practice Location（診療場所）、Endpoint（エンドポイント）の3つの参照ファイルも含まれている。[8] 無効化されたNPIについては、ファイルにはNPI番号と無効化日のみが開示される。[8]

2026-11-21現在、NPI Filesページではバージョン2のファイルのみが提供されている。NPPESは2026年3月3日をもって月次および週次ファイルのバージョン1のサポートを終了しており、バージョン2ではFirst Name（名）およびLegal Business Name（法的事業者名）フィールドの文字数上限が拡張されている。[7] 2026-11-21時点で同ページには、2026年11月9日付の月次ファイル（1,079.11 MBのZIP）、同日付の月次無効化更新ファイル、および2026年11月2日〜8日と11月9日〜15日を対象とする週次更新ファイルが掲載されていた。[7]

## NPPESとNPIレジストリが検証しない事項

NPPESおよびNPIレジストリは、医療提供者の免許や資格を検証しない。レジストリ検索ページ、APIヘルプページ、およびNPI Filesページのすべてに、CMSによる同一の注意書き「Issuance of an NPI does not ensure or validate that the Health Care Provider is Licensed or Credentialed.（NPIの発行は、当該医療提供者が免許または資格を有していることを保証または検証するものではない）」が掲載されている。[5][6][7] レジストリやダウンロード用ファイルのデータは、医療提供者本人、代理人、または組織の権限ある担当者がNPPESに申告した内容であり、CMSは誤った情報がある場合は医療提供者に訂正を求めている。[8]

資格証明のように見えるNPPESの項目のいくつかも、医療提供者自身が入力したものである。個人医療提供者について開示されるデータ項目には、免許番号と免許発行州コードが含まれる。[9] 分類コードは医療提供者が自己選択するものであり、NUCCは免許の適用範囲は分類コード体系の管轄外であると明記している。[11] NPI番号自体にも、専門分野や所在地に関する情報は含まれていない。[1]

NPPESデータの一部は一切公開されない。社会保障番号、内国歳入庁（IRS）の個人納税者識別番号（ITIN）、および生年月日はFOIAに基づく開示対象外と判断されており、公開されない。[9] 一方で、有効なNPIを持つ医療提供者は、開示からのオプトアウトや自己レコードの非公開化を行うことはできない。[8] また、2004年の最終規則の前文では、各種NPI間の関連づけは付番システム内で管理されず、所有権や法人設立に関する情報もシステムに収録されないことが明記されている。[2]

## よくある質問

### NPI番号とは何ですか？

全米医療提供者識別子（NPI）は、米国の医療提供者向けにHIPAAで定められた標準固有識別子です。最終桁をチェックディジットとする10桁の数字で、医療提供者に関する情報は符号化されておらず、メディケア・メディケイド・サービス・センター（CMS）の付番システムであるNPPESを通じて付与されます。 [1][3][6]

### NPIを持っていれば、その医療提供者に免許があるということですか？

いいえ。CMSはNPIレジストリ上で、NPIの発行は医療提供者が免許や資格を有していることを保証または検証するものではないと明記しています。NPPESのデータは医療提供者自身が申告したものであり、分類コードも自己選択によるものです。 [6][8][11]

### NPIのチェックディジットはどのように計算されますか？

10桁目は、番号の先頭にプレフィックス80840が付いているものとみなしてルーン（Luhn）公式（モジュラス10「double-add-double」）で算出されるチェックディジットです。プレフィックスを記述しない場合は、ルーン合計に定数24を加算します。CMSの計算例では、123456789からチェックディジット3が得られ、NPIは1234567893になります。 [4]

### タイプ1 NPIとタイプ2 NPIの違いは何ですか？

エンティティタイプ1のNPIは医療を提供する個人に発行され、個人事業主もこれに該当し、取得できるNPIは1つのみです。エンティティタイプ2のNPIは、病院、グループ診療所、薬局などの組織およびそのサブパートに発行されます。 [10]

### NPIレジストリAPIの制限は何ですか？

2026-11-21時点で、APIがサポートしているのはバージョン2.1のみであり、1リクエストあたりの最大返却件数は200件、skipパラメータでスキップできる上限は1,000レコードで、1組の検索条件あたり最大1,200レコードまで取得できます。CMSは一括利用者に対し、ダウンロード用のデータ配布ファイルを使用するよう案内しています。 [5][6]

### NPPESの公開データはどのくらいの頻度で更新されますか？

CMSはNPIレジストリが毎日更新されると説明しており、APIもNPPESから毎日データを取得しています。ダウンロード用の完全置換ファイルは月次、差分ファイルは週次で発行されます。 [5][8]

## 引用できる文

- 全米医療提供者識別子（NPI）は、10桁目をチェックディジットとする10桁の数値識別子である。 [3]
- NPIのチェックディジットは、先頭にプレフィックス80840が付いているものとみなしてルーン（Luhn）公式で算出される。 [4]
- CMSは、NPIの発行が医療提供者の免許や資格を保証または検証するものではないと明記している。 [6]
- 2026-11-21時点で、NPPES NPIレジストリAPIはバージョン2.1のみをサポートしている。 [5]
- 2026-11-21時点で、NPPES NPIレジストリAPIのクエリは1リクエストあたり最大200件の結果を返す。 [5]
- NPPESは完全置換NPIファイルを月次で、差分NPIファイルを週次で公開している。 [8]
- NPI最終規則は2004年1月23日に連邦官報（69 FR 3434）に公示された。 [2]
- NPPESが保有する社会保障番号、IRS個人納税者識別番号、および生年月日は一般には公開されない。 [9]

## 年表

- 2004-01-23: 米国保健福祉省がNPI最終規則（69 FR 3434）を公示し、全米医療提供者識別子（NPI）を医療提供者の標準固有健康識別子として採択した。 [2]
- 2005-05-23: NPI最終規則が発効し、医療提供者によるNPIの申請受付が開始された。 [2]
- 2006-05-01: 一括付番のための電子ファイル交換（Electronic File Interchange）プロセスが利用可能になった。 [9]
- 2007-05-23: 適用対象医療提供者、医療情報クリアリングハウス、および小規模医療保険者を除く医療保険者の遵守期限が到来した。 [2]
- 2007-05-30: CMSがNPPESデータ配布告示（CMS-6060-N）を連邦官報に公示した。 [9]
- 2008-05-23: 小規模医療保険者の遵守期限が到来した。 [2]
- 2018-06-18: ZIP形式のNPPESダウンロードファイルに、Other Name、Practice Location、Endpointの各参照ファイルが含まれるようになった。 [8]
- 2024-06-25: NPPESが1時間あたりに完了できるNPIレジストリ検索回数の制限を開始した。 [6]
- 2026-03-03: NPPESが月次および週次ダウンロードファイルのバージョン1のサポートを終了した。 [7]

## 出典

1. National Provider Identifier Standard (NPI) | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/regulations-and-guidance/administrative-simplification/nationalprovidentstand (閲覧 2026-11-21; tier 1: government or public registry)
2. HIPAA Administrative Simplification: Standard Unique Health Identifier for Health Care Providers. Federal Register, Department of Health and Human Services. 公開 2004-01-23. https://www.federalregister.gov/documents/2004/01/23/04-1149/hipaa-administrative-simplification-standard-unique-health-identifier-for-health-care-providers (閲覧 2026-11-21; tier 1: government or public registry)
3. 45 CFR Part 162 Subpart D: Standard Unique Health Identifier for Health Care Providers. Electronic Code of Federal Regulations (eCFR). https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-162/subpart-D (閲覧 2026-11-21; tier 1: government or public registry)
4. Requirements for National Provider Identifier (NPI) and NPI Check Digit. Centers for Medicare & Medicaid Services. 公開 2004-01-23. https://www.cms.gov/Regulations-and-Guidance/Administrative-Simplification/NationalProvIdentStand/Downloads/NPIcheckdigit.pdf (閲覧 2026-11-21; tier 1: government or public registry)
5. NPPES NPI Registry: NPPES API Help. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/api-page (閲覧 2026-11-21; tier 1: government or public registry)
6. NPPES NPI Registry: Search NPI Records. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/search (閲覧 2026-11-21; tier 1: government or public registry)
7. NPI Files. Centers for Medicare & Medicaid Services. https://download.cms.gov/nppes/NPI_Files.html (閲覧 2026-11-21; tier 1: government or public registry)
8. Data Dissemination | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/data-dissemination (閲覧 2026-11-21; tier 1: government or public registry)
9. HIPAA Administrative Simplification: National Plan and Provider Enumeration System Data Dissemination. Federal Register, Centers for Medicare & Medicaid Services. 公開 2007-05-30. https://www.federalregister.gov/documents/2007/05/30/07-2651/hipaa-administrative-simplification-national-plan-and-provider-enumeration-system-data-dissemination (閲覧 2026-11-21; tier 1: government or public registry)
10. CMS-10114 National Provider Identifier (NPI) Application/Update Form. Centers for Medicare & Medicaid Services. https://www.cms.gov/Medicare/CMS-Forms/CMS-Forms/downloads/CMS10114.pdf (閲覧 2026-11-21; tier 1: government or public registry)
11. National Uniform Claim Committee - Provider Taxonomy. National Uniform Claim Committee. https://www.nucc.org/index.php/code-sets-mainmenu-41/provider-taxonomy-mainmenu-40 (閲覧 2026-11-21; tier 3: official site)
12. How to Apply | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/how-apply (閲覧 2026-11-21; tier 1: government or public registry)

## このページを引用する

Mimirwiki. "NPPESと全米医療提供者識別子（NPI）." 版 3416bcbd, 2026-11-24. https://mimirwiki.com/ja/wiki/nppes-npi-registry
