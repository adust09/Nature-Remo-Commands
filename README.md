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

# コマンドファイルの中身を変更
取得したアクセストークンとAppliance IDを任意のコマンドファイルのなかにコピペしてください

# zshへの設定方法
①自作コマンドを配置するフォルダを作る<br>
```mkdir ~/mycommands```<br>
<br>
②フォルダまでのパスを通す<br>
```export PATH=$HOME/mycommands:$PATH```<br>
<br>
③.zshrcの変更を反映させる<br>
```source ~/.zshrc```<br>
<br>
④mycommands配下にコマンドファイルを配置する<br>
<br>

⑤コマンドファイルの権限を設定する<br>
```sudo chmod 755 ~/mycommands/<ファイル名>```<br>
<br>

# 呼び出し方法
zshでコマンド名(ファイル名)を打ち込めば動きます
<br>
エアコンをオフにした時はこんな感じ

<img width="601" alt="スクリーンショット 2021-06-19 14 23 17" src="https://user-images.githubusercontent.com/47593288/122631887-ff1e0380-d109-11eb-8c3a-adecf28763b9.png">

<br>
*引数に注意
