# Offmap Factories Decisions (HOI4 MOD)

ディシジョンを選択すると、マップ外（オフマップ）に以下を追加します。

| ディシジョン | 効果 |
| --- | --- |
| 民需工場を20追加 | 民需工場 +20（マップ外） |
| 軍需工場を20追加 | 軍需工場 +20（マップ外） |
| 造船所を20追加 | 造船所 +20（マップ外） |

また「航空技術」カテゴリに以下を追加します。

| ディシジョン | 効果 |
| --- | --- |
| 1940年までの航空技術を一括習得 | By Blood Alone 航空ツリーの1940年以前の技術（機体・エンジン・兵装モジュール・輸送機等）をすべて習得し、空軍経験値 +100 |

さらに「海軍技術」カテゴリに以下を追加します。

| ディシジョン | 効果 |
| --- | --- |
| 1940年までの海軍技術を一括習得 | Man the Guns 海軍ツリーの1940年以前の技術（船体・装甲・対潜・魚雷・機雷・輸送/上陸・ダメコン・射撃管制）とレーダー技術（1940年まで）をすべて習得し、海軍経験値 +100 |

さらに「補給」カテゴリに以下を追加します。

| ディシジョン | 効果 |
| --- | --- |
| 鉄道の夜明け | 所有しているステートの戦勝点があるプロヴィンスすべてに補給ハブを即時設置し、民間鉄道（`basic_train`）の技術を習得 |
| 鉄道網の整備 | 隣接する自国ステートの補給ハブ同士を、自国支配地のみを通る最短経路の鉄道（レベル1）で結ぶ。「鉄道の夜明け」の実行が前提条件 |

- 補給ハブ間の鉄道は各ステートの最良ノード（首都 > 補給ハブ > 港）同士を結びます。1ステートに複数の戦勝点がある場合、鉄道で結ばれるのはそのうち1つです。実行するたびに鉄道レベルが加算されます
- 補給ハブディシジョンは何度でも実行可能（新たに獲得した領土にも設置できます）。補給ハブが機能するには首都と鉄道でつながっている必要があります

- 海軍技術ディシジョンは1回のみ実行可能。Man the Guns 前提で、旧海軍ツリー・特殊プロジェクト・国家固有技術は含みません
- 航空技術ディシジョンは1回のみ実行可能。航空ドクトリン・レーダー・ロケットは含みません
- By Blood Alone（航空機設計）前提です。旧航空ツリー（DLCなし）の技術は含みません
- 工場系ディシジョンは政治力コスト 0、何度でも実行可能
- AI は使用しません（`ai_will_do = 0`）
- 効果は `add_offsite_building` を使用しているため、州の建設スロットを消費しません

## インストール

1. このリポジトリを `Documents/Paradox Interactive/Hearts of Iron IV/mod/offmap_factories/` に配置
2. 同じ `mod` フォルダに `offmap_factories.mod` を作成し、以下を記述

```
version="1.0.0"
tags={
	"Gameplay"
}
name="Offmap Factories Decisions"
supported_version="1.*"
path="mod/offmap_factories"
```

3. ランチャーで MOD を有効化

## 構成

```
descriptor.mod
common/decisions/categories/offmap_factories_categories.txt
common/decisions/offmap_factories_decisions.txt
common/decisions/air_tech_bundle_decisions.txt
common/decisions/naval_tech_bundle_decisions.txt
common/decisions/supply_hub_decisions.txt
localisation/english/offmap_factories_l_english.yml   (UTF-8 BOM付き)
```

※ 日本語化MOD環境を想定し、ローカライズは `l_english` に日本語で記述しています。
