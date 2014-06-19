# GET /api/v1/user_assets
ユーザーの保有する資産のリストを返す

## Resrouce URL
https://moneyforward.com/api/v1/user_assets

## Data definition

name | Description 
-----------|------------------------
code | 株式銘柄コード等。
cost | 現在未使用フィールド
entried_at | 資産取得日（特定できなければnull）
entried_price | 取得価格
jpy_rate | 円換算レート
name | 資産名称
profit | 損益
qty | 数量 (FXの場合、正の数がロング、負の数がショートポジション)
value | 評価額
created_at | レコード作成日
updated_at | レコード更新日


## Parameters
name | Description 
-----------|------------------------
account_ids <br /> *optional* | 登録金融機関ID *hashed* *Array*
asset_class_ids  <br /> *optional* | アセットクラスID *Array*
asset_subclass_ids  <br /> *optional* | アセットサブクラスID *Array*
page  <br /> *optional* | ページ番号
limit <br /> *optional* | 1ページあたりのエレメント数.デフォルト100、最大500

 
## Example
***
> **GET** *https://moneyforward.com/api/v1/user_assets?account_ids[]=LlPqfqeeCZavwPBLmUy6xg==&asset_class_ids[]=3*

    {
      "limit": 100,
      "offset": 0,
      "total_count": 1,
      "user_assets": [
        {
          "user_asset": {
            "asset_class_id": 3,
            "asset_subclass_id": 12,
            "code": "",
            "cost": 0,
            "created_at": "2014-05-22T06:33:13+09:00",
            "currency": "JPY",
            "current_price": 389024.721519843,
            "entried_at": null,
            "entried_price": 300000,
            "jpyrate": 1,
            "name": "【デモ】マネフォファンド",
            "profit": 89024.72151984298,
            "qty": 1,
            "updated_at": "2014-05-22T06:33:13+09:00",
            "value": 389024.721519843,
            "hashed_id": "vpxDzM6STgFT4Br7pFTzVQ==",
            "hashed_account_id": "LlPqfqeeCZavwPBLmUy6xg==",
            "account": {
              "account_uid_hidden": "dem*",
              "created_at": "2014-04-19T17:33:37+09:00",
              "disp_name": null,
              "error_id": 5,
              "last_aggregated_at": "2014-05-22T06:33:13+09:00",
              "last_succeeded_at": "05/22 06:33",
              "memo": null,
              "message": null,
              "msg_flag": 0,
              "msg_time": null,
              "next_aggregate_at": "2014-05-25T02:27:08+09:00",
              "service_category_id": 1,
              "service_id": 1,
              "status": 2,
              "service": {
                "category_name": "銀行",
                "category_type": "BANK",
                "code": "0005",
                "description": "<li>口座番号ではなくオンラインバンキング用のログイン情報となります。オンラインバンキングの手続きは各金融機関へお問い合わせ下さい。</li><li>登録後、「IDとパスワードをお確かめ下さい」というメッセージが表示された場合、一度本サイトにログイン出来るかのご確認をお願いします。</li>",
                "id": 1,
                "login_url": "https://entry11.bk.mufg.jp/ibg/dfw/APLIN/loginib/login?_TRANID=AA000_001",
                "service_name": "三菱東京UFJ銀行",
                "service_type": "B_MUFG",
                "yomigana": "ミツビシトウキョウユーエフジェイギンコウ"
              }
            },
            "asset_class": {
              "asset_class_name": "投資信託",
              "asset_class_type": "MF",
              "disp_order": 4,
              "id": 3
            },
            "asset_subclass": {
              "asset_class_id": 3,
              "asset_subclass_name": "投資信託",
              "asset_subclass_type": "MUTUAL_FUND",
              "id": 12,
              "liquid": 85
            }
          }
        }
      ]
    }