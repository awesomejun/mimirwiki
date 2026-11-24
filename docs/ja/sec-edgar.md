---
title: "SEC EDGAR"
subtitle: "米国証券取引委員会の電子開示書類提出・公開システム"
canonical_url: https://mimirwiki.com/ja/wiki/sec-edgar
language: ja
page_class: anchor
revision_sha256: 066ed7b5442c74fbf7902b59a655ac8b306d6a3bcb8b9d796cc1cc5c7cf167a0
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/sec-edgar.md
  txt: https://mimirwiki.com/ja/wiki/sec-edgar.txt
  json: https://mimirwiki.com/ja/wiki/sec-edgar.json
  jsonld: https://mimirwiki.com/ja/wiki/sec-edgar.jsonld
translations:
  en: https://mimirwiki.com/wiki/sec-edgar
  ko: https://mimirwiki.com/ko/wiki/sec-edgar
  zh: https://mimirwiki.com/zh/wiki/sec-edgar
---

# SEC EDGAR

> EDGAR（Electronic Data Gathering, Analysis, and Retrieval）は、Form 10-K、10-Q、8-Kなどの証券開示書類を提出するための米国証券取引委員会（SEC）の主要システムである。公開データベースは無料で検索でき、各提出者は中央インデックスキー（CIK）によって識別される。data.sec.govのJSON APIはAPIキー不要で利用でき、自動アクセスは毎秒10リクエストに制限されている。

EDGAR（Electronic Data Gathering, Analysis, and Retrieval）は、企業などの提出者が1933年証券法、1934年証券取引所法、1939年信託証書法および1940年投資会社法に基づく書類を提出するための、米国証券取引委員会（SEC）の主要システムである。EDGARの公開データベースへのアクセスは無料である。EDGARは各提出者に中央インデックスキー（Central Index Key、CIK）を、受理された各提出書類に受付番号（accession number）を割り当てる。また、SECは提出履歴および抽出されたXBRL財務データをdata.sec.gov上のREST APIを通じてJSON形式で公開しており、これらのAPIは認証やAPIキーを必要としない。

**別名:** EDGAR, Electronic Data Gathering, Analysis, and Retrieval, SEC EDGARデータベース, EDGAR提出システム, data.sec.gov

## 主要な事実

- **運営機関:** 米国証券取引委員会（EDGARビジネスオフィス） [1]
- **提出者識別子:** 中央インデックスキー（CIK）。API URLでは先頭を0で埋めた10桁表記 [2]
- **リクエスト速度制限:** 利用者あたり毎秒10リクエスト (時点 2026-11-21) [3]
- **API認証:** なし（APIキー不要） (時点 2026-11-21) [2]
- **全文検索の対象範囲:** 2001年以降の電子提出書類 (時点 2026-11-21) [6]

## ファクトシート

- **正式名称:** Electronic Data Gathering, Analysis, and Retrieval [1]
- **運営機関:** 米国証券取引委員会（SEC） [1]
- **担当部署:** EDGARビジネスオフィス（EDGAR Business Office） [1]
- **提出者識別子:** 中央インデックスキー（CIK） [3]
- **提出書類識別子:** 受付番号（accession number）。例：0001193125-15-118890 [3]
- **一般公開:** 無料 [1]
- **データAPI:** JSONを返すdata.sec.gov REST API：submissions、company concept、company facts、frames [2]
- **API認証:** 不要（2026-11-21時点） [2]
- **速度制限:** 毎秒10リクエスト（2026-11-21時点） [3]
- **提出受付時間:** 営業日 米国東部時間 午前6時～午後10時 [3]
- **全文検索の対象範囲:** 2001年以降の電子提出書類 [6]
- **提出者ログイン:** 多要素認証を伴うLogin.govの個人アカウント認証情報 [7]

## SEC EDGARの概要と提出対象者

EDGAR（Electronic Data Gathering, Analysis, and Retrieval）システムは、1933年証券法、1934年証券取引所法、1939年信託証書法および1940年投資会社法に基づいて企業などが書類を提出するための主要システムとしてSECが位置づけているものである。[1] 2025年11月28日に最終確認されたSECのページによると、EDGARは1日あたり約4,700件の提出書類を処理し、年間3,000テラバイトのデータを一般に向けて配信しており、年間平均40,000件の新規提出者を受け入れている。[1] EDGARビジネスオフィス（EDGAR Business Office）が同システムの業務上の責任部署であり、ガバナンス、戦略計画および提出者サポートを担っている。[1]

