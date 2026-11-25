---
title: "Luxスーパーコンピュータ"
subtitle: "オークリッジ国立研究所に設置されたAMDベースの人工知能および高性能計算スーパーコンピュータ"
canonical_url: https://mimirwiki.com/ja/wiki/lux-supercomputer
language: ja
page_class: entity
revision_sha256: 63cc2d8758ff37d7a10f67466e89a3e2a4e41a6033fb8baee2a0629fb2fb58f8
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ja/wiki/lux-supercomputer.md
  txt: https://mimirwiki.com/ja/wiki/lux-supercomputer.txt
  json: https://mimirwiki.com/ja/wiki/lux-supercomputer.json
  jsonld: https://mimirwiki.com/ja/wiki/lux-supercomputer.jsonld
translations:
  en: https://mimirwiki.com/wiki/lux-supercomputer
  ko: https://mimirwiki.com/ko/wiki/lux-supercomputer
  zh: https://mimirwiki.com/zh/wiki/lux-supercomputer
  es: https://mimirwiki.com/es/wiki/lux-supercomputer
---

# Luxスーパーコンピュータ

> Luxスーパーコンピュータは、米国エネルギー省オークリッジ国立研究所にヒューレット・パッカード・エンタープライズが構築した、AMDベースの人工知能および高性能計算システムである。2026年11月16日に科学研究者向けに公開され、2026年11月のTOP500リストでHigh Performance Linpack性能220.79ペタフロップスを記録して14位に初登場した。2026-11-23時点で504台のHPE ProLiant Compute XD685ノードと4,032基のAMD Instinct MI355X GPUで構成され、DOEのジェネシス・ミッションを支援している。

Luxスーパーコンピュータ（Lux SI+HPCスーパーコンピュータとも呼称される）は、米国テネシー州オークリッジにある米国エネルギー省（DOE）オークリッジ国立研究所（ORNL）のオークリッジ・リーダーシップ・コンピューティング施設（OLCF）が運用する人工知能および高性能計算（HPC）クラスターである。米国エネルギー省、Advanced Micro Devices（AMD）、およびHewlett Packard Enterprise（HPE）の官民共同投資パートナーシップによって開発され、DOEのジェネシス・ミッション（Genesis Mission）初の専用AIファクトリーとして2026年11月16日に科学研究者向けに公開された。同日、同システムは第68回TOP500リストにおいてHigh Performance Linpack（HPL）性能220.79ペタフロップスで14位に初登場した。2026-11-23時点のOLCF公式文書によると、Luxはノードあたり2基の64コアAMD EPYC 9575Fプロセッサと8基のAMD Instinct MI355X GPUを搭載した504台のHPE ProLiant Compute XD685ノード（合計4,032基のGPUおよび約1.1ペタバイトのHBM3Eメモリ）で構成され、FP64で317ペタフロップス、FP8で20エクサフロップス、FP4で40エクサフロップスのシステムピーク性能を発揮する。

**別名:** Lux, Lux Supercomputer, Lux SI+HPCスーパーコンピュータ, AMD Lux SIクラスター, ORNL Lux

## 主要な事実

- **運用機関および所在地:** オークリッジ・リーダーシップ・コンピューティング施設（OLCF）、オークリッジ国立研究所、米国テネシー州 [1]
- **TOP500初登場順位:** 2026年11月TOP500リスト14位（HPL 220.79ペタフロップス） (時点 2026-11-16) [1]
- **システム構成:** 504台のHPE ProLiant Compute XD685ノード、1,008基のAMD EPYC 9575F CPU、4,032基のAMD Instinct MI355X GPU (時点 2026-11-23) [4]
- **ピーク性能:** 40 EFLOPS（FP4推論）、20 EFLOPS（FP8学習）、317 PFLOPS（FP64シミュレーション） (時点 2026-11-23) [3]
- **年間ノード時間配分:** 年間350万ノード時間：50% DOEジェネシス・ミッション、50% AMDおよび有償パートナー枠 (時点 2026-11-23) [3]

