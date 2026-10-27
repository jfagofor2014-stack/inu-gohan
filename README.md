# 犬と休日 ごはん日記

-犬と休日- Gear & Food（佐世保市稲荷町）のお客さま向け、愛犬のごはん日記 Web アプリ。
claude.ai のチャットで作ったアーティファクト（https://claude.ai/artifact/QrUBaSYHxHu1BtBa5k6PNe）を 2026-10-27 に引き継いだもの。

- Vanilla JS 1ファイル（index.html）＋ PWA（manifest.json / sw.js）
- 保存は端末内 IndexedDB（DB `inu-gohan` v1、ストア `dogs` / `entries`）。サーバーには送らない
- 写真は長辺1440px（愛犬アイコンは400px）の JPEG に縮小して Blob 保存
- バックアップ：JSON 書き出し（写真は dataURL）／読み込み（`app: "inu-gohan"` を確認）

## ローカル確認

```
python3 -m http.server 8771
```

Service Worker は https のときだけ登録される（GitHub Pages では有効）。
コードを変えたら sw.js の `CACHE` の番号を上げる。