SECは、米国内外の企業がいずれも登録届出書、定期報告書その他の書式をEDGARを通じて電子的に提出しなければならず、その情報は誰でも無料で閲覧・ダウンロードできるとしている。[3] 公開データベースには企業による提出書類のほか、ミューチュアル・ファンド、上場投資信託（ETF）、変額年金および個人が提出した情報も収録されている。[1] EDGARは月曜日から金曜日までの各営業日、米国東部時間の午前6時から午後10時まで新規の提出を受け付けている。米国東部時間の午後5時30分以降（所有報告書であるForm 3、4および5については午後10時以降）に開始された一部の提出は、翌営業日に公開される。[3]

SECは1983年に電子開示システムの開発を開始し、1992年7月15日に実運用版EDGARシステムを任意参加の提出者に公開した。1993年2月23日に発出された規則によって電子提出が義務化され、1993年4月26日から段階的導入が始まった。また、外国発行体にEDGARを通じた提出を義務づける規則は2002年11月4日に発効した。[9] SECのデータアクセス案内ページは、EDGARが1994/1995年に開始され、そのインデックスファイルには1994年第3四半期以降のすべての公開提出書類が掲載されていると記載している。[3]

## EDGARの識別子：CIKと受付番号

EDGARは、提出者がSECへの書類提出のために登録する際、中央インデックスキー（Central Index Key、CIK）と呼ばれる固有の数値識別子を各提出者に割り当てる。CIK番号は提出者固有のものとして維持され、再利用されない。[3] 提出者には企業、ファンドおよび個人が含まれ、企業やファンドが名称を変更した場合には、単一のCIKに複数の名称が紐づくことがある。[3] data.sec.govのAPI URLでは、CIKは先頭を0で埋めた10桁の数字として記述される。[2]

受理された各提出書類には、EDGARが自動的に割り当てる固有の識別子である受付番号（accession number）が付与される。SECの例である0001193125-15-118890では、最初の10桁が提出を行った主体（企業本人または第三者の提出代行業者）のCIK、次の2桁が年、最後の数字列がそのCIKからの提出件数の連番を表す。この連番は通常、暦年の開始時にリセットされるが、必ずしも毎回リセットされるわけではない。[3] 2種類の識別子の形式は以下の通りである。[2][3]

| 識別子 | SEC文書における表記形式 | 識別対象 |
| --- | --- | --- |
| 中央インデックスキー（CIK） | API URLでは`CIK##########`（先頭を0で埋めた10桁） | 提出者（企業、ファンドまたは個人） |
| 受付番号（accession number） | `0001193125-15-118890`：提出主体のCIK、2桁の年、連番 | 受理された1件の提出書類 |

提出書類のファイルは、両方の識別子から構成されるパス配下に保存される。SECの例であるパス`/Archives/edgar/data/1122304/000119312515118890/`では、最初のディレクトリがCIKディレクトリ、2番目のディレクトリがハイフンを除いた受付番号であり、この形式は2000年5月26日以降の提出書類で利用できる。CIKディレクトリおよび受付番号ディレクトリの一覧閲覧は許可されているが、親ディレクトリである`/Archives/edgar/data/`は一覧閲覧できない。[3] また、SECはティッカーシンボル、CIKおよび企業名を対応づけた`company_tickers.json`を公開しており、定期的に更新しているものの、正確性や網羅性は保証していない。[3]

## 主なEDGAR書式の種類

EDGARは各提出書類を書式タイプ（form type）で識別し、10-K/Aのように書式タイプの末尾に「/A」が付く場合は訂正書類を意味する。[5] 以下の書式タイプは、提出書類の調査ガイドおよびForm Dに関するSECの案内で説明されているものの一部である。[5][11]

| 書式タイプ | 説明 |
| --- | --- |
| 10-K | 監査済み年次財務諸表を含む年次報告書 |
| 10-Q | 未監査の四半期財務諸表を含む四半期報告書 |
| 8-K | 次の定期報告書に先立って重要な事象や情報を公開する臨時報告書 |
| S-1 | 一般投資家向けの証券募集・売出しに関する登録届出書（新規株式公開で多く用いられる） |
| 4 | 企業インサイダーによる実質所有権の変動報告書（取引から2営業日以内に提出） |
| 20-F | 外国民間発行体の年次報告書または登録届出書 |
| D | レギュレーションDに基づく登録免除証券発行の届出 |