## ファクトシート

- **施設および運用機関:** オークリッジ・リーダーシップ・コンピューティング施設（OLCF）、オークリッジ国立研究所（ORNL）、米国テネシー州オークリッジ [1]
- **主催および構築:** 米国エネルギー省（DOE）、Advanced Micro Devices（AMD）、Hewlett Packard Enterprise（HPE） [1]
- **プロジェクト発表日:** 2025-10-27（2028年導入予定のDiscoveryスーパーコンピュータと同時発表） [6]
- **科学研究者向け公開日:** 2026-11-16 [1]
- **TOP500順位:** 第68回TOP500リスト（2026年11月）世界14位（HPL 220.79ペタフロップス） (時点 2026-11-16) [1]
- **計算ノードおよびプラットフォーム:** 504台のHPE ProLiant Compute XD685ノード (時点 2026-11-23) [4]
- **ノードあたりCPU:** 64コアAMD EPYC 9575F CPU × 2基、3 TB DDR5メモリ（8 NUMAドメイン） (時点 2026-11-23) [4]
- **GPUおよびHBM容量:** 4,032基のAMD Instinct MI355X GPU（ノードあたり8基、各288 GB HBM3E・8 TB/s、合計約1.1 PB HBM） (時点 2026-11-23) [4]
- **システムピーク性能:** 317 PFLOPS（FP64 HPC）、20 EFLOPS（FP8 AI学習）、40 EFLOPS（FP4 AI推論） (時点 2026-11-23) [3]
- **インターコネクトおよびストレージ:** GPUあたりAMD Pensando 400G Ultra Ethernet NIC、ノードあたり3.2 TBローカルNVMe × 8基、679 PB Orion Lustreファイルシステム (時点 2026-11-23) [3]
- **OSおよびジョブスケジューラ:** Red Hat Enterprise Linux（RHEL）9.8、AMD ROCm、SlurmおよびKubernetesパーティション (時点 2026-11-23) [4]
- **年間計算容量および配分:** 年間350万ノード時間（50% DOEジェネシス・ミッション、50% AMDおよび有償パートナー枠） (時点 2026-11-23) [3]

## Luxスーパーコンピュータの概要、官民パートナーシップおよびTOP500初登場

Luxスーパーコンピュータは、米国テネシー州オークリッジのオークリッジ国立研究所（ORNL）内にある米国エネルギー省（DOE）科学局ユーザー施設、オークリッジ・リーダーシップ・コンピューティング施設（OLCF）に設置された人工知能および高性能計算（HPC）システムである。[1][2] 2026年後半の米国連邦政府およびORNLの公式発表では、大統領令14434号に基づき「人工知能（AI）」に代えて「スーパーインテリジェンス（Super Intelligence、SI）」という用語を採用する連邦方針を反映し、本システムは「SI+HPC」スーパーコンピュータとして位置づけられている。[1][2][7] Luxは、2022年にエクサスケールの壁を突破し、2026年11月のTOP500リストで3位にランクインしたOLCFの1.353エクサフロップス級HPE Cray EX235aフラッグシップシステムであるFrontierと並行して運用されている。[1][3]

DOE、ORNL、Advanced Micro Devices（AMD）、およびHewlett Packard Enterprise（HPE）は、2025年10月27日に、2028年納入予定のHPE Cray Supercomputing GX5000アーキテクチャに基づく8番目のOLCFフラッグシップスーパーコンピュータDiscoveryとともにLuxを初めて発表した。[1][6] 複数年にわたる従来のリーダーシップ級システム調達とは異なり、Luxは短期的なAIおよび科学計算能力を拡充するため、DOEとAMDの官民共同投資パートナーシップの下で約1年という短期間で調達・導入された。[1][3][8]

