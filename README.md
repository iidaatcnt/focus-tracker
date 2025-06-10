# Focus Tracker - 集中度可視化ツール

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/iidaatcnt/focus-tracker)

リアルタイムでユーザーの集中度を可視化するWebアプリケーションです。マウスクリックとキーストロークの頻度から集中レベルを算出し、美しいグラフで表示します。

## 🚀 主な機能

### 📊 リアルタイム可視化
- **集中度グラフ**: HTML5 Canvasを使用したリアルタイム描画
- **集中度メーター**: 0-100点の視覚的表示
- **動的な色分け**: 集中レベルに応じた色変化（赤→黄→緑）

### 📈 アクティビティ検出
- **マウスクリック検出**: 全画面でのクリック数をカウント
- **キーストローク検出**: キーボード入力を検出
- **スマートな集中度算出**: 適度なアクティビティを高評価、過度/不足なアクティビティは低評価

### 📱 統計情報
- セッション時間の表示
- 平均集中度・最高集中度
- 総クリック数・総キーストローク数
- リアルタイム更新

### 🎮 操作機能
- **開始/一時停止/リセット**: 柔軟なセッション管理
- **ステータス表示**: 現在の状態を視覚的に表示
- **レスポンシブデザイン**: モバイル対応

## 🛠️ 技術仕様

- **HTML5 Canvas**: 高性能なグラフ描画
- **JavaScript ES6+**: モダンな実装
- **CSS Grid & Flexbox**: レスポンシブレイアウト
- **バニラJS**: フレームワーク不要

## 📊 集中度算出アルゴリズム

```javascript
// 理想的なアクティビティレベル: 1秒あたり8回
const idealActivity = 8;
const currentActivity = clickCount + keystrokeCount;

// 集中度計算
if (currentActivity === 0) {
    focusScore = 0; // 非活動
} else if (currentActivity <= idealActivity) {
    focusScore = (currentActivity / idealActivity) * 100;
} else {
    // 過度な活動は集中度を下げる
    const excess = currentActivity - idealActivity;
    focusScore = Math.max(100 - (excess * 10), 20);
}
```

## 🚀 デプロイ

### Vercelで簡単デプロイ
1. GitHubリポジトリをVercelに接続
2. 自動デプロイが開始
3. 数秒で本番環境が利用可能

### ローカル実行
```bash
# HTTPサーバーを起動（Python例）
python -m http.server 8000

# または Node.js
npx serve .
```

## 📈 使用方法

1. **開始ボタン**をクリックしてトラッキング開始
2. 通常通りPC作業を継続
3. リアルタイムで集中度グラフを確認
4. 必要に応じて一時停止・リセット

## 🎯 想定用途

- **ポモドーロテクニック**と組み合わせた集中管理
- **リモートワーク**での自己管理
- **学習セッション**の質的評価
- **生産性分析**のためのデータ収集

## 🔧 カスタマイズ

設定可能なパラメータ：
- `updateInterval`: 更新間隔（デフォルト: 1000ms）
- `timeWindow`: 移動平均の時間窓（デフォルト: 60秒）
- `maxDataPoints`: 最大データポイント数（デフォルト: 300点）
- `idealActivity`: 理想的活動レベル（デフォルト: 8回/秒）

## 📱 ブラウザ対応

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 📝 ライセンス

MIT License

## 🔗 関連リンク

- [デモサイト](https://focus-tracker-iidaatcnt.vercel.app)
- [GitHub Repository](https://github.com/iidaatcnt/focus-tracker)

---

Made with ❤️ for better productivity