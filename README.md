# Showater（ショーウォーター）

シャワーの水圧を調整して、コップに水を満たすブラウザゲーム。

- 水圧スライダーでシャワーの勢いを変えると、水の届く位置が変わる
- 「長押しで注ぐ」を押している間だけ水が出る。水タンクには限りがある
- コップの **80%以上** ためればステージクリア（90%以上で星2、98%以上で星3）
- 全30ステージ：風（突風あり）、壁、天井板、動くコップ、穴あきコップ（漏れる）などのギミック
- 進行状況と星はブラウザの localStorage に保存
- キーボード対応：←→で水圧調整 / スペース長押しで注ぐ / Enterで判定
- 音は Web Audio で合成（外部ファイルなし）。注水音とクリア／失敗のジングル

## プレイ

https://showater.mct-official.com/

単一HTMLファイル（`index.html`）だけで動作します。

## 公開方法

Cloudflare Workers（static assets）で配信。`wrangler.jsonc` の routes で `showater.mct-official.com` をカスタムドメインとして設定しています。
デプロイは `python3 ~/workspace/deploy-showater.py`（Muse のワークスペース側スクリプト）。