2026年11月16日、ORNLとAMDはLuxが科学研究者向けに公開され、世界で最も高性能なスーパーコンピュータを格付けする第68回TOP500リストで14位に初登場したと発表した。[1][2][5] TOP500順位付けに用いられるHigh Performance Linpack（HPL）ベンチマークにおいて、LuxはOLCF公表のFP64理論システムピーク性能317ペタフロップスに対し、220.79ペタフロップス（毎秒220.79京回の浮動小数点演算）を達成した。[1][3][8] OLCFの歴史によると、Luxは2004年以降に同施設へ導入された7基のフラッグシップシステムに続くものであり、そのうち4基（Jaguar、2012年のTitan、2018年のSummit、2022年のFrontier）は稼働開始時にTOP500で世界1位を獲得している。[1][3][6]

## Luxスーパーコンピュータのハードウェアアーキテクチャおよびノード仕様

Luxスーパーコンピュータは、AMD製プロセッサ、アクセラレータ、およびネットワーク機器を搭載した直接液冷方式のHPE ProLiant Compute XD685サーバーノードを基盤として構築されている。[1][4][8] 2026-11-23時点のOLCF Luxユーザーガイドによると、本番クラスターは504ノード・4,032 GPUで構成され、ログインノード（`lux.olcf.ornl.gov`の`login1`〜`login3`）と計算ノードに分離されている。[4] 各計算ノードは2基の64コアAMD EPYC 9575F CPU（ノードあたり128 CPUコア）を搭載し、3 TBのDDR5システムメモリを8つの非均一メモリアクセス（NUMA）ドメインで共有しており、各NUMAドメインは16ハードウェアスレッドと1基のGPUに対応づけられている。[4]

504台のノードそれぞれに8基のAMD Instinct MI355X GPUが搭載されており、システム全体で合計4,032基のアクセラレータを備える。[4] 各MI355X GPUは、256コンピュートユニットを含む8基のAccelerated Compute Die（XCD、ノードあたり64 XCD）と、ピークメモリ帯域幅8 TB/sで動作する288 GBのHBM3E広帯域メモリを統合しており、クラスター全体で約1.1ペタバイトの総HBM3E容量を提供する。[3][4] ノード内の8基のMI355X GPUは、接続あたり双方向ピーク帯域幅153.6 GB/sを実現するAMD Infinity Fabric GPU間接続で結ばれている。[4] ノード間通信にはGPUあたり1基のAMD Pensando 400G Ultra Ethernetネットワークインターフェースカード（NIC）が使用され、HPE Juniper Networkingスイッチングインフラストラクチャを介して相互接続されている。[3][5][8]

| 仕様項目 | ノードあたり / GPUあたり | システム全体（504ノード、4,032 GPU） |
| --- | --- | --- |
| サーバープラットフォーム | HPE ProLiant Compute XD685 | 504ノード（ログインおよび計算ノード） |
| ホストプロセッサ | 64コアAMD EPYC 9575F CPU × 2基、3 TB DDR5 RAM | 1,008 CPU（64,512 CPUコア）、約1.5 PB DDR5 |
| GPUアクセラレータ | AMD Instinct MI355X × 8基（GPUあたり8 XCD、256 CU） | 4,032基のMI355X GPU（32,256 XCD） |
| 広帯域メモリ（HBM） | GPUあたり288 GB HBM3E（帯域幅8 TB/s） | 合計約1.1 PB HBM3E |
| ノード内およびファブリック接続 | 153.6 GB/s Infinity Fabric GPU間接続、GPUあたり400G Ultra Ethernet NIC | 4,032基の400G AMD Pensando Ultra Ethernet NIC |
| FP64 HPC性能 | GPUあたりベクトルFP64約78.6 TFLOPS（概要ページでは78 TF表記） | 理論ピーク317 PFLOPS、HPL実測220.79 PFLOPS |
| 低精度AI性能 | GPUあたりベクトルFP16 157.3 TFLOPS、FP8学習5 PFLOPS | FP8学習20 EFLOPS、FP4推論40 EFLOPS |
| ノードローカルストレージ | 3.2 TB NVMe SSD × 8基（ノードあたり24 TB超） | 合計12 PB超のローカルNVMeストレージ |

