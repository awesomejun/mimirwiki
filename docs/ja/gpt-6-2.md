---
title: "GPT-6.2"
subtitle: "2026年11月にリリースされたOpenAIのマルチモーダル推論言語モデル（GPT-6.2 AstraおよびGPT-6.2 Sol）"
canonical_url: https://mimirwiki.com/ja/wiki/gpt-6-2
language: ja
page_class: entity
revision_sha256: f6ef682818e422b0bafcad39f919ee2aa021d43a082f9c4f9e3b7746a6c6b5ef
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 11
alternates:
  md: https://mimirwiki.com/ja/wiki/gpt-6-2.md
  txt: https://mimirwiki.com/ja/wiki/gpt-6-2.txt
  json: https://mimirwiki.com/ja/wiki/gpt-6-2.json
  jsonld: https://mimirwiki.com/ja/wiki/gpt-6-2.jsonld
translations:
  en: https://mimirwiki.com/wiki/gpt-6-2
  ko: https://mimirwiki.com/ko/wiki/gpt-6-2
  zh: https://mimirwiki.com/zh/wiki/gpt-6-2
---

# GPT-6.2

> GPT-6.2は、OpenAIが2026年11月17日にChatGPT Work、Codex、およびOpenAI API向けにリリースしたGPT-6.2 AstraとGPT-6.2 Solの2つの大規模言語モデルである。両モデルともテキストと画像の入力を受け付け、必須の推論トークンを用いてテキストを生成し、1,050,000トークンのコンテキストウィンドウと最大128,000出力トークンをサポートしている。2026-11-23時点の100万トークンあたりの標準API料金は、GPT-6.2 Astraが入力8.00ドル・出力40.00ドル、GPT-6.2 Solが入力2.00ドル・出力10.00ドルである。

GPT-6.2は、OpenAIの第6世代マルチモーダル大規模言語モデルシリーズにおけるリリースであり、2026年11月17日に公開されたGPT-6.2 Astra（`gpt-6.2-astra`）とGPT-6.2 Sol（`gpt-6.2-sol`）の2つの推論モデルで構成される。OpenAIは、GPT-6.2 Astraを複雑な専門的成果物、ソフトウェアエンジニアリング、科学研究、およびコンピュータ操作（computer use）向けのフラッグシップ・フロンティアモデルと位置づけ、GPT-6.2 Solを日常的なコーディングや多段階のエージェントワークフロー向けのコスト効率に優れたモデルと位置づけている。両モデルはテキストと画像の入力を受け付け、推論トークンを伴うテキスト出力を生成し、1,050,000トークンのコンテキストウィンドウ（最大入力922,000トークン、最大出力128,000トークン）を提供する。2026-11-23時点で、これらのモデルはOpenAI API、Google Cloudのプライベートプレビュー、ならびにChatGPT Plus、Pro、Enterprise、Edu契約者向けのChatGPT WorkおよびCodexのプレビューを通じて利用できる。

**別名:** GPT-6.2 Astra, GPT-6.2 Sol, gpt-6.2-astra, gpt-6.2-sol, OpenAI GPT-6.2

## 主要な事実

- **リリース日:** 2026-11-17 [2]
- **モデルおよびAPI ID:** GPT-6.2 Astra（gpt-6.2-astra）およびGPT-6.2 Sol（gpt-6.2-sol） (時点 2026-11-23) [4]
- **コンテキストウィンドウ:** 1,050,000トークン（最大入力922,000、最大出力128,000） (時点 2026-11-23) [4]
- **GPT-6.2 Astra標準API料金:** 100万トークンあたり入力$8.00、キャッシュ済み入力$0.40、出力$40.00（入力272K以下） (時点 2026-11-23) [6]
- **GPT-6.2 Sol標準API料金:** 100万トークンあたり入力$2.00、キャッシュ済み入力$0.10、出力$10.00（入力272K以下） (時点 2026-11-23) [6]

## ファクトシート