EDGARにおけるForm Dは、レギュレーションDによってSECへの提出が義務づけられている登録免除証券発行の届出であり、証券の初回販売から15日以内に提出しなければならない。2026年4月24日に最終確認されたSECのページによると、SECはEDGARアカウントの開設・維持や、Form Dの届出・訂正の提出に対して手数料を課していない。[11] 企業がForm Dを提出するには、事前にEDGARアカウントおよびそれに紐づくCIKを取得する必要がある。[11]

EDGARの複数の書式タイプに含まれる財務諸表は、構造化データとしても提供されている。data.sec.govのXBRL APIはForm 10-Q、10-K、8-K、20-F、40-F、6-Kおよびそれらの派生書式を対象としており、SECは2009年にXBRLを初めて義務化したとしている。[2] SECはXBRLを財務諸表報告用のXMLベース形式と説明しており、独立したXMLファイルとして提出されるか、インラインXBRL（inline XBRL）としてHTML報告書に埋め込まれて提出される。[2]

## data.sec.gov API、XBRLフレームおよびSECの公正アクセス規則

SECはdata.sec.gov上でEDGARデータをJSON形式で配信するRESTful APIを運用している。2026-11-21時点で、これらのAPIは認証やAPIキーを必要とせず、各提出者の提出履歴および財務諸表のXBRLデータを網羅している。[2] 公式に文書化されているエンドポイントは以下の通りである。[2]

| エンドポイント | 返却内容 |
| --- | --- |
| `https://data.sec.gov/submissions/CIK##########.json` | 1つの主体の提出履歴と、現在名称、旧名称、上場取引所、ティッカーシンボルなどのメタデータ |
| `https://data.sec.gov/api/xbrl/companyconcept/CIK##########/us-gaap/AccountsPayableCurrent.json` | 1社による単一コンセプトのすべてのXBRL開示データ |
| `https://data.sec.gov/api/xbrl/companyfacts/CIK##########.json` | 1社のすべての企業コンセプトデータを1回の呼び出しで返却 |
| `https://data.sec.gov/api/xbrl/frames/us-gaap/AccountsPayableCurrent/USD/CY2019Q1I.json` | 指定した暦年期間における報告主体ごと1件のファクトデータ |

submissionsエンドポイントは、少なくとも1年分または直近1,000件のうち多い方の提出書類を返却し、それより古い提出書類については追加ファイルへの参照を示す。framesエンドポイントは、年次データに`CY####`、四半期データに`CY####Q#`、時点データに`CY####Q#I`という形式で期間を指定し、各主体からその暦年期間に最も適合するファクトを返却する。XBRLエンドポイントが集計するのは、us-gaap、ifrs-full、dei、srtなどの非カスタムタクソノミを使用し、提出主体全体に適用されるファクトのみである。[2] APIは提出書類の公開に合わせてリアルタイムに更新され、通常の処理遅延は提出履歴が1秒未満、XBRLデータが1分未満である。また、両データセットの一括アーカイブ（`submissions.zip`および`companyfacts.zip`）は毎晩米国東部時間の午前3時頃に再公開される。[2]

EDGARへの自動アクセスにはSECの公正アクセス（fair access）規則が適用される。2026-11-21時点の最大リクエスト速度は毎秒10リクエストであり、SECは自動クライアントに対してリクエストヘッダーでユーザーエージェントを明示するよう求めている。SECが示す`User-Agent`の例は、企業名に続いて管理担当者のメールアドレスを記載した形式である。[3] この上限は使用するマシン台数にかかわらず利用者単位で適用され、SECは過剰なリクエストを送信するIPアドレスを遮断する権利を留保している。[4] data.sec.govはCORSに対応しておらず、SECはスクリプトによるダウンロード処理の開発やデバッグについて技術サポートを提供できないとしている。[2]

## EDGAR Nextによる提出者アクセスおよびアカウント管理の変更

EDGAR Nextは、SECが2024年9月27日に採択したEDGAR提出者のアクセスおよびアカウント管理に関する規則・書式改正の名称である。[8] この改正により、提出者はEDGARアカウントを管理する特定個人に権限を付与することが義務づけられ、提出者の代理として操作する個人はLogin.govから取得した個人アカウント認証情報を提示する必要がある。また、EDGARアクセス申請書であるForm IDが刷新され、提出者が書類の提出、情報の取得およびアカウント管理業務を行える任意のAPIも導入された。[8] 改正Form IDの遵守は、すべての改正が発効した2025年3月24日から義務づけられ、改正事項全体の遵守期限は2025年9月15日であった。[8]