2026-11-23時点のOLCF Luxユーザーガイドおよびシステム概要文書によると、個々のMI355X GPUの性能はモデリングおよびシミュレーション向けのベクトル倍精度（FP64）で78.6テラフロップス（システム概要ページでは78 TFと丸めて記載）、ベクトル半精度で157.3テラフロップス、FP8 AI学習で5ペタフロップスと評価されている。[3][4] システム全体の合計ピーク性能として、OLCFはFP64 HPCワークロードで317ペタフロップス、FP8 AI学習で20エクサフロップス、FP4 AI推論で40エクサフロップスを公表している。[3]

## Luxスーパーコンピュータのソフトウェア環境、スケジューリングおよびストレージ

LuxスーパーコンピュータはRed Hat Enterprise Linux（RHEL）バージョン9.8を実行し、AMD ROCmオープンソフトウェアスタックおよびROCrランタイムを採用しており、各AMD Instinct MI355Xはジョブスケジューラおよび`ROCR_VISIBLE_DEVICES`に対して個別のGPUとして認識される。[1][4] 同一ハードウェア上で従来のスーパーコンピューティングシミュレーションとクラウドネイティブなAIワークロードの双方を支援するため、OLCFはLuxをSlurmとKubernetesによって管理される2つのスケジューリングパーティションに分割している。[1][3][4] SlurmパーティションとKubernetesパーティションの相対的な規模は、ユーザー需要に応じて経時的に動的に調整される。[3]

ローカルの高速スクラッチ入出力用として、各Lux計算ノードは8基の3.2 TB不揮発性メモリエクスプレス（NVMe）ソリッドステートドライブを搭載し、ノードあたり24 TB超のローカルNVMeストレージを提供する。[3][4] 共有並列ストレージとして、LuxはHPE ClusterStorハードウェア上に構築されたOLCFセンター全体のLustre並列ファイルシステムであるOrion（`/lustre/orion/`）をマウントしている。[3][4] OLCFシステム概要ではOrionの容量を600ペタバイト超と記載している一方、Luxユーザーガイドではファイルの成長に合わせてファイルストライピングを自動調整するProgressive File Layout（PFL）を備えた679 PBの実効名前空間として明記している。[3][4]

OrionはLux、Frontier、Rikerクラスター、およびOLCFデータ転送ノード間で共有されているため、FrontierとLuxの双方に計算資源割り当てを持つ研究チームは、Frontier上で大規模なシミュレーションデータセットを生成してOrionへ直接書き込み、外部へのデータ移動を行うことなくLux上でそのデータセットを用いたAIモデル学習を実行できる。[3][4] また、Luxユーザーにはホームおよびプロジェクトディレクトリ用のOLCFセンター共通ネットワークファイルシステム（NFS）と、OLCFのニアラインアーカイブストレージシステムであるKronosへのアクセスも提供される。[4]

## Luxスーパーコンピュータの割り当て方針、商用アクセスおよびセキュリティ管理

Luxスーパーコンピュータは、米国エネルギー省とAMDの間で均等に分割された共同投資ガバナンスモデルの下、年間350万ノード時間を提供する。[1][3] Luxの年間ノード時間の約半分はオープンな科学的発見のためのDOEジェネシス・ミッションに専用割り当てされ、残りの半分はAMDの技術開発・検証用、ならびにDOEユーザー施設料金に基づく公的・民間部門パートナーによる有償アクセス用に配分されている。[1][3]

有償の専有またはパートナー割り当てについて、OLCFは6か月間あたり最低175,000ノード時間の契約を要件としており、プロジェクト期間は6か月から5年間で、任意の月から柔軟に開始できる。[3] OLCFによると、175,000ノード時間の契約により、6か月間で延べ18日間にわたる400ノード（3,200 GPU）規模の実行や、約40ノードでの6か月間連続実行といったワークロードに対応できる。[3] パートナージョブは単一ノード実行からシステム全体に近い規模まで拡張可能であるが、常駐サービス用に予約されたノードを考慮し、フルシステムジョブの上限は4,000 GPUをわずかに下回る規模に制限される。[3]

