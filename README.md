# 第２回エレクトロニクスシミュレーション研究会ソフトウェアコンテスト

- [サンプルコード]()
- [解説記事](https://github.com/h403/EST2018/wiki/コンテスト-Wiki)
- [質問箱](https://github.com/h403/EST2018/issues)

## 開催概要

昨年度に引き続き、エレクトロニクスシミュレーション研究会では、プログラミングコンテストを開催いたします。本年度は、機械学習やＡＩへの関心の高まりを受けて、広帯域インピーダンス変成器の最適化設計をテーマとして設定します。コンテストでは、審査委員会が、参加チームの開発した設計プログラムを審査し、最も優秀なプログラムを開発したチームおよびそのリーダーを表彰します。応募者による課題提出終了後、審査会（日程・場所：未定）を開催し、表彰するチームとリーダを決定します。審査会には各チームから一人以上参加しなければいけません。審査会
は以下のような内容で構成されます。チームと開発プログラムを紹介するショートプレゼンテーション、開発したプログラムを使ったデモンストレーション、開発したプログラムの公開審査、表彰式。

本コンテストでは、若手研究者・学生が参加しやすいように、プログラミングのサポートを行います。１つは、コンテストで無制限に利用して良いサンプルプログラムを提供します。参加者は、提供されたサンプルプログラムを改造して、独自のアルゴリズムを実装することもできますし、そのまま用いてパラメータ調整や初期値の設定方法に注力することもできます。１つは、コンテストの開発に役立つドキュメント類と質問箱を提供します。質問箱は、参加者からの問い合わせに対して担当者が答える、ウェブ掲示板です。参加者同士の公平性を担保するために、全てのやりとりは他の参加者へも共有されます。

これらのサービスを効率的に運用するために、本年度は、使用言語と開発環境を主催者が指定します。使用言語はPython3、開発環境はGoogle Colaboratoryです。Python は、2017年度アメリカで最も稼げる言語第2位に選出された言語で、機械学習や人工知能開発では事実上の標準言語の地位を獲得していますし、海外では科学計算分野でもその有用性が知られており、各分野で注目されている言語です。開発環境はGoogle Colaboratoryを用います。Googleが無料で提供しているPython開発環境で、ウェブブラウザを使ってPythonプログラムを作成、実行、共有することができます。これによって、参加者は煩雑なPython環境のインストールを回避できます。また、実行環境も統一することができ、公平にコンテストを運営できます。

## 開発課題

**多段の理想伝送線路による広帯域整合回路の設計プログラムの開発**

特性インピーダンス <img src="https://latex.codecogs.com/gif.latex?W_i=Z_i/Z_0" />、中心周波数における電気長 <img src="https://latex.codecogs.com/gif.latex?\theta_i=\beta l_i" /> の理想伝送線路を多段接続することによって、負荷抵抗 <img src="https://latex.codecogs.com/gif.latex?R_L" /> と特性インピーダンス <img src="https://latex.codecogs.com/gif.latex?Z_0" /> の給電線路とを広帯域整合する回路を設計するプログラムを作成せよ。プログラムへの入力は、入出力の変成比、線路接続段数、許容反射損失、要求帯域幅のいずれか、あるいは全部を与えるものとする。出力は、各段の伝送線路の特性インピーダンス <img src="https://latex.codecogs.com/gif.latex?W_i" /> と中心周波数における電気長 <img src="https://latex.codecogs.com/gif.latex?\theta_i" /> を算出するものとする。

また、開発したプログラムを用いて以下の４つの仕様の変成器を設計せよ。

- 仕様１：編成比 2 、帯域内許容反射損失 -20 dB以下、整合帯域幅 2.6 以上、段数 段以下（調整中）
- 仕様２：（調整中）
- 仕様３：（調整中）
- 仕様４（審査会にてデモンストレーション）：審査会場にて指示

参加者は上記プログラムを開発し別途指定する期限内に開発プログラムと共に仕様１〜３の設計データ（<img src="https://latex.codecogs.com/gif.latex?W_i" />、<img src="https://latex.codecogs.com/gif.latex?\theta_i" />）を提出しなければならない。仕様４については、審査会会場にて指示する。指示してから１５分以内に設計完了して提出しなければならない。

## 審査基準
開発したプログラムは以下の審査基準に従って総合的に評価される。
### 設計スコア
後述する基準帯域 RBW の達成度 BW / RBW x 100 [points] を設計スコアとする。ただし、設計仕様が満たされていない場合には、無条件でその仕様の設計スコアは 0 となる。仕様１〜４の設計スコアの合計が審査チームの設計スコア得点となる。基準帯域は段数によって異なり、多段になるほど広帯域となるので、高得点を得るためにはできるだけ少ない段数で仕様を満足する設計を見つける必要がある。

#### 基準帯域の計算式
目標バンド幅 <img src="https://latex.codecogs.com/gif.latex?B = f_H / f_L" /> への達成率で評価する

<img src="https://latex.codecogs.com/gif.latex?B=\pi/\theta_m - 1" />

<img src="https://latex.codecogs.com/gif.latex?\left|T_N\left(\frac{1}{\cos\theta_m}\right)\right|^{-2}=4\frac{R}{(R-1)^2}\frac{\Gamma_{\textrm{max}}^2}{(1-\Gamma_{\textrm{max}}^2)}" />

<img src="https://latex.codecogs.com/gif.latex?N" />：伝送線路の段数、<img src="https://latex.codecogs.com/gif.latex?\Gamma_{\textrm{max}}" />：帯域内許容反射係数、<img src="https://latex.codecogs.com/gif.latex?R" />：変成比 <img src="https://latex.codecogs.com/gif.latex?R_L/Z_0" />、<img src="https://latex.codecogs.com/gif.latex?Z_0" />：給電線路の特性インピーダンス

### アルゴリズム
最適化設計のアルゴリズムに関して、以下の３つの基準で審査する。

#### 初期値の設定法
効率的な最適化設計には、適切な初期値の設定が不可欠である。どのような思想で初期値を設定したのか、導出したのか。あるいは、どのような思想で最適化パラメータの数を制限したのか。合理的かつ効果的な手法が用いられているか、編み出されたか、を審査する。

#### コスト関数
コスト関数は、最適化設計プログラムの中でその性能を左右する大きな要素である。

#### 最適化手法
提供したサンプルプログラムは、Python の scipy モジュールで提供されている最急降下法を用いた実装例である。参加者は、Python の各種モジュールで提供されている機能を利用しても良いし、フルスクラッチしても良い。

### コード
コードの見易さ、簡潔さ、Python のコードとしての完成度など

### プレゼンテーション
発表者の印象、明快さ、見易さ、聴きやすさ、など

## 開発環境
[Google Colaboratory](https://colab.research.google.com/) https://colab.research.google.com/ を利用する。
ウェブサービスであるので、ユーザは煩雑なインストール作業をする必要がなく、参加の敷居を大幅に下げることが期待される。
また、実行環境を統一することが可能で、公平な評価にも役立つ。
サンプルコードも、Google Colaboratory で実行可能な形式で提供する。

## 開発支援
[質問箱](https://github.com/h403/EST2018/issues) を開設するので、これを利用して適宜質問してください。担当者が、可能な範囲で回答します。他のチームの参加者も閲覧できるので、自チームの戦略がバレてしまう可能性に配慮してください。

## スケジュール

- 審査会ー５ｗ：参加者募集開始
- 審査会ー１ｗ：開発プログラム・設計データの提出

### 審査会タイムテーブル

- 13:00 開会の挨拶
- 13:05-13:50 特別講演（演者検討中）
- 14:00-14:30 デモンストレーション（仕様４）
- 14:30-15:30 ショートプレゼンテーション
- 15:45-18:00 コード公開審査
- 18:00-18:15 非公開審査
- 18:30 表彰式
