# PipenvによるWindows PCでのPython仮想環境管理  

作成日: 2020/12/26  

## Pythonをインストールする  

Python Software Foundation（PSF）からPythonのダウンロードはここから。  
[Download Python | Python.org](https://www.python.org/downloads/)  

後々さまざまな仮想環境を作成することになりますが、それらで使うバージョン違いのPythonは仮想環境を作成しようとする時点でPCにインストールされている必要があります。
すでに使いたいバージョンが複数あることが判明していればインストールしておいてください。

※別にpyenvというパッケージをインストールしておくことで、必要なバージョンのPythonがインストールされていない場合自動的にダウンロードしてくれる模様（未検証）。

インストーラ起動時のふたつのチェックボックスについては、

- `Install launcher for all users (recommended)`  
  チェック推奨。プロンプトで `py` コマンドを使ってPCにインストールされている任意のバージョンのPythonを起動することができるようになる。  
-  `Add Python x.x to PATH`  
  チェックすると上記の `py` コマンドを使わなくてもPythonを起動できるようになるため、以下の説明中の `py -m ` 部分は不要になる。  
  ただし、複数バージョンのPythonをPCにインストールする場合はチェックを外した方が無難か。  

となります。  

また、インストール完了時の `Disable path length limit` というオプションはWidowsのパス長制限を無効化してくれるため、差し支えなければクリックしてください。  

## 環境変数を追加する  

|変数名                 |                   値|
|-                     |-                    |
|PIPENV_VENV_IN_PROJECT|true                 |
|HTTP_PROXY            |（プロキシ情報:ポート）|
|HTTPS_PROXY           |（プロキシ情報:ポート）|

## Pipenvをインストールする  

Pipenvドキュメント  
- [pypa/pipenv: Python Development Workflow for Humans.](https://github.com/pypa/pipenv)  
- [Pipenv: Python Dev Workflow for Humans — pipenv 2020.11.16.dev0 documentation](https://pipenv.pypa.io/en/latest/)

```Powershell
py -m pip install pipenv
```  
---  

## 仮想環境を作成する  

### ディレクトリ（フォルダ）を作成し、移動する  

エクスプローラーなどでこれから作業するためのフォルダを作成して、そこでPowerShellやコマンドプロンプトなどのシェルを起動するか、シェルから、

```PowerShell  
mkdir ProjectDirectory
cd ProjectDirectory
```  

と実行して `ProjectDirectory` に移動します。

### 仮想環境にPythonをインストールする  

```PowerShell  
py -m pipenv --python x.x
```  

Pythonのバージョン `x.x` を指定しない場合、PCにインストールされているPythonの最新バージョン（`py` コマンドで呼ばれるもの）が仮想環境にインストールされます。  

これを実行すると、`ProjectDirectory` フォルダに、`.venv` フォルダと `Pipfile` というファイルが作成されます。  

### 仮想環境に必要なパッケージをインストールする  

```PowerShell  
py -m pipenv install package_1 package_2 ...
py -m pipenv install package_3=VersionNo ...
py -m pipenv install package_4==FullVersionNo ...
py -m pipenv install --dev dev_only_package ...
```  

2行目のように `package=x` とバージョンNo.を指定するとメジャーバージョン `x` の中で適したバージョンをインストールします。  
3行目のように `package==x.x.x` とバージョンNo.を正確に指定することも可能です。  
4行目のように `--dev` オプションに続けて、開発時のみ利用するコードの自動整形用パッケージなどをインストールすると、`Pipfile` や `pipfile.lock` を使って環境を再現する際にそれらを含めないようにできます。  

上記を実行すると、`ProjectDirectory` フォルダの、`.venv` フォルダにインストールされたパッケージのファイルが保存されます。また、`Pipfile` にインストールされたパッケージの一覧が記録されます。さらに、`Pipfile.lock` というパッケージと実際にインストールされたバージョンの一覧が記録されたファイルが新たに作成されます。    

## 仮想環境にインストールしたパッケージを管理する    

### インストール済みのパッケージを表示する  

```PowerShell  
py -m pipenv graph
```  

### インストール済みのパッケージの依存関係に脆弱性がないかチェックする  

```PowerShell  
py -m pipenv check
```  

### インストール済みのパッケージのなかにアップデートできるものがないかチェックする  

```PowerShell  
py -m pipenv update --outdated
```  

### 古いパッケージをアップデートする  

```PowerShell  
py -m pipenv update
```  

※パッケージ更新後、`Pipfile.lock` が更新される。  

### パッケージをアンインストールする  

```PowerShell  
py -m pipenv uninstall package_name
```  

### `Pipfile.lock` に記載のないパッケージをアンインストールする  

```PowerShell  
py -m pipenv clean
```  


## 仮想環境を有効化/無効化する  

`pipenv shell` コマンドで、仮想環境が有効化されたシェルを起動します。  

```PowerShell  
py -m pipenv shell
```  

仮想環境下のシェルでは下記のように `pip list` コマンドでインストール済みのパッケージとバージョンの一覧を確認したり、`python some_script.py` のようにPythonスクリプトファイルを実行したりできます。  

```pipenv  
pip list

Package             Version
------------------- -------
package_1           x.x.x
package_2           x.x.x
...
```  

仮想環境の無効化しシェルを終了するには、  

```pipenv  
exit
```  

と実行します。

また、`pipenv shell` によって新たなシェルを起動せずに、`pipenv run` コマンドから、

```PowerShell  
py -m pipenv run pip list
py -m pipenv run python some_script.py
py -m pipenv run jupyter lab
```

のように直接元のシェルから各コマンドを実行することも可能です。  
2行目、3行目の部分をバッチファイルにすると、Pythonスクリプトの実行やJupyterなどの起動が簡単にできます。  


## 仮想環境の再現    

`Pipfile` および、`Pipfile.lock` を他のフォルダや他のPCにコピーして、容易に仮想環境を再現することが可能です。  

### `Pipfile` を元にパッケージをインストールする  

元の環境と同じパッケージがインストールされますが、バージョンは異なる場合があります。  

```PowerShell  
py -m pipenv install
```  

### `Pipfile.lock` を元にパッケージをインストールする  

元の環境と同じバージョンのパッケージがインストールされます。  

```PowerShell  
py -m pipenv sync
```  

## 仮想環境の削除  

エクスプローラーなどから仮想環境を作成したフォルダ内の `.venv` フォルダを削除するか、

```PowerShell  
py -m pipenv --rm
```  

と実行することで仮想環境を削除することができます。  
（上記コマンドでは `Pipfile` および、`Pipfile.lock` は削除されない）  