2026-11-23時点で、LuxはFrontierと同じセキュリティベースラインであるDOE Moderateセキュリティ管理の下で運用されており、輸出管理対象のアプリケーションおよびデータの処理が許可されている。[3] OLCFはLuxにDOE Moderate-Enhanced管理を追加する計画を発表しており、これにより国際武器取引規則（ITAR）対象ワークロードやHIPAAに基づく保護対象保健情報（PHI）への適用範囲拡大が見込まれている。[3]

## DOEジェネシス・ミッションにおけるLuxスーパーコンピュータの役割と科学ワークロード

Luxスーパーコンピュータは、DOE傘下の17の国立研究所全体でスーパーコンピューティング、AI基盤モデル、量子システム、および実験施設を統合する国家イニシアチブである米国エネルギー省ジェネシス・ミッションにおいて、初の専用AIファクトリーかつ主要な計算インフラ増強拠点としての役割を担っている。[1][2][5] ジェネシス・ミッションの中で、ORNLは研究所の計算資源、データ、および高速ネットワークを連携させるフェデレーション型発見プラットフォームであるAmerican Science Cloud（AmSC）も主導している。[2]

2026年11月16日の公開発表において、ORNLとAMDはLux上で稼働するジェネシス・ミッションの代表的な3つの研究割り当てを詳述した。[1][2][5][8]

- 核融合発電所設計（FADO）：Fusion Agentic Design Orchestratorは、エージェント型AIワークフローを用いて高精度プラズマ・工学シミュレーション、ロボット保守システム設計、および核融合パイロットプラント向けの信頼性・可用性・保守性・検査性（RAMI）基準を統合する。[1][5][8]
- 材料開発および先端製造：米国産業界向けにカスタムマルチモーダル基盤モデルを学習するAI基盤モデルファクトリーであり、3Dプリントおよび積層造形部品向け合金微細組織の予測・設計などが含まれる。[1][5][8]
- 地球システムおよび長期水資源予測：テネシー川流域開発公社（TVA）地域における水力発電および火力発電所の冷却運用を支援するため、数週間から数年先までの水資源利用可能性、河川流量、および河川水温を予測するAI予測プロジェクトである。[1][5][8]

2026年11月16日のORNL発表によると、ORNLの研究者はジェネシス・ミッション第1フェーズにおいて上記以外の6プロジェクトを主導するとともに30の多機関共同プロジェクトに参加しており、第2フェーズにおいてもさらに6プロジェクトを主導している。[1][2]

## よくある質問

### Luxスーパーコンピュータとは何ですか？どこに設置されていますか？

Luxは、米国テネシー州オークリッジにある米国エネルギー省（DOE）オークリッジ国立研究所（ORNL）のオークリッジ・リーダーシップ・コンピューティング施設（OLCF）が運用する、AMDベースのスーパーインテリジェンス（SI：大統領令14434号に基づく米国連邦政府の人工知能の呼称）および高性能計算（HPC）スーパーコンピュータです。DOEとAMDの官民共同投資パートナーシップの下でヒューレット・パッカード・エンタープライズ（HPE）が構築し、2026年11月16日に科学研究者向けに公開されました。 [1][2][4][5]

### LuxのTOP500順位とピーク性能はどのくらいですか？

2026年11月16日に発表された第68回TOP500リストにおいて、LuxはHigh Performance Linpack（HPL）ベンチマークスコア220.79ペタフロップスを記録し、世界14位に初登場しました。2026-11-23時点のOLCFシステム仕様では、モデリングおよびシミュレーション向けのFP64で317ペタフロップス、AI学習向けのFP8で20エクサフロップス、AI推論向けのFP4で40エクサフロップスの理論ピーク性能も公表されています。 [1][3][5]

### Luxの各計算ノードにはどのようなハードウェアとプロセッサが採用されていますか？