2025年12月22日に最終確認されたSECのEDGAR Nextページによると、EDGARで書類を提出するにはEDGAR Nextへの対応が必須であり、移行登録（enrollment）は終了している。提出者はEDGAR Nextへの登録を完了しているか、2025年3月24日以降にForm ID申請の承認を受けている必要があり、アクセス権を持たない提出者はEDGAR Filer Managementウェブサイト上でForm IDを提出して申請する。[7] 3つのEDGARウェブサイト（EDGAR Filer Management、EDGAR Online FormsおよびEDGAR Filing）のいずれかにログインするには、Login.govの個人アカウント認証情報と多要素認証が必要であり、従来のログイン方式は廃止された。[7] 提出者向けAPIは公開のdata.sec.gov APIとは別に文書化されており、提出者APIトークンおよびユーザーAPIトークンを扱うガイドが用意されている。[2]

## EDGARへの提出が証明しない事項

SEC EDGARに提出書類が掲載されていることは、SECがその内容を検証したことを意味しない。SECの企業財務局（Division of Corporation Finance）は提出書類を選別的に審査しており、審査プロセスは「開示が完全かつ正確であることの保証ではない（is not a guarantee that the disclosure is complete and accurate）」と明言している。完全かつ正確な開示の責任は、企業および提出書類の作成に関与した関係者が負う。[10] 2002年サーベンス・オクスリー法（Sarbanes-Oxley Act of 2002）に基づき、各報告企業は少なくとも3年に1回は何らかの水準で企業財務局の審査を受ける。同局はさらに、取引の妥当性を評価することも、特定の投資が特定の投資家に適しているかを判断することもないと述べている。[10]

EDGARへの提出は、登録や承認の証拠にもならない。SECの投資家教育サイトであるInvestor.govは、SECへの書類提出によって個人や企業がSECに登録されたことにはならず、SECは登録証明書を発行しないとしている。[12] 同ページは、Form Dの提出が個人や企業のSECへの登録や認可の有無を示すものではないことも指摘している。[12]

EDGARの公開ツールには収録範囲の制約もある。全文検索の対象は2001年以降に電子提出された書類（付属書類などの添付ファイルを含む）に限られる。[6] 一部の書類は現在も紙媒体で提出されており、EDGARからは閲覧できない。また、誤った提出者名義で提出された場合や過去の提出と重複した場合など、SEC職員は提出者の要請に応じて受理後に書類を削除または訂正することがある。[3]

## よくある質問

### CIK番号とは何ですか？

中央インデックスキー（CIK）は、提出者がSECへ書類を提出するために登録する際、EDGARが割り当てる固有の数値識別子です。CIK番号は再利用されず、data.sec.govのAPIでは先頭を0で埋めた10桁で表記されます。 [3][2]

### SEC EDGARのAPIにはAPIキーが必要ですか？

いいえ。2026-11-21時点で、SECはdata.sec.govのAPIに認証やAPIキーは不要であるとしています。ただし自動リクエストは毎秒10リクエストに制限されており、SECはリクエストヘッダーでユーザーエージェントを宣言するよう求めています。 [2][3]

### SECはEDGARに掲載された提出書類の正確性を検証していますか？

SECの企業財務局は提出書類を選別的に審査していますが、その審査プロセスは開示が完全かつ正確であることを保証するものではないと明言しています。完全かつ正確な開示の責任は、企業および書類作成に関与した関係者にあります。 [10]

### EDGARの提出書類はいつまで遡れますか？

SECによるとEDGARは1994/1995年に開始され、インデックスファイルには1994年第3四半期以降の公開提出書類が掲載されています。全文検索の対象は2001年以降に電子提出された書類です。 [3][6]

### EDGAR Nextとは何ですか？

EDGAR Nextは、2024年9月27日にSECが採択した提出者アクセスおよびアカウント管理に関する規則・書式改正の総称です。改正は2025年3月24日に発効し、2025年9月15日までに全面遵守が義務づけられました。現在、EDGARへのログインには多要素認証を伴うLogin.govの個人アカウント認証情報が必要です。 [8][7]

### Form 10-K、10-Q、8-Kの違いは何ですか？

Form 10-Kは監査済み財務諸表を含む年次報告書であり、Form 10-Qは未監査の財務諸表を含む四半期報告書です。Form 8-Kは、次の定期的な四半期報告書や年次報告書の公表前に重要な事象や情報を開示するための臨時報告書です。 [5]

## 引用できる文

