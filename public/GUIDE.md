# 開発生産管理アプリ 修正ガイド

## ファイル構成
```
public/index.html  ← アプリ本体（これ1ファイルだけ）
```

## 編集方法
1. https://github.com/u-donchan/management-app にアクセス
2. public/index.html を開く → 鉛筆アイコンで編集
3. 修正して「Commit changes」で保存
4. 1分以内にアプリに自動反映

## よく変更する箇所（index.html内）

### 会社名の変更・追加
検索: `COMPANIES`
```javascript
const COMPANIES = ['クロダルマ','シンメン','NSP'];
// → 追加する場合:
const COMPANIES = ['クロダルマ','シンメン','NSP','新しい会社名'];
```

### カテゴリの変更・追加
検索: `CATEGORIES`
```javascript
const CATEGORIES = ['ファン','バッテリー','ケーブル','充電器','その他'];
```

### マスター設定の選択肢を変更
検索: `MASTER_DEFS`
```javascript
const MASTER_DEFS = [
  {key:'package', label:'パッケージ', opts:['新規','去年と同様','不要']},
  ...
];
```

### 開発フェーズの項目を変更・追加
検索: `DEV_COLS`
```javascript
const DEV_COLS = [
  {key:'factoryQuote', label:'工場見積り', grp:'A'},
  // → 新しい項目を追加する場合、末尾に追加:
  {key:'newItem', label:'新しい項目', grp:'A'},
];
```

### 副資材フェーズの項目
検索: `SUB_LABELS`

### 量産フェーズの項目
検索: `PROD_COLS`

### shipフェーズの項目
検索: `SHIP_COLS`
```javascript
const SHIP_COLS = [
  {key:'shipDoc', label:'船積み書類依頼'},
  // → 項目名を変える場合は label を変更するだけ
];
```

### 入力制限ルール
検索: `isDevDis` `isSubDis` `isProdDis`
- isDevDis: 開発フェーズのグレーアウト判定
- isSubDis: 副資材フェーズのグレーアウト判定
- isProdDis: 量産フェーズのグレーアウト判定

## 注意
- 修正前にブラウザの「Ctrl+F」で該当箇所を検索すると見つけやすい
- カンマ(,)やクォーテーション(')の閉じ忘れに注意
- 壊してしまった場合はGitHubの「History」から前のバージョンに戻せる
