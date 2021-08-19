# 執筆について
## SATySFi環境構築
- Windowsユーザー  
WSL 2を使いましょう、導入は[こちら](https://qiita.com/whim0321/items/ed76b490daaec152dc69)  
```
> wsl --set-default-version 2
```
で __必ずバージョンを2にしてください__。

- Mac, Linuxユーザー、およびWSLを導入したWindowsユーザー  
[こちらの記事](https://qiita.com/na4zagin3/items/a6e025c17ef991a4c923)にしたがってsatyrographosを導入してSATySFiをインストールしてください。

## ライブラリ導入
[使用ライブラリ](../README.md#使用ライブラリ)をsatyrographosでインストールします。インストール方法は各レポジトリを参照しましょう。

## フォント導入
各段階で、既に対象のディレクトリ・ファイルが存在する場合はその操作は必要ありません。  
以下、UNIX環境を仮定してコマンドを記述します (Windowsではcmdに `wsl` と入力することでUNIX環境になります)
1. `~/.satysfi` ディレクトリ内に `local` ディレクトリを生成し、その下に `hash`, `fonts` の2つのディレクトリを生成します。  
```
$ mkdir -p ~/.satysfi/local/hash & mkdir -p ~/.satysfi/local/fonts
```
2. `~/.satysfi/local/fonts` 内にフォントファイル `cirlxarli_liparxe.ttf` と `segoeui.ttf` を配置 (リパーシェフォントはダウンロードしておいてください。)  
3. `~/.satysfi/local/hash` 内に `fonts.satysfi-hash` ファイルを作成し、以下を書き込み  
```
{
    "cirlipa":<"Single":{"src":"local/fonts/Cirlxarli_liparxe.ttf"}>,
    "segoeui":<"Single":{"src":"local/fonts/segoeui.ttf"}>
}
``` 
4. 3.ですでに `fonts.satysfi-hash` が存在する場合は以下を`}`の前に書き込む  
```
"cirlipa":<"Single":{"src":"local/fonts/Cirlxarli_liparxe.ttf"}>,
"segoeui":<"Single":{"src":"local/fonts/segoeui.ttf"}>
```

## テストコンパイル
UNIX環境では `satysfi [ファイルパス]` でコンパイルが出来ます。実行して
```
output written on 'LLLIL.pdf'.
```
が表示されれば成功です。