- EDGARはElectronic Data Gathering, Analysis, and Retrievalの略称である。 [1]
- EDGARによって割り当てられるCIK番号は提出者固有であり、再利用されない。 [3]
- 2026-11-21時点で、SECのdata.sec.gov APIは認証やAPIキーを必要としない。 [2]
- 2026-11-21時点で、EDGARへの自動アクセスに対するSECの最大リクエスト速度は毎秒10リクエストである。 [3]
- EDGARの全文検索は、2001年以降に電子提出された書類を対象としている。 [6]
- SECは2024年9月27日にEDGAR Nextの規則および書式改正を採択した。 [8]
- SECの企業財務局は、提出書類の審査プロセスが開示の完全性および正確性を保証するものではないと明言している。 [10]
- Form Dは証券の初回販売から15日以内に提出しなければならない。 [11]

## 年表

- 1992-07-15: 実運用版EDGARシステムが任意参加の提出者向けに公開される。 [9]
- 1993-02-23: SECが電子提出を義務づける暫定規則を採択するリリースを発出する。 [9]
- 1993-04-26: 提出者のEDGARシステムへの段階的導入が開始される。 [9]
- 1994-12-19: SEC Release No. 33-7122により暫定EDGAR規則が最終化され、すべての米国登録企業に適用される。 [9]
- 1999-06-28: EDGARがHTML形式による正式提出書類の受付を開始する。 [9]
- 2002-11-04: 外国発行体にEDGARを通じたSEC書類提出を義務づける規則が発効する。 [9]
- 2024-09-27: SECが提出者アクセスおよびアカウント管理に関するEDGAR Next規則・書式改正を採択する。 [8]
- 2025-03-24: EDGAR Next改正が発効し、改正Form IDの遵守が義務づけられる。 [8]
- 2025-09-15: EDGAR Nextのすべての規則および書式改正の遵守が義務づけられる。 [8]

## 出典

1. SEC.gov | About EDGAR. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/about-edgar (閲覧 2026-11-21; tier 1: government or public registry)
2. SEC.gov | EDGAR Application Programming Interfaces (APIs). U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-application-programming-interfaces (閲覧 2026-11-21; tier 1: government or public registry)
3. SEC.gov | Accessing EDGAR Data. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data (閲覧 2026-11-21; tier 1: government or public registry)
4. SEC.gov | Developer Resources. U.S. Securities and Exchange Commission. https://www.sec.gov/about/developer-resources (閲覧 2026-11-21; tier 1: government or public registry)
5. SEC.gov | Using EDGAR to Research Investments. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/using-edgar-research-investments (閲覧 2026-11-21; tier 1: government or public registry)
6. SEC.gov | EDGAR Full Text Search FAQ. U.S. Securities and Exchange Commission. https://www.sec.gov/edgar/search/efts-faq.html (閲覧 2026-11-21; tier 1: government or public registry)
7. SEC.gov | EDGAR Next: Improving Filer Access and Account Management. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/improving-edgar/edgar-next-improving-filer-access-account-management (閲覧 2026-11-21; tier 1: government or public registry)
8. SEC.gov | SEC Adopts Improvements to EDGAR System to Enhance Security, Filer Access, and Account Management. U.S. Securities and Exchange Commission. 公開 2024-09-27. https://www.sec.gov/newsroom/press-releases/2024-155 (閲覧 2026-11-21; tier 1: government or public registry)
9. Electronic Filing and EDGAR (October 2006). U.S. Securities and Exchange Commission. 公開 2006-10-03. https://www.sec.gov/info/edgar/regoverview.htm (閲覧 2026-11-21; tier 1: government or public registry)
10. SEC.gov | Filing Review Process. U.S. Securities and Exchange Commission. https://www.sec.gov/divisions/corpfin/cffilingreview.htm (閲覧 2026-11-21; tier 1: government or public registry)
11. SEC.gov | What is Form D?. U.S. Securities and Exchange Commission. https://www.sec.gov/resources-small-businesses/capital-raising-building-blocks/what-form-d (閲覧 2026-11-21; tier 1: government or public registry)
12. False Claims of SEC Registration | Investor.gov. U.S. Securities and Exchange Commission, Investor.gov. https://www.investor.gov/protect-your-investments/fraud/types-fraud/false-claims-sec-registration (閲覧 2026-11-21; tier 1: government or public registry)

## このページを引用する

Mimirwiki. "SEC EDGAR." 版 066ed7b5, 2026-11-21. https://mimirwiki.com/ja/wiki/sec-edgar
