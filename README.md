# Nature-Remo-Commands
Nature Remoをシェルスクリプトで動かすためのファイルを置いています.<br>
各自のアクセストークンやApplience IDを取得した上で、書き換えてください.

# アクセストークンの取得
こちらのページから取得できます.家電を勝手にイジられるので他人に見られないようにしてください.
https://home.nature.global/home


# Applience IDの取得
こちらのコマンドであなたの家に登録されているNature Remoの家電一覧が取得できます.

```curl -X GET "https://api.nature.global/1/appliances" -H "authorization: Bearer <Access Token>"```
<br>そのなかで、操作したい家電のAppliance IDを取得してください.
```
[
    {
        "id": <Appliance ID>,
        "device": { ... },
        "model": { ... },
        "type": "LIGHT",
        "nickname": "エアコン",
        "image": "ico_light",
        "settings": null,
        "aircon": null,
        "signals": [ ... ],
        "light": {
            "buttons": [
                {
                    "name": "on",
                    "image": "ico_on",
                    "label": "Light_on"
                },
                {
                    "name": "off",
                    "image": "ico_off",
                    "label": "Light_off"
                },
                { ... }
            ],
            "state": { ... }
        }
    }
]
```
*このIDを間違えると404エラーになるので注意

# ファイルの中身を変更
取得したアクセストークンとAppliance IDを任意のコマンドファイルのなかにコピペしてください

