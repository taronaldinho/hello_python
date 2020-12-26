# JupyterLabの始め方（with Pipenv）  

## Node.jsのインストール  

最新版を入れとけばOK

## デフォルトのブラウザをChromeまたはFireFoxに  

## フォルダ構成  

```
jupyter
   ├──lab             (←ここにJupyterLabの仮想環境を作る/JupyterLabの起動はここから)
   │   ├─project_1
   │   ├─project_2
   │    …
   └──kernels
       ├─kernel_1     (←ここにJupyterLabのカーネルとして利用する仮想環境を作る)
       ├─kernel_2     (同上)
        …
```  

## JupyterLabを起動する環境の作成

```PowerShell  
cd jupyter\lab
py -m pipenv --python x.x
py -m pipenv install jupyterlab
```

[krassowski/jupyterlab-lsp: Language Server Protocol integration for JupyterLab](https://github.com/krassowski/jupyterlab-lsp)

```PowerShell  
py -m pipenv install jupyter-lsp
```

```PowerShell  
py -m pipenv run jupyter labextension install @krassowski/jupyterlab-lsp
```

```PowerShell  
py -m pipenv install python-language-server[all]
```

```PowerShell  
py -m pipenv run jupyter lab
```

JupyterLabが起動したら拡張機能を `Enable` にする。  

JupyterLabの終了は、File→Logout→タブを閉じたのち、シェル側で `Ctrl+C` を行ってサーバをシャットダウンする。  

---

## カーネルとして利用する仮想環境の作成  

`ipykernel` は必須。あとはお好みで。

```PowerShell  
cd jupyter\kernels\kernel_1
py -m pipenv --python x.x
py -m pipenv install ipykernel numpy pandas ...
```

```PowerShell  
py -m pipenv run ipython kernel install --user --name=kernel_name --display-name=display_name
```

このあと、JupyterLab起動環境からJupyterLabを起動すればカーネルとして選択できるようになっている。  