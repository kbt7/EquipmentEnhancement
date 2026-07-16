# 装備強化シミュレーター

NEXT ADVENTURE の装備強化システムを検証するためのシミュレーターです。
`index.html` 1ファイルだけで動作する完全な静的ページで、サーバーや外部ライブラリは不要です（データはブラウザの localStorage に保存されます）。

## 機能

- **鍛冶屋（強化）**: 装備＋同じ強化値の強化書で強化。成功(+1)/大成功(+2)/超大成功(+3)/失敗（強化書のみ消費）。ランクと強化値による成功率補正を反映。強化書解読キット使用で100%成功(+1)のみに
- **強化書作成（変換）**: 同じ強化値の装備2個 → 強化書1枚（通常は最大10ペア、検証用の一括変換あり）
- **検証**: 強化書無制限仮定のモンテカルロ試行（最大10万回）、解読キットをどの強化値で使うべきかの最適戦略計算（動的計画法＋モンテカルロ実測）、全ランク比較・キット価格感度分析
- **確率・価格表**: 実効成功率一覧、キット確定強化前提の価格表、ランク別の +k 強化書作成価格（最適戦略調達）

装備価格・キット価格（zen）は画面左の「価格設定」で自由に変更でき、各種価格表・分析に即時反映されます（初期値: 装備 2 zen、キット 3 zen）。

## GitHub Pages での公開手順

1. このフォルダを GitHub リポジトリとして push する

   ```sh
   git init
   git add index.html README.md
   git commit -m "装備強化シミュレーター"
   git branch -M main
   git remote add origin https://github.com/kbt7/EquipmentEnhancement.git
   git push -u origin main
   ```

2. GitHub のリポジトリページで **Settings → Pages** を開く
3. **Source** を「Deploy from a branch」、Branch を `main` / `/ (root)` にして保存
4. 数分後に `https://kbt7.github.io/EquipmentEnhancement/` で公開されます

ローカルで試す場合は `index.html` をブラウザで開くだけで動きます。
