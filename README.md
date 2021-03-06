# 〈API〉1.1.ゲストユーザ作成（標準化）

## 修正履歴

|  | 修正日 | 修正者 | 備考 |
| :--- | :--- | :--- | :--- |
| 1 | 2017.11.28 | 金 | 初期版 |

## 1.処理概要

| **機能区分** | ログイン |
| :--- | :--- |
| **機能名称** | ゲストユーザー作成 |
| **機能概要** | ・DBにユーザのDoc情報を作成する <br/>・JWTトークンを生成してAPPに返す |
| **Ver** | v1 |
| **Method** | POST |
| **URL** | /api/v1/login/create\_guest |

## 2.処理フロー

### 2.1.処理フロー図

### 2.2.処理詳細

|  | 処理名 | 処理詳細 | 
| :--- | :---------- | :--------------- | 
| 1 | ゲストユーザ作成 | アプリ利用規約の同意画面で同意して次の画面に遷移する前に発生する | 
| 2 | ユーザ情報保存 | データベースにユーザ情報Docを作成し、作成したDocID（_id）をユーザIDとして返す | 
| 3 | ゲストユーザ作成 | 作成したユーザIDでJWTを作成して、APP側に返す | 

## 3.リクエストデータ定義

### 3.1.ヘッダフィールド・パラメータ

|  | ヘッダフィールド | オプション<br/>パラメータ | 値（例） | 説明 |
| :--- | :---------- | :--------------- | :----- | :--------------- | 
| 1 | Content-Type | ー | application/json | 固定値：<br/>application/json;charset=UTF-8 | 
| 2 |  | charset | UTF-8 |  | 
| 3 | x-minefocus-app | ー | iOS&lt;space&gt;&lt;kCFBundleIdentifierKey&gt;&lt;space&gt;&lt;kCFBundleVersionKey&gt;<br/>OR<br/>android&lt;space&gt;パッケージ名&lt;space&gt;ビルドバージョン | iOS:<br/>ios<br/>jp.shiroyagi.kamelio 23<br/>Android：<br/>android jp.shiroyagi.kamelio 23 | 
| 4 | x-device-machine-name | ー | システムデバイスID(マシン名) &lt;space&gt;OSバージョン | 例：<br/>iPhone8;11.1.2 | 
| 5 | Authorization | Bearer | JWTトークン | ゲストユーザ作成APIのみ空白 | 

### 3.2.リクエストパラメータ／ボディ
なし

### 3.3.正常レスポンス

|  | フィールド | フィールド名 | タイプ | 桁数 | 固定値 | 省略 | 値（例） | 説明 |
| :--- | :--- | :--- | :--- | :--- | :--- |:--- |:--- |:--- |
| 1 | jwt | JWTトークン | String | ー | ー | 不可 | ー |  |

### 3.4.エラーレスポンス

[Link]

## 4.データベース定義

[Link]