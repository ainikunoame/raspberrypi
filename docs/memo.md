## pythonライブラリ導入時のapt, pipの違いについて

### インストール先のパス

|入れ方  |sudo apt install  |sudo pip install  |pip install  |
| - | - | - | - |
|インストール先パス  |/usr/lib/python3/dist-packages  |/usr/local/lib/python3.6/dist-packages  |/home/hoge/.local/lib/python3.6/site-packages/  |
|利用  |rootが全ユーザに適用したい場合  |rootが全ユーザに適用したい場合  |一般ユーザが自分の身を対象に使う場合  |

### 優先順位
同じライブラリが入っている場合、パスの順序の優先度が高いものが利用されます。
```
import sys
print(sys.path)
```
```
# 出力
['', '/usr/lib/python36.zip', '/usr/lib/python3.6', '/usr/lib/python3.6/lib-dynload', 
'/home/hoge/.local/lib/python3.6/site-packages', '/usr/local/lib/python3.6/dist-packages',
 '/usr/lib/python3/dist-packages']
```
優先度的にはpip install > sudo pip install > sudo apt install

### 導入順序による導入可否
#### sudo apt install → sudo pip install
入らない。

`Requirement already satisfied: numpy in /usr/lib/python3/dist-packages`

既に入っている旨のメッセージ。

#### sudo pip install → sudo apt install
入る。だが`sudo pip install`が優先。

#### sudo apt install → pip install, sudo pip install → pip install
入る。使う時は`pip install`が最優先。
