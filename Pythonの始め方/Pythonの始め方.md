# Pythonのはじめかた  

この記事ではPythonを手っ取り早く使ってみる方法や、ローカルPCへインストールする方法を紹介しています。  

## Pythonとは  

Pythonは、比較的学習しやすくさまざまな用途に利用可能なオープンソースライセンスで提供されているプログラミング言語です。  

[Welcome to Python.org（公式)](https://www.python.org/)  
[Top - python.jp（日本の Python コミュニティ)](https://www.python.jp/)  
[Python - Wikipedia](https://ja.wikipedia.org/wiki/Python)  

> 文法を極力単純化してコードの可読性を高め、読みやすく、また書きやすくしてプログラマの作業性とコードの信頼性を高めることを重視してデザインされた、汎用の高水準言語である。  
> 核となる本体部分は必要最小限に抑えられている。一方で標準ライブラリやサードパーティ製のライブラリ、関数など、さまざまな領域に特化した豊富で大規模なツール群が用意され、インターネット上から無料で入手でき、自らの使用目的に応じて機能を拡張していくことができる。（Wikipediaより引用）  

## WEBを利用して手っ取り早くPythonを使う  

インターネットを利用できるPC環境（スマホは厳しい）であれば、WEB上のさまざまな無料サービスを利用してすぐにPythonに触れることができます。  

### Google Colaboratoryを利用する  

[Colaboratory へようこそ - Colaboratory](https://colab.research.google.com)  

> Colaboratory（以下Colab）は、Googleが提供する、完全にクラウドで実行されるJupyter Notebook環境であり、無料で利用することができる。  

特徴  

- インターネット接続に加えて、Googleアカウントがあればいつでも始めることができる。  
- 自分のGoogleドライブにNotebookやデータを保存できる。  
- 自分のGoogleドライブのNotebookやデータを利用できる。  
- GPUや専用のプロセッサも無料で利用できる。  
- いくつかの練習用データセットがデフォルトで利用可能。  
- その他、本来のJupyter Notebookにはない機能が多数存在する。  

注意点  

- **Googleアカウントが必要。**  
- Jupyter Notebookとは若干操作方法が異なる。  
- 連続利用可能な時間に制限があり、Notebookを開いて最大12時間まで。ただし90分間何らかの操作が無ければ切断されてしまう。  
※ Try Jupyterよりも制限時間は長く、作成したファイルはGoogleドライブに保存されるため消失してしまうことはない。  

### Try Jupyterを利用する  

[Project Jupyter | Try Jupyter](https://jupyter.org/try)  

> Try JupyterはProject Jupyterが提供しているサービスである。  
このサービスは下記のような特徴を持っており、Pythonコードを簡単かつ迅速に試したり、練習したりすることに向いている。ただし、作成したファイルを保存したのち、後日作業を再開するためには、ファイルのダウンロード＆アップロードが必要である点に注意しなければならない。  

特徴  

- インターネット接続さえ可能ならば、PythonやJupyter Notebookをインストールしたりする手間なしに無料で簡単に始めることができる。  
- アカウント登録などは一切不要。  
- ローカルPCにインストールしたJupyter Notebookと画面や操作方法が同じ。  

注意点  

- 同時利用者が多いとサービスを利用できない場合がある。  
- 作成したファイルの保存が面倒。(ダウンロードしてローカルPCなどに保存）
- しばらく（数十分？）放置しているとサーバが終了してしまい、作成したファイルはすべて失われる。そのため保存したいデータはまめにダウンロードしなければならない。  
- 以前の作業を再開するにはダウンロードしたファイルをアップロードしなければならない。  

### プログラミング教育サービスを利用する  

[Progate | プログラミングの入門なら基礎から学べるProgate[プロゲート]](https://prog-8.com/)  
[SoloLearn: Learn to Code for Free!](https://www.sololearn.com/)  

## 自分のパソコンでPythonを使う  

### Anaconda Distributionを利用する  

Anacondaを使えばPythonに加えて、データ分析に利用されるさまざまなパッケージを同時にインストールできます。例として、  

- Beautiful Soup → HTMLの解析  
- Jupyter Notebook/JupyterLab → Pythonによる対話的なデータ分析実行環境  
- NumPy → 高速な配列、行列操作  
- Pandas → 表形式データの操作  
- Matplotlib/seaborn → 図によるデータの可視化  
- scikit-learn → 統計的なデータ分析  
- Sphinx → ドキュメント作成  
- pywin32 → Windows（Win32 API）の操作  
- xlwings/openpyexl → Excelの操作  

などがすぐに利用できます。  
また、下記のパッケージなども追加でダウンロードできます。  

- TensorFlow → Deep Learningフレームワーク（Google製）  
- PyTorch → Deep Learningフレームワーク（Facebook製）  
- Selenium → WEBブラウザの操作  

さらに、`conda` コマンドで仮想環境やパッケージの管理もできます。  
Pythonを対象とした書籍でも、多くの場合Anacondaを利用して環境構築を行っているため、Python初学者に対してはAnacondaを利用することをオススメします。  

Anacondaのインストーラのダウンロードはここから  
[Anaconda Python/R Distribution - Free Download](https://www.anaconda.com/distribution/)  

Miniconda（必要最小限のパッケージのみ）のダウンロードはここから  
[Miniconda — Conda documentation](https://docs.conda.io/en/latest/miniconda.html)  

Anacondaのインストール先についてはデフォルトのままでも良いのですが、今後インストールするパッケージによっては、Windowsの最長パス制限を超過することによる不具合が生じる可能性があるため、あまり深すぎない場所にインストールしたほうがいいかも。(`C:\Users\[USERPROFILE]\Anaconda3` などを推奨）  

インストールが完了したら、スタートメニューから、  
![スタートメニュー](./pictures/Anacondaインストール後のスタートメニュー.png)  
上記のように追加されていることが確認できる。  

### 公式からPythonをダウンロードする  

Python Software Foundation（PSF）からPythonのダウンロードはここから  
[Download Python | Python.org](https://www.python.org/downloads/)  

この方法の場合、`pip` コマンドでPyPI（The Python Package Index）からパッケージをダウンロードし、venvやpipenvなどの仮想環境管理ツールと組み合わせて利用することになる。  