- **開発元:** OpenAI [1]
- **リリース日:** 2026-11-17 [2]
- **モデル構成およびAPI ID:** GPT-6.2 Astra（gpt-6.2-astra）およびGPT-6.2 Sol（gpt-6.2-sol） (時点 2026-11-23) [4]
- **前世代モデル:** GPT-6 AstraおよびGPT-6.1 Sol [1]
- **モダリティ:** テキスト・画像入力、テキスト出力（音声・動画は非対応） (時点 2026-11-23) [4]
- **コンテキストウィンドウおよび上限:** 1,050,000トークン（最大入力922,000、最大出力128,000） (時点 2026-11-23) [4]
- **知識カットオフ:** 2026-05-18（GPT-6.2 Astra）、2026-06-01（GPT-6.2 Sol） (時点 2026-11-23) [4]
- **標準API料金（272K以下）:** Astra：入力$8.00 / キャッシュ$0.40 / 出力$40.00（100万トークンあたり）、Sol：入力$2.00 / キャッシュ$0.10 / 出力$10.00（100万トークンあたり） (時点 2026-11-23) [6]
- **対応APIエンドポイント:** v1/responses, v1/chat/completions, v1/batch (時点 2026-11-23) [4]
- **ChatGPTおよびクラウド提供状況:** ChatGPT WorkおよびCodex（Plus、Pro、Enterprise、Edu）、Google Cloud（プライベートプレビュー） (時点 2026-11-23) [3]
- **Preparedness評価:** サイバーセキュリティ：Critical（両方）、生物・化学：High（両方）、AI自己改善：High（Astraのみ） (時点 2026-11-22) [8]

## GPT-6.2の概要、リリース履歴、およびモデルラインナップ

