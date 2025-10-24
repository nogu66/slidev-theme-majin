---
theme: ./
---

<style>
:deep(strong) {
  color: #4285F4;
  font-weight: 700;
}
</style>

---
layout: title
date: 2025.10.25
---

# Slidev Theme Majin

Google Slidesスタイルのプロフェッショナルテーマ

17種類以上のレイアウトでビジネスプレゼンテーションを強力にサポート

---
layout: section
sectionNo: 1
---

# 基本レイアウト

title, section, content, closing

---
layout: content
subhead: Google Slidesスタイルの洗練されたデザインシステム
---

<template v-slot:title>
Content レイアウト - 1カラム
</template>

- **17種類以上のレイアウト** - タイトル、比較、プロセス、KPIなど多彩なレイアウト
- **Google Slidesスタイル** - 洗練されたカラーリングと視覚的階層構造
- **レスポンシブデザイン** - どんな画面サイズでも美しく表示
- **プロップスベース** - 簡単な設定で高度な表現が可能
- **開発者フレンドリー** - Vue 3とTypeScriptで構築

---
layout: content
twoColumn: true
subhead: 1カラムと2カラムのレイアウトをプロップスで簡単に切り替え
---

<template v-slot:title>
Content レイアウト - 2カラム
</template>

**左カラム**
- プロップス \`twoColumn: true\` で2カラムに
- マークダウンで簡単に記述
- 自動的にグリッド配置
- レスポンシブ対応

**右カラム**
- コード例、画像、リストなど
- 柔軟なコンテンツ配置
- バランスの取れたレイアウト
- 視認性の高いデザイン

---
layout: section
sectionNo: 2
---

# 比較レイアウト

compare, stats-compare

---
layout: compare
leftTitle: 従来のスライド
rightTitle: Theme Majin
subhead: 比較レイアウトで2つの概念を視覚的に対比
---

<template v-slot:title>
Compare レイアウト - 左右比較
</template>

<template v-slot:left>

- 限られたレイアウトオプション
- 単調なデザイン
- カスタマイズが困難
- 視覚的インパクトが弱い
- テンプレートの制約

</template>

<template v-slot:right>

- **17種類以上**の豊富なレイアウト
- **プロフェッショナル**なデザイン
- **柔軟な**カスタマイズ性
- **強力な**視覚表現
- **自由度の高い**構成

</template>

---
layout: stats-compare
leftTitle: 導入前
rightTitle: 導入後
subhead: 導入効果を具体的な数値で示す
---

<template v-slot:title>
Stats Compare レイアウト - 数値比較
</template>

<script setup>
const statsItems = [
  { label: '開発サイクル時間', leftValue: '160時間', rightValue: '80時間', trend: 'down' },
  { label: '品質スコア', leftValue: '75点', rightValue: '95点', trend: 'up' },
  { label: 'バグ検出数', leftValue: '45件', rightValue: '12件', trend: 'down' },
  { label: '顧客満足度', leftValue: '70%', rightValue: '92%', trend: 'up' },
]
</script>

<StatsCompare :stats="statsItems" />

---
layout: section
sectionNo: 3
---

# プロセス・時系列

process, timeline

---
layout: process
subhead: ステップバイステップで工程を明確に表現
---

<template v-slot:title>
Process レイアウト - 開発プロセス
</template>

<ol>
<li>**要件定義** - ステークホルダーとの対話を通じて、プロジェクトの目標と範囲を明確化</li>
<li>**設計フェーズ** - システムアーキテクチャ、データベース設計、UI/UXデザインを策定</li>
<li>**実装とテスト** - アジャイル開発手法でコードを実装し、継続的にテストを実施</li>
<li>**デプロイと運用** - CI/CDパイプラインで本番環境にリリースし、監視体制を構築</li>
<li>**改善サイクル** - ユーザーフィードバックを収集し、継続的な機能改善を実施</li>
</ol>

---
layout: timeline
subhead: プロジェクトのマイルストーンを時系列で表示
---

<template v-slot:title>
Timeline レイアウト - プロジェクト計画
</template>

<script setup>
const milestones = [
  { date: '2025.01', label: 'プロジェクトキックオフ', state: 'done' },
  { date: '2025.03', label: 'α版リリース', state: 'done' },
  { date: '2025.06', label: 'β版リリース', state: 'next' },
  { date: '2025.09', label: '正式版リリース', state: 'todo' },
  { date: '2025.12', label: '機能拡張', state: 'todo' },
]
</script>

<Timeline :milestones="milestones" />

---
layout: section
sectionNo: 4
---

# カード系レイアウト

cards, header-cards, bullet-cards, kpi

---
layout: cards
columns: 3
subhead: グリッド形式で情報を整理して表示
---

<template v-slot:title>
Cards レイアウト - 3カラム
</template>

<script setup>
const items3col = [
  { title: '高速パフォーマンス', desc: '最新の技術スタックで高速かつ軽量な動作を実現' },
  { title: '堅牢なセキュリティ', desc: '業界標準のセキュリティ対策と定期的な脆弱性診断' },
  { title: 'スケーラビリティ', desc: 'マイクロサービス設計で成長に合わせて柔軟に拡張' },
  { title: 'クラウドネイティブ', desc: 'Kubernetes対応で可用性とスケーラビリティを確保' },
  { title: 'DevOps統合', desc: 'CI/CD完備で開発から本番までスムーズなデプロイ' },
  { title: 'モニタリング', desc: 'リアルタイム監視とアラートで問題を即座に検知' },
]
</script>

<Cards :items="items3col" />

---
layout: cards
columns: 2
subhead: 2カラムでより詳細な情報を表示
---

<template v-slot:title>
Cards レイアウト - 2カラム
</template>

<script setup>
const items2col = [
  {
    title: 'エンタープライズ向けSaaS',
    desc: '大規模組織向けの包括的なクラウドソリューション。マルチテナント対応、高度な権限管理、エンタープライズSSO、詳細な監査ログ機能を提供。'
  },
  {
    title: 'スタートアップ向けパッケージ',
    desc: '迅速な立ち上げを支援する軽量かつ柔軟なソリューション。必要な機能だけを選択でき、成長に合わせて段階的にスケールアップ可能。'
  },
  {
    title: 'データ分析プラットフォーム',
    desc: 'ビッグデータを活用したインサイト創出。機械学習モデルの統合、リアルタイムダッシュボード、予測分析機能を搭載。'
  },
  {
    title: 'モバイルファースト開発',
    desc: 'ネイティブアプリとWebアプリの統合開発環境。React Native、Flutter対応で効率的なクロスプラットフォーム開発を実現。'
  },
]
</script>

<Cards :items="items2col" />

---
layout: header-cards
columns: 3
subhead: ヘッダー部分を強調したカードデザイン
---

<template v-slot:title>
Header Cards レイアウト - 開発プロセス
</template>

<script setup>
const headerItems = [
  {
    title: '計画フェーズ',
    desc: 'プロジェクトの目標と要件を明確にし、詳細なスケジュールとリソース配分を計画します。ステークホルダーとの合意形成が重要です。'
  },
  {
    title: '実行フェーズ',
    desc: '計画に基づいてタスクを実行し、定期的に進捗を確認します。スプリントレビューとデイリースタンドアップで透明性を確保。'
  },
  {
    title: '検証フェーズ',
    desc: '成果物を包括的にレビューし、品質基準を満たしているか確認します。必要に応じて改善とリファクタリングを実施。'
  },
]
</script>

<HeaderCards :items="headerItems" />

---
layout: bullet-cards
subhead: 最大3つの重要ポイントを強調表示（番号付き）
---

<template v-slot:title>
Bullet Cards レイアウト - 重要な3つのポイント
</template>

<script setup>
const bulletItems = [
  {
    title: 'ユーザー中心設計',
    desc: 'ユーザーのニーズと行動パターンを深く理解し、直感的で使いやすいインターフェースを設計します。ユーザビリティテストを繰り返し実施し、継続的に改善を図ります。'
  },
  {
    title: 'データドリブン意思決定',
    desc: '定量的なデータ分析とA/Bテストに基づいて機能開発の優先順位を決定します。仮説検証サイクルを高速化し、ROIの高い施策に集中投資します。'
  },
  {
    title: 'アジャイルイテレーション',
    desc: '短いスプリントで価値を提供し、市場フィードバックを素早く取り込みます。失敗から学び、ピボットを恐れない文化を醸成することで競争優位性を確立します。'
  },
]
</script>

<BulletCards :items="bulletItems" />

---
layout: kpi
columns: 4
subhead: 主要指標を一目で把握できるダッシュボード形式
---

<template v-slot:title>
KPI レイアウト - 事業指標（4カラム）
</template>

<script setup>
const kpiItems4 = [
  { label: '月間売上高', value: '¥150M', change: '+25%', status: 'good' },
  { label: 'アクティブユーザー', value: '50,000', change: '+15%', status: 'good' },
  { label: '運用コスト', value: '¥30M', change: '-10%', status: 'good' },
  { label: '解約率', value: '2.5%', change: '+0.5%', status: 'bad' },
]
</script>

<Kpi :items="kpiItems4" />

---
layout: kpi
columns: 3
subhead: 3カラムでより大きく表示
---

<template v-slot:title>
KPI レイアウト - マーケティング指標（3カラム）
</template>

<script setup>
const kpiItems3 = [
  { label: 'コンバージョン率', value: '4.2%', change: '+0.8%', status: 'good' },
  { label: '平均顧客単価', value: '¥12,500', change: '+5%', status: 'good' },
  { label: 'リピート率', value: '68%', change: '-2%', status: 'bad' },
]
</script>

<Kpi :items="kpiItems3" />

---
layout: section
sectionNo: 5
---

# データ表示レイアウト

table, progress

---
layout: table
subhead: データを構造化して見やすく表示
---

<template v-slot:title>
Table レイアウト - プラン比較表
</template>

<script setup>
const headers = ['機能', 'Starter', 'Professional', 'Enterprise']
const rows = [
  ['月額料金', '¥980', '¥4,980', '要相談'],
  ['ユーザー数', '5人まで', '50人まで', '無制限'],
  ['ストレージ', '10GB', '100GB', '1TB以上'],
  ['プロジェクト数', '3件', '無制限', '無制限'],
  ['サポート', 'メール', 'チャット', '専任担当'],
  ['SLA保証', '-', '99.5%', '99.9%'],
]
</script>

<Table :headers="headers" :rows="rows" />

---
layout: progress
subhead: プロジェクトやタスクの進捗を視覚的に表示
---

<template v-slot:title>
Progress レイアウト - 開発進捗状況
</template>

<script setup>
const progressItems = [
  { label: 'フロントエンド開発', percent: 85 },
  { label: 'バックエンドAPI開発', percent: 70 },
  { label: 'データベース設計', percent: 90 },
  { label: 'セキュリティ監査', percent: 45 },
  { label: 'ユーザビリティテスト', percent: 60 },
  { label: 'ドキュメント作成', percent: 30 },
]
</script>

<Progress :items="progressItems" />

---
layout: section
sectionNo: 6
---

# その他のレイアウト

quote, faq

---
layout: quote
text: シンプルさは究極の洗練である。デザインは機能だけでなく、感情にも訴えかけなければならない。
author: Leonardo da Vinci
subhead: 偉人の言葉を効果的に引用
---

<template v-slot:title>
Quote レイアウト - 引用表示
</template>

---
layout: faq
subhead: よくある質問をQ&A形式で整理
---

<template v-slot:title>
FAQ レイアウト - よくある質問
</template>

<script setup>
const faqItems = [
  {
    q: 'このテーマは無料で使用できますか？',
    a: 'はい、完全に無料でオープンソースです。MITライセンスの下で公開されており、個人利用・商用利用ともに自由に使用できます。'
  },
  {
    q: 'カスタマイズは簡単にできますか？',
    a: 'はい、CSSとVue.jsの基本的な知識があれば、色やフォント、レイアウトを簡単にカスタマイズできます。プロップスベースの設計により、コードを変更せずに多くの調整が可能です。'
  },
  {
    q: 'どのようなプロジェクトに適していますか？',
    a: 'ビジネスプレゼンテーション、技術カンファレンス、教育資料、営業資料、社内報告会など、あらゆる場面で使用できます。特にデータや比較を含むプレゼンテーションに最適です。'
  },
]
</script>

<Faq :items="faqItems" />

---
layout: closing
---

# ご清聴ありがとうございました

Theme Majinで素晴らしいプレゼンテーションを作成しましょう

**GitHub**: https://github.com/slidevjs/slidev
**ドキュメント**: https://sli.dev