2026-11-23時点のOLCF Luxユーザーガイドによると、Luxは504台のHPE ProLiant Compute XD685ノードと4,032基のAMD Instinct MI355X GPUで構成されています。各計算ノードには、3 TBのDDR5システムメモリを備えた64コアAMD EPYC 9575F CPU 2基、8基のAMD Instinct MI355X GPU（各GPUは帯域幅8 TB/sの288 GB HBM3Eメモリと8基のAccelerated Compute Dieを搭載）、8基の3.2 TBローカルNVMe SSD（ノードあたり24 TB超）、および400G Ultra Ethernet対応AMD Pensando NICが搭載されています。 [3][4][5]

### Luxの計算時間はジェネシス・ミッションとパートナー間でどのように配分されていますか？

OLCFはLuxの年間350万ノード時間の約半分をオープンな科学的発見のための米国エネルギー省ジェネシス・ミッションに割り当て、残りの半分をAMDの開発・検証用およびDOEユーザー施設料金に基づく公的・民間パートナーの有償専有利用向けに提供しています。有償パートナー枠は6か月あたり最低175,000ノード時間の契約が必要であり、DOE Moderateセキュリティ管理の下で6か月から5年間利用できます。 [1][3]

### Luxはどのオペレーティングシステム、スケジューラ、ストレージシステムに対応していますか？

LuxはRed Hat Enterprise Linux（RHEL）9.8とAMD ROCmオープンソフトウェアスタックを実行し、ノードを従来のバッチHPCジョブ向けSlurmパーティションと、コンテナ化されたAI学習・推論およびエージェント型オーケストレーション向けKubernetesパーティションに分割して運用しています。すべての割り当てにおいて、OLCFのOrion Lustre並列ファイルシステム（HPE ClusterStor上の実効名前空間679 PB）とニアラインアーカイブストレージシステムKronosへのアクセスが提供されます。 [1][3][4]

### Luxスーパーコンピュータではどのような科学研究プロジェクトが実行されていますか？

2026年11月16日の発表において、ORNLとAMDはLuxに割り当てられたジェネシス・ミッションの初期3プロジェクトを紹介しました。すなわち、HPCシミュレーションとロボット保守を核融合発電所設計に統合するFusion Agentic Design Orchestrator（FADO）、材料開発および先端製造（3Dプリント合金の微細組織など）向けのAI基盤モデルファクトリー、そしてテネシー川流域開発公社地域の水資源利用可能性・河川流量・河川水温を予測する地球システム予測プロジェクトです。 [1][2][5][8]

## 引用できる文

- Luxスーパーコンピュータは2026年11月16日に米国エネルギー省オークリッジ国立研究所で科学研究者向けに公開され、第68回TOP500リストでHigh Performance Linpack性能220.79ペタフロップスを記録して世界14位に初登場した。 [1][2][5]
- 2026-11-23時点のOLCF Luxユーザーガイドによると、Luxは504台のHPE ProLiant Compute XD685ノードで構成され、合計4,032基のAMD Instinct MI355X GPUとノードあたり2基の64コアAMD EPYC 9575F CPUを搭載している。 [4]
- Luxに搭載された各AMD Instinct MI355X GPUは、8基のAccelerated Compute Die（256コンピュートユニット）にわたりピークメモリ帯域幅8 TB/sの288 GB HBM3Eメモリを備え、システム全体で約1.1ペタバイトのHBM3E容量を提供する。 [3][4]
- 2026-11-23時点で、オークリッジ・リーダーシップ・コンピューティング施設（OLCF）はLuxのピーク性能をFP4 AI推論で40エクサフロップス、FP8 AI学習で20エクサフロップス、FP64高性能計算モデリングおよびシミュレーションで317ペタフロップスと公表している。 [3]
- Luxの年間350万ノード時間のうち半分は米国エネルギー省のジェネシス・ミッション（Genesis Mission）に充てられ、残りの半分はAMDおよび6か月あたり175,000ノード時間以上を契約する民間・公的機関パートナーの有償利用枠として確保されている。 [1][3]
- Luxの計算ノードはRed Hat Enterprise Linux 9.8を実行し、リソースをSlurmとKubernetesのスケジューリングパーティションに分割するとともに、ノードあたり8基の3.2 TBローカルNVMeドライブを備え、OLCFのOrion Lustre並列ファイルシステム（実効名前空間679 PB）をマウントしている。 [3][4]
- Luxにおけるジェネシス・ミッションの初期割り当て課題には、核融合発電所設計向けのFusion Agentic Design Orchestrator（FADO）、材料および先端製造向けの基盤モデルファクトリー、テネシー川流域開発公社地域向けの長期水資源・河川流量予測が含まれる。 [1][2][5][8]
- 米国エネルギー省、ORNL、AMD、およびHPEは、2025年10月27日に官民共同投資パートナーシップの下でLuxおよびDiscoveryスーパーコンピュータプロジェクトを発表した。 [6]

