# Pythonライブラリ紹介  

この記事ではPythonのライブラリを紹介します。  

さまざまな記事や資料の中で、ライブラリ（Library）、パッケージ（Package）、モジュール（Module）など、似た概念の言葉が現れます。  
モジュールは `.py` ファイルであり、再利用可能なクラス（Class）や関数（Function）が内蔵されているもの、パッケージはいくつかのモジュールが集まったもの、ライブラリはいくつかのパッケージが集まったものとなります。  

![picture](./pictures/Python_lib_pkg_mdl.png)

これらを利用する際に、それぞれの違いを意識する必要はほとんどないと思います。本記事でも厳密な定義通りの呼称が用いられていない部分がありますが、ライブラリ、モジュール、パッケージに関しては基本的に「同じもの」という認識で差し支えありません。  

## ユーティリティ  

### os, sys  

ファイルやフォルダ（ディレクトリ）のパスの取得や操作をしたり、一時的に環境変数を操作したりできます。  

WEBページ  

- [os --- 雑多なオペレーティングシステムインタフェース](https://docs.python.org/ja/3/library/os.html)  
- [sys --- システムパラメータと関数 — Python 3.8.2rc2 ドキュメント](https://docs.python.org/ja/3/library/sys.html?highlight=sys%20version)  

練習用資料  

- [os と sys モジュールの使い方](./osとsysモジュールの使い方.ipynb)  

---

### pathlib  

このモジュールはファイルシステムのパスを表すクラスを提供しています。  

- ファイルパスの操作  
- ファイルやフォルダのリネームや移動、作成や削除  
- ファイルやフォルダ一覧の取得  

などを容易に行うことができます。  

WEBページ  

- [pathlib --- オブジェクト指向のファイルシステムパス](https://docs.python.org/ja/3/library/pathlib.html)  

練習用資料  

- [pathlib モジュールの使い方](./pathlibモジュールの使い方.ipynb)

---

### datetime  

このモジュールは日付や時刻を操作するためのクラスを提供しています。  

WEBページ  

- [datetime --- 基本的な日付型および時間型](https://docs.python.org/ja/3/library/datetime.html)  

練習用資料  

- [datetime モジュールの使い方](./datetimeの使い方.ipynb)  

## 科学計算、データ分析  

### NumPy  

NunPyは多次元配列の操作を行うためのライブラリです。  

WEBページ  

- [NumPy](https://numpy.org/)  

<練習用資料  

- [NumPy 練習](./NumPy練習.ipynb)  

---

### pandas  

pandasは表形式のデータの操作、可視化を得意とするライブラリです。  

WEBページ  

- [pandas - Python Data Analysis Library](https://pandas.pydata.org/)  

練習用資料  

- [pandas 練習](./pandas練習.ipynb)  

---

### matplotlib  

matplotlibはPythonおよびその科学計算用ライブラリNumPyのためのグラフ描画ライブラリです。  

WEBページ  

- [Matplotlib: Python plotting](https://matplotlib.org/index.html)  

練習用資料  

- [matplotlib 練習](./matplotlib練習.ipynb)  

---

### seaborn  

Seabornは、Pythonで統計分析のための図を作成するためのライブラリです。 matplotlibのラッパーとして機能し、pandasのデータ構造と密接に統合されています。  

WEBページ  
[seaborn: statistical data visualization](https://seaborn.pydata.org/index.html)

練習用資料  

- [seaborn - Plotting with categorical data](./seaborn_Categorical_Tutorial.ipynb)  
- [<作成中> seaborn - Visualizing statistical relationships](./seaborn_Relational_Tutorial.ipynb)  
- [<作成中> seaborn - Visualizing the distribution of a dataset](./seaborn_Distribution_Tutorial.ipynb)  
- 今後も追加予定  

## 仕事効率化  

### xlwings  

xlwingsはVBAライクにExcelを扱うことができるライブラリです。  

WEBページ  

- [xlwings - xlwings is an open-source Python library that makes it easy to automate Excel with Python. It works great for reporting, unit tests and user defined functions (UDFs).](https://www.xlwings.org/)  

練習用資料  

- [xlwings 練習](./xlwings練習.ipynb)  

---

### openpyxl  

WEBページ  

- [openpyxl - A Python library to read/write Excel 2010 xlsx/xlsm files](https://openpyxl.readthedocs.io/en/stable/)  

<今後追記予定>  

---

### selenium  

WEBページ  

- [Selenium with Python](https://selenium-python.readthedocs.io/)  

<今後追記予定>  
