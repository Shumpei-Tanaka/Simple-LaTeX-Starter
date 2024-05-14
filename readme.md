<a name="readme-top"></a>

[![GitHub License][license-shield]][license-url]

[![Paypal][Paypal-shield]][Paypal-url][![BuyMeACoffee][BuyMeACoffee-sheild]][BuyMeACoffee-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">

  <h3 align="center">Simple-LaTeX-Starter</h3>

  <p align="center">
    シンプルに $\LaTeX$ をセットアップして文書を書こう
    <br />
  </p>
</div>

1. [Demo](#demo)
2. [Focus](#focus)
    1. [xymtex を使用するときの情報源](#xymtex-を使用するときの情報源)
3. [Installation](#installation)
    1. [TeX Live のインストールとコレクションのインストール](#tex-live-のインストールとコレクションのインストール)
        1. [TeX Live の基本環境のみのインストール](#tex-live-の基本環境のみのインストール)
        2. [TeX Live の拡張機能をインストール](#tex-live-の拡張機能をインストール)
    2. [vscode のインストールと設定](#vscode-のインストールと設定)
    3. [vscode のインストール](#vscode-のインストール)
    4. [vscode 拡張機能のインストール](#vscode-拡張機能のインストール)
4. [Usage](#usage)
    1. [このリポジトリをダウンロードする](#このリポジトリをダウンロードする)
        1. [A: zip としてダウンロード](#a-zip-としてダウンロード)
        2. [B: git clone する](#b-git-clone-する)
    2. [このリポジトリを開く](#このリポジトリを開く)
    3. [タイプセットをして pdf を作成する](#タイプセットをして-pdf-を作成する)
    4. [作成した pdf を画面を分けて表示](#作成した-pdf-を画面を分けて表示)
    5. [画像などのファイルを手軽に貼り付ける](#画像などのファイルを手軽に貼り付ける)
    6. [スニペットを使う](#スニペットを使う)
5. [License](#license)
6. [Appendix](#appendix)
    1. [Windowsのユーザー名が日本語文字を含む場合にインストール失敗することの回避方法](#windowsのユーザー名が日本語文字を含む場合にインストール失敗することの回避方法)
        1. [日本語文字を含まない新しいtempフォルダを作る](#日本語文字を含まない新しいtempフォルダを作る)
        2. [`TEMP`、`TMP`環境変数を設定しなおす](#temptmp環境変数を設定しなおす)
    2. [Sumatra PDF](#sumatra-pdf)

## Demo

サンプル(/srcs/simple-report)の.tex をタイプセットし、その結果を右側に表示しながら書き換えている様子を示す。

![alt text](readme.md_assets/image.png)

![alt text](readme.md_assets/image-1.png)

具体的な入力例を[/srcs/simple-report.tex](/srcs/simple-report.tex)、その出力例を[/examples/srcs/simple-report/simple-report.pdf](/examples/srcs/simple-report/simple-report.pdf)に示す。

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Focus

ここではセットアップと例示のみを取り扱う。
具体的な $\LaTeX$ の記載方法については[TeX Wiki](https://texwiki.texjp.org/)や Web 検索の結果を参照。

### xymtex を使用するときの情報源

化学構造を書く場合には

-   [@TeX-seminar XyMTeX 美構造式作成入門](https://qiita.com/TeX-seminar/items/c11f8b364d6391737b20#%E5%8E%9F%E5%AD%90%E3%83%AA%E3%82%B9%E3%83%88)

化学反応を書く場合には

-   [LaTeXで化学構造式 --- XyMTeX の紹介](http://web.archive.org/web/20090224162250/http://www.klavis.info/xym.html#react)

それでも不明なことがあれば[xymtex(catan)](https://ctan.org/pkg/xymtex)から xymtex.zip をダウンロードし、xymtex/doc/XyMTeX-manual.pdf を参照するとよい。

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Installation

### TeX Live のインストールとコレクションのインストール

フルスキームですべてインストールすることが望ましいが、7GB ほどの容量を必要とする。

ここでは科学実験レポートに向けた実践で必要な機能に絞りインストールする。ここで上げているものをインストールすると 3GB ほどとなる。

#### TeX Live の基本環境のみのインストール

TeX Live を最小構成でインストールする。これは $\LaTeX$ さえ付属しない、ほとんど $\LaTeX$ 用のインストーラのようなものとなる。

※ $\LaTeX$ は TeX を使いやすくしたものであり、TeX Live の最小構成では TeX のみが付属するため。

この手順では、インストール開始後、1 分程で完了する。インストール終了後、使用容量は 300MB ほどとなる。

> [!CAUTION]
> Windowsのユーザー名が日本語文字の場合、インストールが途中で止まったままになる。
> [付録:Windowsのユーザー名が日本語文字を含む場合にインストール失敗することの回避方法](#windowsのユーザー名が日本語文字を含む場合にインストール失敗することの回避方法)をこの手順の前に実行することで、途中で止まってしまう現象を回避する。

-   `install-tl.zip` をダウンロード
    -   [Installing TeX Live over the Internet - TeX Users Group](https://www.tug.org/texlive/acquire-netinstall.html)
    -   ![alt text](readme.md_assets/image-9.png)
-   `install-tl.zip`を`日本語文字を含まない場所`へ移動・解凍する
    -   `日本語文字を含まない場所`は例えば`C:\ws`など
    -   `ドキュメント`や`ダウンロード`自体は問題ないが、これは`ユーザーフォルダ`の下にある。
        -   `ユーザー名`が日本語文字を含む場合、`ユーザーフォルダ`が日本語文字になってしまうため、`ドキュメント`や`ダウンロード`は不可となる
-   `install-tl-windows.bat` を起動する
    -   ![alt text](readme.md_assets/image-8.png)
-   TeX Live インストーラが表示されたら、`特定のミラーを選択`から日本のどれかを選択する
    -   ![alt text](readme.md_assets/image-10.png)
    -   あまりにも時間がかかるようであればここを選択し直してみると解決するかもしれない。
-   インストーラが自動で次の画面に遷移する。
    -   ![alt text](readme.md_assets/image-11.png)
-   `高度な設定`ボタン → `スキーム`の行の`変更`ボタン →`minimal スキーム`を選び、OK を押す
    -   ![alt text](readme.md_assets/image-12.png)
    -
    -   ![alt text](readme.md_assets/20231211143338-latex--1.png)
    -
    -   ![alt text](readme.md_assets/20231211143338-latex--2.png)
-   正しく`minimal スキーム`を選択できていれば次のような表示になる。
    -   ![alt text](readme.md_assets/image-14.png)
-   この状態を確認した後、`インストール`ボタンの押しインストールを開始する
    -   ![alt text](readme.md_assets/image-15.png)
-   １分ほどで次のようなログで終了し、基本環境のインストールは完了となる
    -   ![alt text](readme.md_assets/image-13.png)

#### TeX Live の拡張機能をインストール

$\LaTeX$ で文書を作る際に必要となるであろう拡張機能をインストールしていく。

この手順では、インストール開始後 1 時間ほどで終了する。インストール終了後、使用容量は 4GB ほどとなる。

-   tex live manager を起動する
    -   ![alt text](readme.md_assets/20231211143338-latex--3.png)
-   必要なものを全てにチェックを入れ`選択項目をインストール`ボタンを押しインストールを開始する。
    -   コレクションとスキームに絞ると探しやすい
    -   ![alt text](readme.md_assets/image-16.png)
    -   必要なもの
        -   collection-bibtexextra
        -   collection-binextra
        -   collection-langjapanese
        -   collection-latex
        -   collection-latexextra
            -   float が付属している
                -   その位置に表示する
        -   collection-luatex
            -   メインで使うもの
        -   collection-mathscience
            -   化学系
                -   xymtex が付属している
                    -   化学構造図を描画できる
        -   collection-pictures
        -   collection-pstrics
            -   xymtexps を使用してよりきれいな化学構造図を作るのに必要
    -   `選択項目をインストール`を押すとインストールが始まり、次のようなログが出始める
        -   ![alt text](readme.md_assets/image-29.png)
-   次のような表示で終了すればインストールが正しく完了となる
    -   ![alt text](readme.md_assets/image-28.png)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### vscode のインストールと設定

$\LaTeX$ そのものはテキストファイルで記述するため、編集に用いるツールはメモ帳でも何でもよい。

しかし、保存時にタイプセットを行ったり出力 pdf を随時確認するには何かしらのエディタを扱うと便利である。

ここでは vscode の設定を用意したため、vscode とその拡張機能をインストールし、快適に $\LaTeX$ を記述・タイプセットするための設定を行う。

また、vscode は ssh や wsl のリモート接続に対応しており、より高速な $\LaTeX$ タイプセットを求めて linux に移行した際にもそのまま扱うことができる。

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### vscode のインストール

-   公式サイトよりダウンロード・インストールを行う
    -   [https://code.visualstudio.com/](https://code.visualstudio.com/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### vscode 拡張機能のインストール

-   画面左下部分から次図のように拡張機能管理画面を開く
    -   ![alt text](readme.md_assets/image-2.png)
-   LaTeX Workshop を検索しインストールする
    -   ![alt text](readme.md_assets/image-3.png)
-   Paste Image (mushan 作)を検索しインストールする
    -   ![alt text](readme.md_assets/image-4.png)

ここまで導入を行った後、ショートカットキーが被っているためそれを修正する。

-   画面左下部分からショートカット設定画面を開く
    -   ![alt text](readme.md_assets/image-6.png)
-   「latex view」で検索する
    -   ![alt text](readme.md_assets/image-7.png)
-   デフォルトでは Ctrl+Alt+V になっている
    -   画像を貼り付ける PasteImage もこのキーになっている
-   この行をダブルクリックし、キーバインドを設定する
    -   おすすめは Ctrl+K→V
        -   vscode の拡張機能ではこのショートカットをプレビューに割り当てることがままある
    -   Ctrl ＋ K を押した後に Ctrl を離し、V を押す

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

### このリポジトリをダウンロードする

[A](#a-zipとしてダウンロード)、[B](#b-git-cloneする)のどちらかの方法でこのリポジトリをダウンロードする。

#### A: zip としてダウンロード

-   次のリンクから zip としてダウンロード・展開をする。

    -   [https://github.com/Shumpei-Tanaka/Simple-LaTeX-Starter/archive/refs/heads/main.zip](https://github.com/Shumpei-Tanaka/Simple-LaTeX-Starter/archive/refs/heads/main.zip)

#### B: git clone する

-   git でこのリポジトリをクローンする

### このリポジトリを開く

-   ダウンロードしたこのリポジトリ内にある[`Simple-LaTeX-Starter.code-workspace`](/Simple-LaTeX-Starter.code-workspace)を vscode で開く

-   ファイルツリーが図のようになる
    -   ![alt text](readme.md_assets/image-5.png)
-   .vscode/setting.json に $\LaTeX$ を扱う設定が記載されている
    -   これは`Simple-LaTeX-Starter.code-workspace`を vscode で開くことで自動で反映される
-   srcs/simple-report.tex をそのまま vscode 上で開く

### タイプセットをして pdf を作成する

-   Ctrl+Alt+B を押す
    -   buildtex/に出力結果が現れる

### 作成した pdf を画面を分けて表示

-   Ctrl+K→V と押す
    -   出力された pdf を画面右半分に開くことができる

### 画像などのファイルを手軽に貼り付ける

-   画像ファイルをコピーした状態にする
-   srcs/simple-report.tex のどこかの行を編集状態にする
-   Ctrl+Alt+V を押す
-   画像が自動で srcs/simple-report.tex_assets/にコピーされる
-   その保存した場所へのパスが srcs/simple-report.tex に入力される

### スニペットを使う

vscode にはよく使う定型文をすばやく書くためのスニペットと呼ばれる機能がある。

$\LaTeX$ における画像の貼り付け、表の作成、段落間の空行、プログラムコードの貼付けに使えるスニペットをサンプルとして用意したため、これを紹介する。

スニペットの定義は[/.vscode/latex.code-snippets](/.vscode/latex.code-snippets)にある。

具体的な使用方法は以下の通り

-   srcs/simple-report.tex のどこかの行を編集状態にする
-   次の表の命令のどれかを打ち込むと自動補完され、矢印キーで選択し Enter を押すとスニペットが展開される。

| 命令文   | 機能                                       |
| -------- | ------------------------------------------ |
| sfigure  | 画像を貼り付ける場所を用意する             |
| stable   | 表の雛形を作成                             |
| smargine | 段落間などに空行を挿入                     |
| scode    | プログラムコードを貼り付ける場所を用意する |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->

## License

The source code is licensed MIT. See [LICENSE.md][license-url].

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Appendix

### Windowsのユーザー名が日本語文字を含む場合にインストール失敗することの回避方法

#### 日本語文字を含まない新しいtempフォルダを作る

-   `C:\ws\temp`となるようにフォルダを作る
    -   フォルダは通常通り右クリックから`新規作成`で作成する
        -   ![alt text](readme.md_assets/image-20.png)
    -   `C:\ws\temp`を開き表示が次のようになっていれば正しい
        -   ![alt text](readme.md_assets/image-19.png)

#### `TEMP`、`TMP`環境変数を設定しなおす

-   `環境変数を編集`を開く。方法はいくつかある

    -   A: `Windowsキー`を押し、`環境変数を編集`を検索して開く
        -   ![](readme.md_assets/image-17.png)
    -   B: `コントロールパネル`から検索して開く
        -   `コントロールパネル`を開く
            -   ![alt text](readme.md_assets/image-22.png)
        -   右上の検索欄に`環境変数`と検索し、`環境変数を編集`を開く
            -   ![alt text](readme.md_assets/image-21.png)

-   上の`ユーザー環境変数`の中から`TEMP`を選択し、`編集`ボタンを押す
    -   ![alt text](readme.md_assets/image-18.png)
-   `ディレクトリを参照`ボタンを押し、[日本語文字を含まない新しいtempフォルダを作る](#日本語文字を含まない新しいtempフォルダを作る)で作成した`C:\ws\temp`のフォルダを指定する
    -   ![alt text](readme.md_assets/image-23.png)
    -   ![alt text](readme.md_assets/image-24.png)
-   正しく指定できると次の図のように`C:\ws\temp`が`変数値`欄に記載される。この状態で`OK`を押す
    -   ![alt text](readme.md_assets/image-25.png)
-   正しく設定できると次の図のように`TEMP`の行の`値`列が`C:\ws\temp`に書き換わる
    -   ![alt text](readme.md_assets/image-26.png)
-   同じ手順で`TMP`も書き換え、`TEMP`、`TMP`両方が`C:\ws\temp`になっていることを確認して`OK`を押す
    -   ![alt text](readme.md_assets/image-27.png)
-   これで途中終了を回避するための設定は完了となる

### Sumatra PDF

PDFをPCで見るにはSumatra PDFがおすすめ

-   [Sumatra PDF official](https://www.sumatrapdfreader.org/free-pdf-reader)
-   [Sumatra PDF official Download](https://www.sumatrapdfreader.org/download-free-pdf-viewer)

-   利点
    -   余計な購入促しがない
    -   画面が広くとれ、PDFを読みやすい
    -   日本語に対応している
    -   PDFのパスワードを保存でき、いちいち再入力が必要ない

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[license-shield]: https://img.shields.io/github/license/Shumpei-Tanaka/Simple-LaTeX-Starter?flat-square
[license-url]: /LICENSE.md
[Paypal-shield]: https://img.shields.io/badge/paypal.me-s6tanaka-white?style=flat-squere&logo=paypal
[Paypal-url]: https://paypal.me/s6tanaka
[BuyMeACoffee-sheild]: https://img.shields.io/badge/buy_me_a_coffee-s6tanaka-white?style=flat-squere&logo=buymeacoffee&logocolor=#FFDD00
[BuyMeACoffee-url]: https://www.buymeacoffee.com/s6tanaka