## 年表

- 2025-10-27: 米国エネルギー省、オークリッジ国立研究所、AMD、およびHPEがLuxおよびDiscoveryスーパーコンピュータプロジェクトを発表した。 [6]
- 2026-11-16: LuxスーパーコンピュータがDOEジェネシス・ミッション初のAIファクトリーとしてORNLで科学研究者向けに公開され、第68回TOP500リストで220.79ペタフロップスを記録して14位に初登場した。 [1][2][5]
- 2028: Luxと同時に発表されたORNLの次世代HPE Cray GX5000フラッグシップスーパーコンピュータDiscoveryの納入予定年である。 [1][6]

## 出典

1. Lux SI+HPC Supercomputer Debuts in the Top500, Advances Genesis Mission Goals – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). 公開 2026-11-16. https://www.olcf.ornl.gov/2026/11/16/lux-genesis-mission/ (閲覧 2026-11-23; tier 1: government or public registry)
2. Lux SI+HPC supercomputer debuts in the Top500, advances Genesis Mission goals – Oak Ridge National Lab. Oak Ridge National Laboratory. 公開 2026-11-16. https://www.ornl.gov/news/lux-sihpc-supercomputer-debuts-in-the-top500-advances-genesis-mission-goals/ (閲覧 2026-11-23; tier 1: government or public registry)
3. Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). https://www.olcf.ornl.gov/olcf-resources/compute-systems/lux/ (閲覧 2026-11-23; tier 1: government or public registry)
4. Lux User Guide - OLCF User Documentation. Oak Ridge Leadership Computing Facility (ORNL). https://docs.olcf.ornl.gov/systems/lux_user_guide.html (閲覧 2026-11-23; tier 1: government or public registry)
5. Lux Supercomputer Opens to Scientific Users at Oak Ridge - AMD Newsroom. Advanced Micro Devices (AMD). 公開 2026-11-16. https://newsroom.amd.com/news/amd-powered-lux-supercomputer-opens-scientific-users/ (閲覧 2026-11-23; tier 3: official site)
6. ORNL, AMD, and HPE to Deliver DOE’s Newest AI Supercomputers: Discovery and Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). 公開 2025-10-27. https://www.olcf.ornl.gov/2025/10/27/ornl-amd-and-hpe-to-deliver-does-newest-ai-supercomputers-discovery-and-lux/ (閲覧 2026-11-23; tier 1: government or public registry)
7. Oak Ridge National Laboratory unveils Lux supercomputer - DCD. Data Center Dynamics. 公開 2026-11-17. https://www.datacenterdynamics.com/en/news/oak-ridge-national-laboratory-unveils-lux-supercomputer/ (閲覧 2026-11-23; tier 2: academic or news)
8. AMD opens up its new Lux supercomputer, powering everything from nuclear fusion to weather predictions | TechRadar. TechRadar. 公開 2026-11-21. https://www.techradar.com/pro/amd-opens-up-its-new-lux-supercomputer-powering-everything-from-nuclear-fusion-to-weather-predictions (閲覧 2026-11-23; tier 2: academic or news)

## このページを引用する

Mimirwiki. "Luxスーパーコンピュータ." 版 63cc2d87, 2026-11-23. https://mimirwiki.com/ja/wiki/lux-supercomputer
