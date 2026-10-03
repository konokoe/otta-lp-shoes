# 納品ファイル管理

## 命名規則

```
shoes_v{通し番号}_{YYYYMMDD}.zip
```

- 日付が基本。通し番号は **同じ日に複数回納品するときだけ** +1 する
  （その日の1回目は必ず `v1`。日付が変われば番号も `v1` に戻る）
- 日付は zip を作成した日
- 中身は `shoes/` フォルダ1つ。クライアントは `/lp/` 配下に展開して `/lp/shoes/` になる

## 作成手順

```bash
git checkout main
git merge --ff-only dev
npm run build
# dist/ の中身を shoes/ に入れて zip 化
git checkout dev && npm run build   # dev の dist を戻す
```

## 納品履歴

| バージョン | 日付 | main の HEAD | 内容 |
|---|---|---|---|