GPT-6.2は[OpenAI](https://mimirwiki.com/ja/wiki/openai)が開発したGPT-6世代の大規模言語モデルにおけるリリースであり、2026年11月17日にGPT-6.2 AstraとGPT-6.2 Solの2つのバリエーションで公開された。[1][2] 2026-11-23時点のOpenAIのモデルカタログにおいて、GPT-6ファミリーは天体にちなんだ階層名を採用している。フロンティア推論向けのAstra、バランスの取れた日常的なコーディングおよびエージェントワークロード向けのSol、視覚推論および執筆向けのTerra（`gpt-6.1-terra`、2026年10月26日公開）、大量・低コスト処理向けのLuna（`gpt-6-luna`、2026年9月22日公開）に加え、特化型モデルとしてGPT-6 CyberおよびGPT-6 Rosalind Research（2026年10月30日公開）が存在する。[2][9][11]

GPT-6.2 AstraはGPT-6 Astraの後継であり、GPT-6.2 SolはGPT-6.1 Sol（2026年9月29日リリース）およびGPT-6 Sol（2026年9月22日リリース）の後継にあたる。[1][9][11] OpenAIのリリース発表およびAPIドキュメントによると、GPT-6.2 Astraはソフトウェアエンジニアリング、科学研究、法務・財務分析、コンピュータ操作、3Dやフロントエンドデザインにわたる複雑なエンドツーエンドのプロジェクト向けに設計されている。一方、GPT-6.2 Solは低遅延の日常的なコーディング、執筆、および大規模な多段階エージェントワークフロー向けに最適化されており、多くのOpenAI従業員にとって社内デフォルトモデルとして機能している。[1][4][5]

2026年11月17日、OpenAIはOpenAI API、[ChatGPT](https://mimirwiki.com/ja/wiki/chatgpt) Work、およびCodexデスクトップで両モデルを同時に展開した。[1][2][3] ChatGPTでは、Plus、Pro、Enterprise、Eduの各ユーザーがWorkモデルピッカーおよびCodexモデルセレクターを通じてGPT-6.2 AstraとGPT-6.2 Solのプレビューにアクセスできる一方、標準のChatGPT Chatタブでは従来のモデル選択肢が維持されている。[1][3][10]

## GPT-6.2の技術仕様とResponses APIアーキテクチャ

2026-11-23時点のOpenAI開発者向けドキュメントによると、GPT-6.2 Astra（`gpt-6.2-astra`）とGPT-6.2 Sol（`gpt-6.2-sol`）はいずれもテキストと画像の入力を受け付けてテキスト出力を返す一方、音声および動画モダリティ、ファインチューニング、予測出力（predicted outputs）には対応していない。[4][5] 各モデルは1,050,000トークンのコンテキストウィンドウを備え、1リクエストあたり最大922,000入力トークンおよび最大128,000出力トークンをサポートしている。[4][5] 公式ドキュメント上の知識カットオフは、GPT-6.2 Astraが2026年5月18日、GPT-6.2 Solが2026年6月1日である。[4][5]

| 仕様項目 | GPT-6.2 Astra（`gpt-6.2-astra`） | GPT-6.2 Sol（`gpt-6.2-sol`） |
| --- | --- | --- |
| 主な役割 | 複雑な推論、コーディング、専門業務向けのフロンティアモデル | 日常的なコーディングおよび大規模な多段階エージェント向けのバランス型モデル |
| 前世代モデル | GPT-6 Astra（`gpt-6-astra`） | GPT-6.1 Sol（`gpt-6.1-sol`） |
| 入出力モダリティ | テキスト・画像入力、テキスト出力 | テキスト・画像入力、テキスト出力 |
| コンテキストウィンドウ | 1,050,000トークン（最大入力922,000、最大出力128,000） | 1,050,000トークン（最大入力922,000、最大出力128,000） |
| 知識カットオフ | 2026年5月18日 | 2026年6月1日 |
| 対応APIエンドポイント | `v1/responses`, `v1/chat/completions`, `v1/batch` | `v1/responses`, `v1/chat/completions`, `v1/batch` |
| クラウドパートナー提供 | Google Cloud（プライベートプレビュー） | Google Cloud（プライベートプレビュー） |

両モデルとも推論トークンを生成し、`reasoning.effort`を`none`に設定したAPIリクエストを拒否する。[4][5] 両モデルでサポートされるAPI機能には、ストリーミング、構造化出力（structured outputs）、関数呼び出し（function calling）、ファイル検索、画像入力、ウェブ検索、プロンプトキャッシングが含まれる。[4][5] Responses API（`v1/responses`）経由で呼び出す場合、両モデルは`web_search`、`file_search`、`image_generation`、`code_interpreter`、`hosted_shell`、`apply_patch`、`skills`、`computer_use`、[Model Context Protocol](https://mimirwiki.com/ja/wiki/model-context-protocol)（`mcp`）、および`tool_search`の各組み込みツールに加え、Multi-agentベータによるサブエージェント委任をサポートしている。[4][5]

OpenAIの移行ガイド「Using GPT-6.2」では、GPT-6.2から始まるResponses APIにおける3つの挙動変更が挙げられている。[7]

- プレフィックス編集（Prefix edits）：会話の途中で過去の履歴（以前のdeveloperメッセージやツール呼び出しなど）を変更したり、モデルをダウングレードしたり、ユーザーや組織を変更したりした場合、Responses APIは以前の推論項目を破棄するため、推論状態とプロンプトキャッシングを維持するにはプレフィックスを変更しない必要がある。[7]
- トップレベル`instructions`の配置順序：GPT-6.2はトップレベルの`instructions`パラメータを`input`の前ではなく後ろに追加するため、プロンプトキャッシングを有効にするには、再利用可能な指示を`input`内の先頭の`developer`メッセージに配置する必要がある。[7]
- バックグラウンド完了ウィンドウ：GPT-6.2の両モデルはいずれもFlex処理（`service_tier: flex`）に対応していない代わりに、長時間実行されるResponses APIリクエスト向けに、2時間または8時間の完了ウィンドウを備えたパブリックベータの割引バックグラウンドモードを利用できる。[4][5][7]

## GPT-6.2のAPI料金、処理階層、およびレート制限

OpenAIはGPT-6.2のAPI使用量を100万トークンあたり米ドル建てで課金しており、ショートコンテキストのリクエスト（入力272,000トークン以下）とロングコンテキストのリクエスト（入力272,000トークン超）に区分している。ロングコンテキストではリクエスト全体に対して入力およびキャッシュ単価が2倍、出力単価が1.5倍になる。[4][5][6] GPT-6 Astra（100万トークンあたり入力10.00ドル、キャッシュ済み入力1.00ドル、出力50.00ドル）と比較すると、GPT-6.2 Astraは標準の入出力料金を20%、キャッシュ済み入力料金を60%引き下げており、GPT-6.2 SolはGPT-6.1 Solの料金体系を維持している。[1][6]

| モデルおよび処理階層（2026-11-23時点） | ショート入力（<=272K） | ショート出力（<=272K） | ショートキャッシュ済み入力 | ショートキャッシュ書き込み（30分 / 12時間） | ロング入力（>272K） | ロング出力（>272K） |
| --- | --- | --- | --- | --- | --- | --- |
| GPT-6.2 Astra（Standard） | $8.00 / 1M | $40.00 / 1M | $0.40 / 1M | $10.00 / $20.00 | $16.00 / 1M | $60.00 / 1M |
| GPT-6.2 Astra（Batch、Standardの50%） | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Astra（Fast、Standardの2倍） | $16.00 / 1M | $80.00 / 1M | $0.80 / 1M | $20.00 / $40.00 | $32.00 / 1M | $120.00 / 1M |
| GPT-6.2 Astra（Ultrafastプロモーション、2027-02-28までStandardの3倍） | $24.00 / 1M | $120.00 / 1M | $1.20 / 1M | $30.00 / $60.00 | $48.00 / 1M | $180.00 / 1M |
| GPT-6.2 Sol（Standard） | $2.00 / 1M | $10.00 / 1M | $0.10 / 1M | $2.50 / $5.00 | $4.00 / 1M | $15.00 / 1M |
| GPT-6.2 Sol（Batch、Standardの50%） | $1.00 / 1M | $5.00 / 1M | $0.05 / 1M | $1.25 / $2.50 | $2.00 / 1M | $7.50 / 1M |
| GPT-6.2 Sol（Fast、Standardの2倍） | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Sol（Ultrafastプロモーション、2027-02-28までStandardの3倍） | $6.00 / 1M | $30.00 / 1M | $0.30 / 1M | $7.50 / $15.00 | $12.00 / 1M | $45.00 / 1M |

Standard、Batch（50%割引）、Fast（Standardの2倍）の各階層に加え、OpenAIは太平洋時間2027年2月28日までStandard料金の3倍、2027年3月1日以降はStandard料金の6倍となるUltrafast階層を提供している。[4][5][6] 2026-11-23時点の両モデルの標準レート制限は、Build階層で毎分5,000リクエスト（RPM）および毎分1,000,000トークン（TPM）、Launch階層で10,000 RPMおよび4,000,000 TPM、Grow階層で15,000 RPMおよび40,000,000 TPMである。[4][5]

## GPT-6.2のベンチマーク評価と初期の反応

2026年11月17日のリリース発表において、OpenAIはGPT-6.2 AstraとGPT-6.2 Solのいずれも、出力トークン数を削減しつつ、長期的な専門業務、科学、およびコーディングのベンチマークで前世代モデルを上回ったと報告した。[1][2]

- Agents' Last Exam（長期多段階の専門業務）：OpenAIの報告によれば、GPT-6.2 AstraはGPT-6 Astraより3分の1未満のコストで5.2ポイント高いスコアを記録し、フォールバックモデルを使用した9タスクを除いた[Claude Fable 5.2](https://mimirwiki.com/ja/wiki/claude-fable-5-2)に対しても5%のコストで5.5ポイント上回った。[1]
- Terminal-Bench-Science 0.1およびVals Science Index v1：OpenAIは、GPT-6.2 AstraがTerminal-Bench-Science 0.1でGPT-6 Astraより3分の1未満のコストで9パーセントポイント高いスコアを達成し、Vals Science Index v1でも過去最高を更新したとしている。[1]
- 法務および財務ワークフロー：Harvey LAB-AA v1.1において、OpenAIはGPT-6.2 Astraが約6分の1のコストでClaude Fable 5.2の合格率の2倍以上を達成し、法務向け構成のAstra for Lawはさらに高いスコアを記録したと報告している。また、Artificial Analysisのスプレッドシート・レポート評価ベンチマークAA-AnalystAgentでは、GPT-6.2 Astraが5回の独立試行すべてで62.5%の問題に正答した。[1]
- GDPval v2（OpenAI社内の知識労働評価）：GPT-6.2 Astraは出力トークン数を22%削減しながらGPT-6 Astraより6.2パーセントポイント向上し、GPT-6.2 SolはGPT-6.1 Solより5.3ポイント向上した。[1]
- FrontierCode 2.0およびLifeVal：最大推論強度でのCognitionのFrontierCode 2.0において、GPT-6.2 Solは約5分の1のコストでGPT-6.2 Astraとの差を0.5ポイント以内に収め、OpenAIの日常タスク評価LifeValでは約7分の1のコストでGPT-6 Astraを上回った。[1]

リリース後、VentureBeatは2026年11月17日に、外部のAIパワーユーザーによるリリース前および公開当日の反応が賛否両論であったと報じた。[10] OpenAIが引用した初期の企業評価者（IMC、Legora、Harvey、ClickUpのエンジニアや幹部を含む）は、法務およびワークスペースのベンチマークでトークン使用量が34.5%から62%削減されたと報告し、テスターのBen Hylak（Raindrop.ai CTO）およびAshe MagalhaesはGPT-6.2 Astraのモーショングラフィックス、視覚効果、および動画編集能力を高く評価した。[1][10] 一方、開発者のTheo Browne、投資家のMatt Shumer、Every CEOのDan Shipper、およびウォートン・スクール教授のEthan Mollickは、GPT-6.2 Astraが長時間の自律的なビルド作業で早期に停止する傾向や、異なるゲームプロンプトに対しても同じ「Bellwether」という名前の水域レベルを生成するような画一的なハウススタイル、さらにはデフォルトの文章が過度に簡潔すぎるために文脈が欠落する点を批判した。[10]

## GPT-6.2システムカード、Preparedness Framework評価、および安全性評価

OpenAIは2026年11月17日にGPT-6.2システムカードを公開し、2026年11月22日に変更履歴を更新して、OAI-repo Sabotage v2評価におけるL2モニターの優先度分類（`P0`はセキュリティチームによる即時レビュー、`P0.5`は営業時間内の高優先度フォローアップ）を明確化した。[8] OpenAI Preparedness Frameworkの下で、GPT-6.2 AstraとGPT-6.2 Solはいずれもサイバーセキュリティ能力でCritical基準、生物・化学能力でHigh基準を満たしている。[8] 両モデルとも既知のソフトウェア脆弱性から動作するエクスプロイトを開発する能力でGPT-6 AstraおよびGPT-6.1 Solを上回ったため、OpenAIは高リスクなサイバーセキュリティ関連クエリに対するデフォルトの制限を強化し、緩和されたサイバーアクセスに対して追加審査を義務づけた。[8]

さらに、GPT-6.2 AstraはAI自己改善（AI Self-Improvement）能力でHigh基準に達したOpenAI初の外部公開モデルである。OpenAIはこの基準を、完全自動化された再帰的自己改善が可能なモデルの登場に先立って安全対策を準備するための初期マイルストーンと定義しており、GPT-6.2 Solはこの基準を下回っている。[8] Codex内でのGPT-6.2 Astraの社内展開を拡大する前に、OpenAIは段階的ゲート付きのアライメント安全対策を検証し、研究環境の隔離を強化し、フロンティアエージェントの監視体制を拡充した。[8]

GPT-6.2システムカードには、プロンプトインジェクション耐性、ハルシネーション、HealthBench Professional、MentalHealthBench、ExploitGym Honeypot、Blocker Deception、Broken Search Tool、職場タスクシミュレーション、意図しないエージェント間通信、思考の連鎖制御（`CoT-Control`）、`OAI-repo Sabotage v2`、`Sneaky Sandbox Escape`にわたる包括的なアライメントおよび監視可能性テストに加え、SecureBioおよび英国AIセキュリティ研究所（UK AISI）による外部評価が記載されている。[8]

## よくある質問

### GPT-6.2とは何ですか？また、GPT-6.2 AstraとGPT-6.2 Solはどう違いますか？

GPT-6.2は2026年11月17日に発表されたOpenAIの言語モデルリリースであり、2つのモデルで構成されています。GPT-6.2 Astra（`gpt-6.2-astra`）は複雑な推論、ソフトウェアエンジニアリング、科学研究、専門的な成果物作成向けのフロンティアモデルとして位置づけられ、GPT-6.2 Sol（`gpt-6.2-sol`）は日常的なコーディングや多段階のエージェントワークフロー向けの高速・低コストなモデルとして位置づけられています。両モデルとも1,050,000トークンのコンテキストウィンドウを備え、テキストと画像の入力に対応しています。 [1][2][4][5]

### OpenAI APIにおけるGPT-6.2 AstraとGPT-6.2 Solの料金はいくらですか？

2026-11-23時点で、ショートコンテキストのリクエスト（入力272,000トークン以下）に対する100万トークンあたりの標準API料金は、GPT-6.2 Astraが入力8.00ドル、キャッシュ済み入力0.40ドル、30分キャッシュ書き込み10.00ドル（12時間は20.00ドル）、出力40.00ドルです。GPT-6.2 Solは入力2.00ドル、キャッシュ済み入力0.10ドル、30分キャッシュ書き込み2.50ドル（12時間は5.00ドル）、出力10.00ドルです。入力が272,000トークンを超えるロングコンテキストのリクエストでは、リクエスト全体に対して入力およびキャッシュ単価が2倍、出力単価が1.5倍になります。 [4][5][6]

### GPT-6.2のコンテキストウィンドウ、出力上限、知識カットオフはどうなっていますか？

GPT-6.2の各モデルは1,050,000トークンのコンテキストウィンドウを備え、最大922,000入力トークンおよび最大128,000出力トークンに対応しています。知識カットオフはGPT-6.2 Astraが2026年5月18日、GPT-6.2 Solが2026年6月1日です。両モデルともテキストと画像の入力およびテキスト出力に対応していますが、音声、動画、ファインチューニング、予測出力（predicted outputs）には対応していません。 [4][5]

### ユーザーや開発者はどこでGPT-6.2 AstraとGPT-6.2 Solを利用できますか？

2026-11-23時点で、GPT-6.2 AstraとGPT-6.2 SolはChatGPT Plus、Pro、Enterprise、Eduユーザー向けにChatGPT WorkおよびCodexデスクトップでプレビュー提供されており、通常のChatGPTのChatタブでは従来のモデル選択が維持されています。開発者はOpenAI API（`v1/responses`、`v1/chat/completions`、`v1/batch`）から両モデルを呼び出すことができ、Google Cloudでもプライベートプレビューとして提供されています。 [1][3][4][5][10]

### GPT-6.2 AstraとSolはPreparedness Frameworkのどの基準に達していますか？

2026年11月17日に公開され、2026年11月22日に更新されたGPT-6.2システムカードにおいて、OpenAIはGPT-6.2 AstraとGPT-6.2 Solの両モデルがOpenAI Preparedness Frameworkのサイバーセキュリティ能力でCritical基準、生物・化学能力でHigh基準に達していると述べています。さらに、GPT-6.2 AstraはAI自己改善（AI Self-Improvement）能力でHigh基準に達したOpenAI初の外部公開モデルであり、GPT-6.2 Solはその基準未満にとどまっています。 [8]

## 引用できる文

- OpenAIは2026年11月17日、ChatGPT Work、Codex、およびOpenAI APIにおいて、モデル識別子gpt-6.2-astraおよびgpt-6.2-solとしてGPT-6.2 AstraとGPT-6.2 Solをリリースした。 [1][2][3]
- GPT-6.2 AstraとGPT-6.2 Solはそれぞれ1,050,000トークンのコンテキストウィンドウ（最大入力922,000トークン、最大出力128,000トークン）をサポートし、テキストと画像の入力を受け付けて推論トークンを含むテキスト出力を生成する。 [4][5]
- 公式ドキュメントに記載された知識カットオフは、GPT-6.2 Astraが2026年5月18日、GPT-6.2 Solが2026年6月1日である。 [4][5]
- 2026-11-23時点で、入力トークン数272,000以下のプロンプトに対するGPT-6.2 Astraの標準OpenAI API料金は、100万トークンあたり入力8.00ドル、キャッシュ済み入力0.40ドル、30分キャッシュ書き込み10.00ドル、出力40.00ドルである。 [4][6]
- 2026-11-23時点で、入力トークン数272,000以下のプロンプトに対するGPT-6.2 Solの標準OpenAI API料金は、100万トークンあたり入力2.00ドル、キャッシュ済み入力0.10ドル、30分キャッシュ書き込み2.50ドル、出力10.00ドルである。 [5][6]
- GPT-6.2 Astraは、前世代モデルであるGPT-6 Astra（100万トークンあたり入力10.00ドル、キャッシュ済み入力1.00ドル、出力50.00ドル）と比較して、標準の入力・出力トークン単価を20%、キャッシュ済み入力単価を60%引き下げている。 [1][6]
- OpenAI Preparedness Frameworkの下で、GPT-6.2システムカードはGPT-6.2 AstraとGPT-6.2 Solの両モデルをサイバーセキュリティ能力でCritical基準、生物・化学能力でHigh基準に分類しており、GPT-6.2 AstraはAI自己改善能力でHigh基準に達したOpenAI初の外部公開モデルである。 [8]
- GPT-6.2の両モデルは、推論強度（reasoning effort）をnoneに設定したAPIリクエストを拒否し、Flex処理（service_tier: flex）には対応していない一方、Responses APIでは割引適用のバックグラウンド完了ウィンドウ（2時間または8時間）をサポートしている。 [4][5][7]

## 年表

- 2026-09-22: OpenAIはGPT-6 Astraの公開に続き、GPT-6 SolとGPT-6 LunaによってGPT-6モデルファミリーを拡充した。 [9]
- 2026-09-29: OpenAIはGPT-6シリーズでGPT-6.1 Solをリリースした。 [9]
- 2026-10-26: OpenAIはOpenAI API、ChatGPT Work、およびCodexでGPT-6.1 Terraを展開した。 [2]
- 2026-11-17: OpenAIはChatGPT Work、Codex、およびOpenAI APIでGPT-6.2 AstraとGPT-6.2 Solをリリースし、GPT-6.2システムカードを公開した。 [1][2][3][8]
- 2026-11-22: OpenAIはGPT-6.2システムカードの変更履歴を更新し、OAI-repo Sabotage v2セクションにおけるL2モニターの優先度分類を明確化した。 [8]
- 2027-03-01: GPT-6.2 AstraおよびGPT-6.2 SolのUltrafast API料金がStandard料金の3倍から6倍へ引き上げられる予定日である。 [4][5][6]

## 出典

1. Introducing GPT-6.2 Astra and Sol | OpenAI. OpenAI. 公開 2026-11-17. https://openai.com/index/introducing-gpt-6-2-astra-sol/ (閲覧 2026-11-23; tier 3: official site)
2. Model Release Notes | OpenAI Help Center. OpenAI Help Center. 公開 2026-11-17. https://help.openai.com/en/articles/9624314-model-release-notes (閲覧 2026-11-23; tier 3: official site)
3. ChatGPT release notes | OpenAI Help Center. OpenAI Help Center. 公開 2026-11-20. https://help.openai.com/en/articles/6825453-chatgpt-release-notes (閲覧 2026-11-23; tier 3: official site)
4. GPT-6.2 Astra - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-astra (閲覧 2026-11-23; tier 3: official site)
5. GPT-6.2 Sol - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-sol (閲覧 2026-11-23; tier 3: official site)
6. Pricing - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/pricing (閲覧 2026-11-23; tier 3: official site)
7. Using GPT-6.2 - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/guides/latest-model (閲覧 2026-11-23; tier 3: official site)
8. GPT-6.2 System Card - OpenAI Deployment Safety Hub. OpenAI Deployment Safety Hub. 公開 2026-11-17. https://deploymentsafety.openai.com/gpt-6-2-astra-sol (閲覧 2026-11-23; tier 3: official site)
9. GPT-6 Astra: A new generation of intelligence | OpenAI. OpenAI. https://openai.com/index/gpt-6-astra/ (閲覧 2026-11-23; tier 3: official site)
10. 'Essentially unusable': OpenAI launches GPT-6.2 Astra and Sol to negative reception from AI power users | VentureBeat. VentureBeat. 公開 2026-11-17. https://venturebeat.com/technology/essentially-unusable-openai-launches-gpt-6-2-astra-and-sol-to-negative-reception-from-ai-power-users (閲覧 2026-11-23; tier 2: academic or news)
11. Models - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "GPT-6.2." 版 f6ef6828, 2026-11-23. https://mimirwiki.com/ja/wiki/gpt-6-2
