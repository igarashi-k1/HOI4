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
| 1940年までの航空技術を一括習得 | 1940年以前の航空機関連技術（機体・各機種・エンジン・兵装モジュール等）をすべて習得し、空軍経験値 +100 |

- 航空技術ディシジョンは1回のみ実行可能。航空ドクトリン・レーダー・ロケットは含みません
- By Blood Alone の有無どちらでも動くよう、新旧両方の航空ツリーの技術を習得します
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
localisation/english/offmap_factories_l_english.yml   (UTF-8 BOM付き)
```

※ 日本語化MOD環境を想定し、ローカライズは `l_english` に日本語で記述しています。
