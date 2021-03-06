# EnchantDojo

## 概要
このドキュメントは [ドットインストール](http://dotinstall.com/ "ドットインストール") というサイトで公開されている「 [enchant.js入門](http://dotinstall.com/lessons/basic_enchant_js_v2 "enchant.js入門") 」を使いつつ、動画で触れられていない点を補足するものです。

比較対象として [Scratch](http://scratch.mit.edu/ "Scratch") の事例を参照しますのでScratchを使ったことのない人は先にScratchを体験しておくとよいかもしれません。

またパソコン操作の基礎知識があることを前提としています。パソコンの操作については細かく説明しません。ご了承ください。


## 必要な環境
* パソコン
* インターネットに接続できる環境
* HTML5+JavaScriptをサポートしているブラウザ（Chrome、Firefoxなど）
* プログラムを入力するためのテキストエディタ


## 利用する教材
* ドットインストール [enchant.js入門](http://dotinstall.com/lessons/basic_enchant_js_v2 "enchant.js入門")


*****

# レッスン１

## [#01 enchant.jsとはなにか？](http://dotinstall.com/lessons/basic_enchant_js_v2/11501 "enchant.jsとはなにか？")
国産のゲーム開発用フレームワークである **enchant.js** について、その概要、公式サイト、必要となる知識やツールなどを解説していきます。

* 概要
* 公式サイト
* 必要となる知識
* 必要となるツール

> 補足

### 公式サイト
[こちら](http://enchantjs.com/ja/)

### Scratchとの大きな違い
Scratchとenchant.jsではとても大きな違いがあります。

* ScratchはScratchという一つの **道具** でプログラムを全て作ることができる
* enchant.jsではブラウザやテキストエディタやお絵かきツールなどいくつかの **道具** を使うことになる

大変に思えるかもしれませんが道具の使い処が分かってしまえばScratch以上にいろいろなことができる。それがenchant.jsです。

# レッスン２

## [#02 開発の準備を進めよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11502 "開発の準備を進めよう")
最新版をダウンロードしたのちに必要なファイルを取り出し、開発の準備を進めていきます。

* 必要なファイルの準備
* main.jsの作成
* 動作確認

> 補足

### プログラム作成用フォルダの用意
ダウンロードするenchant.jsのファイルを置いたり、自分のプログラムを作る場所としてフォルダを作成します。

### enchant.jsの最新版をダウンロードするには
enchant.jsの公式ページ http://enchantjs.com/ja/ をブラウザで表示します。なお ja/ を付けないと英語のページが表示されます。

画面の上の方の「Download」をクリックします。次の図の矢印の先です。

![alt "図2-1"][lesson02-01]

    青いDownloadボタンでもダウンロードページへ移動できるのですが、こちらの方は英語のページへ移動してしまうようです。2013/03/19現在

ダウンロードページへ移動したら青いDownloadボタンを押すことでダウンロードが始まります。

次の図の矢印の先です。

![alt "図2-2"][lesson02-02]

### ダウンロードしたファイルを使えるようにする
まずはダウンロードしたファイルを移動します。移動先は先に用意しておいたプログラム作成用のフォルダです。

ダウンロードしたファイルはzipファイルという形式になっています。

このままでは使用できませんので「展開」する必要があります。

以下はzipファイルを展開する操作の例です。

* Macではファイルをダブルクリック
* Windowsではファイルを右クリックした後に表示されるメニューから「ここへ展開」を選択します。

### 自分のプログラム用フォルダの用意
自分のプログラムを保存するフォルダを作成します。

### 自分のプログラムを動かす
index.htmlをブラウザへドラッグ＆ドロップすることで動かすことができます。

プログラムを書き換えた後にはブラウザをリロードして動作を確認します。

### window.onload()
プログラムが始まることを表すwindow.onload()はScratchの「緑の旗がクリックされたら」みたいなものと考えてください。
onloadとは「ファイルが読み込まれたとき」といった意味です。

![alt "図2-4"][lesson02-04]


### JavaScriptコンソールの開き方
JavaScriptコンソールの開き方は使用しているブラウザによって違います。
以下の図はChromeとFirefoxでどのようにメニューをたどるとコンソールを表示できるかを説明した物です。

* Chrome 25では「ツール→JavaScriptコンソール」

![alt "図2-5"][lesson02-05]

* Firefox 19では「Web開発→Webコンソール」

![alt "図2-6"][lesson02-06]

> レッスン２のソースコード

```javascript
enchant();

window.onload = function() {
	console.log('hello world');
};
```

# レッスン３

## [#03 クマを表示してみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11503 "クマを表示してみよう")
CoreやrootScene、Spriteの説明をしたのちにまずはクマの画像を表示してみます。

* Core、rootScene、Sprite
* Coreの設定
* bearの設定
* bearの設置
* 動作確認

> 補足

### 画像ファイルフォルダ
enchant.jsのフォルダの中に「<font color="blue">images</font>」という名前のフォルダがあります。

このフォルダの中にプログラムに利用できる画像が置いてあります。

### new Core(320, 320)の320についての話。
これはゲームを作る上でゲーム中に表示するものが見える範囲のサイズを指定しています。

コンピュータはピクセル（ドットとも言う）と呼ばれる光の点の集まりで画面に絵や字を表示します。

new Core(320, 320)という指定は横320個、縦320個のピクセルを使うことを意味します。

このドキュメントではこの見える範囲のことをゲーム画面と呼ぶことにします。

なお320ではなく好きなサイズを指定することもできます。

ただしゲーム投稿サイト9leap.netでゲームを公開したいのであれば320を指定してください。

次の写真はあるゲーム機です。写真では黒く写っているいわゆる液晶画面の部分がゲーム画面です。

![alt "図3-1"][lesson03-01]


### シーンについて
シーン（Scene）とは、ゲーム画面に表示するものを管理する単位です。

ゲーム画面に表示したいキャラクタはシーンへ登録（addChild）する必要があります。逆に言うと登録しないと表示されません。

Scratchと違ってenchant.jsではスプライトが最初から表示されているわけではないため、表示するためのプログラムを書く必要があります。


### スプライトの表示位置
スプライトの表示位置はx座標、y座標という二つの値で指定します。

enchant.jsのゲーム画面においては画面の左上がx=0、y=0の座標となります。この座標は原点とも言います。

座標の指定は0から始まるため、320✕320サイズのゲーム画面におさまる座標の最大の値はx=319、y=319です。ちょっと変かもしれませんがこういうものだと思っていてください。

スプライトが画面内に表示されているかどうかを判定する場合などに備えてこのルールを覚えておいてください。

次の図はxyの値を増やした場合に画面のどの方向に移動していくのかを表したものです。

スプライトはxの値を増やすと画面の右側へ、yの値を増やすと画面の左側へ移動していきます。

![alt "図3-2"][lesson03-02]

    他のゲームエンジンでは表示位置の指定ルールが違うことがあります。

### Scratchにおける原点
Scratchでプログラムしていると普段気にすることは少ないと思いますが、原点は存在します。

Scratchはenchant.jsとは違いステージ（ゲーム画面）の中央が原点（x=0、y=0）です。

中央が原点なのでenchant.jsとは違って次の図のようにx、yの値が変化します。図でも色分けしていますが四つの領域があると覚えておいてください。

![alt "図3-3"][lesson03-03]

### SpriteをrootSceneに乗せる
動画の中で「SpriteをrootSceneに乗せる」と言っている箇所があります。

この乗せるの意味は先ほども書いた「ゲーム画面に表示したいキャラクタをシーンへ登録する(addChildする)」ということだと考えてください。

シーンへ登録するにはaddChildというメソッドを使います。

シーンへ登録することでスプライトがゲーム画面に表示されるようになります。

なおScratchでは見えているかどうかに関わらず全てのスプライトがステージに乗っていると考えてください。ここは大きな違いです。

    ちなみにchild（子供）と表現しているのはプログラムでデータを扱うときによく使われる構造に由来する表現です。興味がある人は調べてみてください。

> レッスン３のソースコード

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.onload = function() {
		
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		core.rootScene.addChild(bear);
	}
	core.start();
	
};
```

# レッスン４

## [#04 クマを動かしてみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11504 "クマを動かしてみよう")
enterframeイベントを使ってクマを移動・回転・拡大させてみます。

* enterframeイベント
* 移動
* 回転（rotate）
* 拡大（scale）

> 補足

### フレーム
動画の解説にフレームという言葉がいきなり出てきます。

今後気をつけないといけないのはenchant.jsではフレームという言葉が意味する内容が状況によって変わることです。

レッスン４でのフレームの意味はゲームの進行にあわせてゲーム画面全体を書き換える１セットの操作のことを表します。

レッスン５でもフレームという言葉が出てきますがレッスン４とは違う意味のフレームです。これはレッスン５で説明します。

### enterframe
enterframeを無理矢理Scratchで説明すると「ずっと」の中身です。

次のenchant.jsのスクリプトの赤い部分が

![alt "図4-1"][lesson04-01]


次のScratchのスクリプトの赤い四角に対応すると考えてください。

![alt "図4-2"][lesson04-02]

なおenchant.jsでは「ずっと」ブロックに対応するプログラムはひとまず書かなくても大丈夫なようになっています。

### ゲーム画面のはし
クマが右側に歩いていって、あるところまで来たら左から登場する動きを表すプログラムについての補足です。
```javascript
if (this.x > 320) {
  this.x = 0;
}
```

これは「もしスプライトの表示位置がゲーム画面の外に出たら○○する」という意味です。（thisというのは状況で対象が変わるのですがここではbearのことです）

Scratchでいうところの「はしにさわったら」に近いものではあるのですが、でもやっぱり違います。

Scratchで近い動きを表現すると次のようなスクリプトになると思います。

![alt "図4-3"][lesson04-03]

スプライトの表示位置とゲーム画面の端っこの関係についてのサンプルプログラムを用意しました。

このサンプルでは二頭のクマがそれぞれ右と左へ歩いていきます。

そして表示位置がゲーム画面の外に出たら停止するというプログラムになっています。

https://github.com/kivatek/EnchantCoordDemo

それぞれのクマが停止する位置の違いに注目してください。

右へ歩いたクマは見えなくなってから停止しますが、左へ歩いたクマは見えているうちに停止します。

これはスプライトの表示位置がスプライトの左上であることが理由です。レッスン３でも少し触れましたがスプライトがゲーム画面内にあるかどうかを判定する場合の重要なルールですのでよく覚えておいてください。

    enchant.jsに慣れてくるとスプライト表示を細かく設定できることが分かると思います。興味がある人は調べてみてください。

> レッスン４のソースコード

動画の１分４０秒あたりの動きを再現するソースです。動画では回転や拡大を行う説明が続きます。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
			this.x += 10;
			if (this.x > 320) this.x = 10;
		});
		
		core.rootScene.addChild(bear);
	}
	core.start();
	
};
```

# レッスン５
## [#05 アニメーションを作ってみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11505 "アニメーションを作ってみよう")
Spriteのframeを操作することでアニメーションを実現していきます。

* Spriteのframe
* core.fps
* Spriteのage

> 補足

### フレーム(frame)
レッスン５で説明するフレームはレッスン４で出てきたフレームとは意味が異なります。注意してください。

enchant.jsのスプライトは動いているように見える何枚かの画像を一枚の画像にまとめて扱います。

そしてスプライトを用意するときに指定したサイズで切り分けてゲーム画面に表示を行います。

enchant.jsでは指定サイズで切り分けた画像の一枚一枚をフレームと呼びます。

一枚一枚のフレームがScratchでのコスチュームだと考えてください。Scratchのコスチュームはそれぞれ別の絵を用意するのでちょっと違いますね。

次のプログラムは画像chara1.pngから横32ピクセル、縦32ピクセルのサイズで画像を切り分けてスプライトとして表示する例です。

```javascript
var bear = new Sprite(32,32);
bear.image = core.assets['chara1.png'];
bear.frame = 0;
```

スプライトを表示する際、何番目のフレームを表示するかを指定することができます。

たとえば上のプログラムの bear.frame = 0; の部分が表示するフレーム番号をしているプログラムの例です。この例だと棒立ちのクマを表示することになります。

フレーム番号は切り分ける前の画像の左上から右に向かって順番に割り当てられています。

フレーム番号の割り当てルールを説明する図を用意しました。

![alt text][lesson05-01]

ところで、上の図で９と表示されている箇所に注目してください。

ここにはクマの画像はありません。ありませんがフレーム番号９として存在します。

<font color="red">**人間が目で見てクマの絵が無いからといって番号をスキップするわけではありません。**</font>

もしプログラムでこのフレーム番号９を表示するように指定するとゲーム画面には何も表示されていないように見えるでしょう。

### age: 動き始めてからのフレーム数とは？
このフレームはレッスン４で出てきたフレームの意味です。

ゲーム画面全体を書き換える処理が行われる中で、そのスプライトの処理が何回行われたかを表しています。

ゲーム画面全体を書き換える処理が一回行われるたびにスプライトが誕生日を迎えるとでも思ってください。

サンプルプログラムはこちら。画面左上に表示されている数字がクマスプライトの「age」の値です。

https://github.com/kivatek/EnchantAgingDemo

なおスプライトの処理が行われると言うことはゲーム画面へ登録されているということです。逆に言うとスプライトを用意してもゲーム画面に登録していなければ何も行われません。

    実は見た目の画面の変化が無くてもプログラム的には画面を書き換える操作が発生しています。


### 剰余算
「%」という記号で計算した答えは、普通の算数の感覚とは違う答えになります。（%は普通にはパーセント・百分率の記号ですがプログラムでは特別な記号として使われます）

これは剰余算といって割り算を行ったときに割り切れなかった部分の分子を答えとする特別な計算です。

次の図の赤い○で囲まれた部分が剰余算での答えとなります。

![alt text][lesson05-02]

ちなみに上の図の内容をプログラムで書くと次のようになります。

```javascript
answer1 = 1 % 3;	// answer1は1
answer2 = 2 % 3;	// answer2は2
answer3 = 3 % 3;	// answer3は0
answer4 = 4 % 3;	// answer4は1
```


### 指定したfpsで動かない？
パソコンの性能によっては設定したfpsで動作しないことがあります。

最近のパソコンだとあまり気になることはないと思いますが、少し前のパソコンを使っている場合には表示がカクカクする場合があるかもしれません。

> レッスン５のソースコード

動画の２分１０秒あたりの動きを再現するソースです。動画では表示するスプライトを白クマに切り替える説明が続きます。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		bear.frame = 0;
		
		bear.addEventListener('enterframe', function() {
			this.x += 10;
			this.frame = this.age % 3;
			if (this.x > 320) this.x = 10;
		});
		
		core.rootScene.addChild(bear);
	}
	core.start();
	
};
```

# レッスン６
## [#06 クマを操作してみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11506 "クマを操作してみよう")
矢印キーやタッチイベントでクマを動かしてみましょう。

* 上左右キーの入力
* Spriteのタッチイベント
* Coreのタッチイベント

> 補足

### 名前が違っても同じように動くメソッド
動画でも説明がありますがaddEventListenerという長いメソッド名の代わりにonと書いても同じように動きます。

覚えやすく間違いにくいのでメソッド名はonを使うと良いでしょう。

    このようにenchant.jsでは同じ機能を違う名前のメソッドとして扱うことがあります。

### タッチの情報を受け取る
タッチの情報を受け取ることは、私たちの生活で言うとメールを受け取るようなものです。

メールを受け取るには差出人が正しい宛先を知っている必要があります。この場合タッチ情報というメールの差出人はenchant.jsとなります。
つまりenchant.jsがタッチ情報の宛先を知っている必要があります。

ドットインストールのサンプルではタッチ情報をcore.rootSceneが受け取るようにプログラムされています。

サンプルのように簡単なプログラムであれば問題ないのですが、実際にゲームを作る場合にはcore.rootSceneを直接届け先とするのは避けた方がよいでしょう。

むしろcore.rootSceneを届け先とするのはサンプルプログラムなどの特別な場合だけです。

ゲームではタッチする場所ごとに反応する内容が違うことが普通なので、タッチ情報の宛先も個別に細かく指定することになると思います。
たとえばスプライトも宛先となります。（サンプルでも使われています）

### 「e」って何？
eは英語のevent（イベント）の頭文字のeです。

私たちの生活でイベントというとお正月とか誕生日とか特別なことが起きることを言います。

プログラムの世界では特別なことという意味はちょっと薄いです。何かが起こったきっかけというくらいの意味でしょうか。

enchant.jsにおけるイベントとはあらかじめ決めておいた状況になったことを連絡してくるメールみたいなものとイメージしてください。

そしてそのメールの内容に状況に関連する情報が書かれている程度に覚えておいてください。（先ほどのタッチ情報もその一例です）

enchant.jsではプログラム的に必要な多くのイベントがあらかじめ用意されています。

公式ドキュメントは[こちら](http://wise9.github.com/enchant.js/doc/core/ja/symbols/enchant.Event.html "enchant.Event")

以下のイベントがゲームで使う頻度が高いと思います。

* enchant.Event.ENTER_FRAME
* enchant.Event.TOUCH_START
* enchant.Event.TOUCH_MOVE
* enchant.Event.TOUCH_END
* ボタンが押されたときに発生するイベントなど

### 消えたクマの復活
クリックして消えてしまったクマですが、ドットインストールのサンプルではゲーム画面への登録を解除(removeChild)しているため普通には再び見えるようにすることはできません。

この点はScratchとの大きな違いです。

Scratchでは隠すことで見えないようにするだけのことですが、enchant.jsでremoveChildすると本当に消えてしまいます。

同じように見えるスプライトを新しく追加するか、またはちょっとしたテクニックを使ってスプライトを復活させるかプログラムの目的に合わせて手段を選んでいくことになります。

### スプライトを隠す
なおScratchのスプライトを隠すに近いことをenchant.jsでも行うことができます。スプライトの変数を操作してvisible = falseに設定することで見えない状態にすることができます。

ちなみに見えなくなっただけでタッチ操作には反応します。見えないことをうまく使ったテクニックも考えられますし、もしタッチに反応させたくない場合はスプライトの変数touchEnabledをfalseにしてください。

https://github.com/kivatek/EnchantInvisibleSpriteDemo

> レッスン６のソースコード

動画の２分３０秒あたりの動きを再現するソースです。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
			if (core.input.left) this.x -= 5;
			if (core.input.right) this.x += 5;
			if (core.input.up) this.y -= 5;
			if (core.input.down) this.y += 5;
		});
		
		bear.on('touchstart', function() {
			core.rootScene.removeChild(this);
		});

		core.rootScene.on('touchstart', function(e) {
			bear.x = e.x;
			bear.y = e.y;
		});

		core.rootScene.addChild(bear);
	}
	core.start();
	
};
```

# レッスン７

## [#07 ラベルを表示してみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11507 "ラベルを表示してみよう")
ラベルを作成し、経過時間を表示させてみます。

* ラベルの作成
* 経過時間の表示

> 補足

### カラー指定
ラベルに表示する文字の色を指定することができます。サンプルで'red'と指定している箇所を'green'、'blue'などと書き換えてみてください。違いが分かると思います。

この色の指定はHTMLのルールに沿った指定ができますので興味がある方は調べてみてください。

また名前ではなく光の三原色である赤緑青の値を指定した書き方も可能です。例えば次の様な指定をすると緑文字のラベルが表示されます。

```javascript
label.color = '#00FF00';
```


### フォント指定
次のコードはサンプルからの抜粋です。

```javascript
label.font = '14px "Arial"';
```

このうち14pxと書いている部分は文字の大きさを指定しています。たとえば20pxなどに書き換えてサイズが変わることを確認してください。

またArialと書いている部分は使用するフォントの種類を指定します。表示する文字の雰囲気を変えることができるのですが、そのためにはフォントの名前を知っている必要があります。興味がある方は調べてみてください。

    フォントの種類は使っているマシンに依存します。たとえばMacでは期待通り表示されてもWindowsでは期待通りに表示されないといったことが発生します。

### core.fps
fpsは１秒間に画面を描き換える回数を指定します。

描き換える回数が多いほどなめらかな動きを表現できるようになるのですが、使っているマシンの性能が低いと処理しきれないこともあります。

処理しきれないとはどういうことかというと、たとえば高速シューティングゲームを作ったつもりでも古めのパソコンで動かすとゆっくりと動いてしまうといったことが起きます。（場合によってはそもそも正しく動かない）

    参考までに…ディズニーのアニメは１秒間に24回描き換えますが、日本のアニメは8回だったり12回だったりします。
    PS3などのゲーム機では１秒間に30回または60回描き換えることが一般的です。（とはいえ実際にはいろいろとわけありだったりします）


### core.frame
ゲームプログラムが動き始めてから画面の描き換えを何回行ったかを記録している変数です。

一見変化が無くても画面の描き換えが行われていることがわかると思います。

> レッスン７のソースコード

動画の２分１８秒あたりの動きを再現するソースです。動画では表示位置の修正と表示内容を秒数に変更する説明が続きます。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
		});

		var label = new Label();
		label.x = 300;
		label.y = 5;
		label.color = 'red';
		label.font = '14px "Arial"';
		label.text = '0';
		bear.on('enterframe', function() {
			label.text = core.frame;
		});

		core.rootScene.addChild(label);
		core.rootScene.addChild(bear);
	}
	core.start();
	
};
```

# レッスン８

## [#08 衝突判定をしてみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11508 "衝突判定をしてみよう")
もう一つのクマを作り、キャラクター同士の衝突判定をしてみます。

* enemyの作成
* intersect
* within

> 補足

### コメント
プログラムに「//」を書くと、書いた場所より後ろは自由に文章を書くことができます。

プログラムが何を行うものなのかのメモを残すためによく使います。（ドットインストールの動画でも何度も使われています）

コメントしてしまうことでプログラムの一部を動かないようにすることにも使えます。

動画では2分15秒あたりで「//」をつけていますが、これでコメント扱いにすることで「label.text = 'hit!';」が動かなくなります。

### デモプログラム
intersectとwithinの動きを同時に見ることが出来るプログラムを用意しました。

プログラムはちょっと複雑に見えるかもしれませんが、内容はドットインストールで紹介されているものに準じています。

https://github.com/kivatek/EnchantCollisionDemo

ちなみに、このデモプログラムで表示されている白クマの向きは動画での見え方と違います。これはちょっとしたテクニックを使っています。

プログラムソースにはどのようなテクニックを使っているかというコメントは残していません。興味がある人は調べてみてください。（そしてなぜ表示が変わるのか考えてみてください）

> レッスン８のソースコード

動画の２分８秒あたりの動きを再現するソースです。動画ではwithinを使った衝突判定の説明が続きます。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
			if (core.input.right) this.x += 5;
			// intersect
			if (this.intersect(enemy)) {
				label.text = 'hit!';
			}

			// within
			
		});

		var enemy = new Sprite(32, 32);
		enemy.image = core.assets['chara1.png'];
		enemy.x = 80;
		enemy.y = 0;
		enemy.frame = 5;

		var label = new Label();
		label.x = 280;
		label.y = 5;
		label.color = 'red';
		label.font = '14px "Arial"';

		core.rootScene.addChild(label);
		core.rootScene.addChild(bear);
		core.rootScene.addChild(enemy);
	}
	core.start();
	
};
```

# レッスン９

## [#09 ゲームオーバー処理をしてみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11509 "ゲームオーバー処理をしてみよう")
ゲームの停止方法、Sceneの作成・追加方法について学びます。

* Sceneの作成
* Sceneの表示
* core.stop()

> 補足

### rootSceneとgameOverSceneの切り替え

ゲームでよくある例に取るとタイトル画面、ゲーム難易度選択画面、ゲーム本編と切り替わることに相当します。

動画で説明されているpushScene以外に関連するメソッドとしてpopScene、replaceScene、removeSceneが用意されています。

    準備中：pushSceneの動きを図解する。

### core.stop()について
enchant.jsを使って作られたプログラムを停止させる命令です。

なお9leapに投稿するプログラムではcore.stop()の代わりにcore.end()を使用することで点数やコメントの登録を行えるようになります。

> レッスン９のソースコード

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
			if (core.input.right) this.x += 5;
			// intersect
			if (this.intersect(enemy)) {
				// label.text = 'hit!';
			}

			// within
			if (this.within(enemy, 10)) {
				// label.text = 'hit!';
				core.pushScene(gameOverScene);
				core.stop();
			}
			
		});

		var enemy = new Sprite(32, 32);
		enemy.image = core.assets['chara1.png'];
		enemy.x = 80;
		enemy.y = 0;
		enemy.frame = 5;
		
		var gameOverScene = new Scene();
		gameOverScene.backgroundColor = 'black';

		var label = new Label();
		label.x = 280;
		label.y = 5;
		label.color = 'red';
		label.font = '14px "Arial"';

		core.rootScene.addChild(label);
		core.rootScene.addChild(bear);
		core.rootScene.addChild(enemy);
	}
	core.start();
	
};
```

# レッスン１０

## [#10 クラスを作ってみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11510 "クラスを作ってみよう")
Spriteを拡張し、自分でクラスを作る方法を学びます。

* クラスの作成方法
* クラスの利用方法

> 補足

### 実際のゲーム作りにおいての注意点

* 「クラス」をどこに記述するか

動画ではBearクラスをcore.onloadの中に記述していますが、レッスン１１で出てくるrand()メソッドのように、window.onload()の外側に用意する形式となります。（さらに複雑なゲームの場合はプログラムのファイルを分けるとよいでしょう）

* スプライトをSceneへ登録するタイミング

動画ではBearクラスのinitialize()の中でSceneへの追加を行っていますが、これは「var bear = new Bear(0, 0);」の後に行う形式の方がよいと思います。

なぜならば実際のゲームにおいては状況次第で登録先を切替えることがあるからです。

> レッスン１０のソースコード

動画の２分１２秒あたりの動きを再現するソースです。動画では表示位置を変更する説明が続きます。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
/*
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
			if (core.input.right) this.x += 5;
		});
		
		core.rootScene.addChild(bear);
*/

		var Bear = Class.create(Sprite, {
			initialize: function(x, y) {
				Sprite.call(this, 32, 32);
				this.x = x;
				this.y = y;
				this.image = core.assets['chara1.png'];
				this.on('enterframe', function() {
					this.x += 5;
				});
				core.rootScene.addChild(this);
			}
		});
		
		var bear = new Bear(0, 0);
	}
	core.start();
	
};
```

# レッスン１１

## [#11 クマをたくさん表示させてみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11511 "クマをたくさん表示させてみよう")
クラスを使ってたくさんのクマを表示させてみます。

* 乱数生成の関数を作成
* クラスの変更
* クマの表示

> 補足

### Math.floor
floorはその数値より小さい一番近い整数を返します。「1.6」は「1」に「-1.6」「-2」になります。

関連するメソッドにceilというメソッドがあります。こちらはその数値より大きい一番近い整数を返します。「1.6」は「2」に「-1.6」「-1」になります。

floorは床・ceilは天井の意味です。小さい値を返すのが足下のfloor、大きい値を返すのが上へ手を伸ばさないと届かないceilとでも覚えてください。

### Math.random
最大数を指定出来るさいころ。Scratchにもありますね。

randomを使用した際に得られる数字の範囲ですが0.0以上1.0未満の値を得ることができます。

動画でrand()というメソッドを用意していますが、渡した数字を上限とする範囲のランダムな整数を送り返してくるメソッドになります。

### 配列
[]を使うことで入れ物の用意をしていると考えてください。

### 透明度opacityの指定
透明度opacityとはスプライトをどの程度の透明具合で表示するかを指定する変数です。

opacityに設定する値は0から1の間です。ですので動画ではrand(100)を実行した結果得られた値を100で割った値を設定するようプログラムしています。

> レッスン１１のソースコード

動画の１分４４秒あたりの動きを再現するソースです。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
/*
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
			if (core.input.right) this.x += 5;
		});
		
		core.rootScene.addChild(bear);
*/

		var Bear = Class.create(Sprite, {
			initialize: function(x, y) {
				Sprite.call(this, 32, 32);
				this.x = x;
				this.y = y;
				this.frame = rand(5);
				this.opacity = rand(100) / 100;
				this.image = core.assets['chara1.png'];
				this.on('enterframe', function() {
					this.rotate(rand(10));
				});
				core.rootScene.addChild(this);
			}
		});
		
		var bears = [];
		for (var i = 0; i < 100; i++) {
			bears[i] = new Bear(rand(320), rand(320));
		}
	}
	core.start();
	
};

function rand(n) {
	return Math.floor(Math.random() * (n+1));
}
```

# レッスン１２

## [#12 Timelineを使ってみよう](http://dotinstall.com/lessons/basic_enchant_js_v2/11512 "Timelineを使ってみよう")
アニメーションに特化したクラス、Timelineを使う方法について学びます。

* tl.moveBy()
* enchant.Easing
* tl.fadeIn() / tl.fadeOut(), tl.loop()

> 補足

### タイムライン(Timeline)とは
Timelineを使うことで計算式を自分でプログラムしなくてもスプライトの座標や透明度を簡単に変化させることができます。

### イージング(Easing)とは
Easingとは座標や透明度の変化に一工夫するための計算式です。

Easingの動きの違いがわかるサンプルプログラムを用意しました。

https://github.com/kivatek/EnchantEasingDemo

なおサンプルで紹介しているのはたくさん用意されているEasingの一部の種類のみです。

使用できるEasingの一覧は[こちら](http://wise9.github.com/enchant.js/doc/core/ja/symbols/enchant.Easing.html)です。

### 参考リンク
「cocos2d for iPhone」というゲームフレームワークのEasingの説明ページをご紹介。

英語のページですがEasingの値の変化がグラフで説明されています。
[こちら](http://www.cocos2d-iphone.org/wiki/doku.php/prog_guide:actions_ease)です。

### timelineの指定の書き方
timelineの指定の書き方は大きく二つのパターンがあります。

timelineの指定をつなげて書く書き方の例。（ドットインストールの書き方はこちら）
```javascript
ball.tl.moveTo(80, 240, 48, enchant.Easing.BOUNCE_EASEOUT).
    then(function() {
        ball.y = 80;
    }).
    loop();
```

timelineの指定をつなげない書き方の例。
```javascript
ball.tl.moveTo(80, 240, 48, enchant.Easing.BOUNCE_EASEOUT);
ball.tl.then(function() {
    ball.y = 80;
});
ball.tl.loop();
```

> レッスン１２のソースコード

動画の１分１４秒あたりの動きを再現するソースです。動画では更にタイムラインを続けて指定する説明が続きます。

```javascript
enchant();

window.onload = function() {

	var core = new Core(320, 320);
	core.preload('chara1.png');
	core.fps = 15;
	core.onload = function() {
		
/*
		var bear = new Sprite(32, 32);
		bear.image = core.assets['chara1.png'];
		bear.x = 0;
		bear.y = 0;
		
		bear.addEventListener('enterframe', function() {
			if (core.input.right) this.x += 5;
		});
		
		core.rootScene.addChild(bear);
*/

		var Bear = Class.create(Sprite, {
			initialize: function(x, y) {
				Sprite.call(this, 32, 32);
				this.x = x;
				this.y = y;
				this.frame = rand(5);
				this.opacity = rand(100) / 100;
				this.image = core.assets['chara1.png'];

				this.tl.moveBy(rand(100), 0, 40, enchant.Easing.BOUNCE_EASEOUT);

				core.rootScene.addChild(this);
			}
		});
		
		var bears = [];
		for (var i = 0; i < 100; i++) {
			bears[i] = new Bear(rand(320), rand(320));
		}
	}
	core.start();
	
};

function rand(n) {
	return Math.floor(Math.random() * (n+1));
}
```

# エクストラ

この章では動画では触れていないポイントについて追加説明します。

## 背景色
ゲーム画面の背景が白色だと有効範囲がわかりづらいので色をつけるとよいかもしれません。

色を付ける場合は次のようにコードを修正します。rgb()の中の数字を0～255の値で書き換えることで自分の好きな色を表現できます。

```javascript
core.onload = function() {
	core.currentScene.backgroundColor = 'rgb(239, 228, 202)';
	
	// 省略
}
```

## Mapを使って地形の表示
RPG風の地面を表示する場合にはMapというクラスを使うと簡単です。

## Groupをうまく使う
例えばRPGなどでよく見かける壁の向こうに人が隠れて表示されるようにしたい場合は、スプライトを単純にaddChildするだけでは表現できません。

この様なときにはGroupという機能を使います。

Groupをものすごく乱暴に説明すると絵を表示しないスプライトと言えます。実際絵を表示すること以外はスプライトとだいたい同じことができます。

### Groupのメリット

* スプライトを目的別に管理しやすい
* 重ね合わせ表示のコントロールがしやすい
* メニューや点数表示のレイアウト調整に役立つ
    * Group自体の座標を動かすことでそのGroupにaddChildされているスプライトの表示位置を一気に動かすことができます。

## より複雑なtimelineの使い方

* and()
* then()
* repeat()

## Scratchの「○秒待つ」に相当するプログラムはちょっと面倒
enchant.jsではScratch「○秒待つ」に相当するプログラムの途中で処理を一時停止するプログラムを書くことはありません。

javascriptのsetTimeout()というメソッドか、またはenchant.jsのタイムラインを利用して一定時間経過後に動くプログラムを用意します。

サンプルプログラムを用意しました。

https://github.com/kivatek/EnchantTimeOutDemo

    本ドキュメントでは説明を省略しますがScratchでのスクリプトの書き方とは違う考え方が必要になります。

## 9leap.netにゲームを投稿する
必要になるファイル。

* nineleap.enchant.js - enchant.jsのplugins/フォルダに置いてあります。
* start.png - enchant.jsのimages/フォルダに置いてあります。
* end.png - enchant.jsのimages/フォルダに置いてあります。

### 画像ファイルstart.png、end.pngを置くフォルダ
nineleap.enchant.jsを使用する場合、画像ファイルstart.png、end.pngはソースファイルと同じフォルダに置きます。（次の図はWindows環境での一例です）

![alt "図Extra-4"][extra-04]

そうしないとアプリの起動に失敗します。（画像ファイルが見つからないことによるエラー）

### zipファイルの作成
9leapへのアップロードはzip形式の圧縮ファイルにしてアップロードすることになります。

* Windowsの場合はエクスプローラ上でアップロードするファイルを選んで右クリックメニューの「送る→圧縮(zip形式)フォルダー」

![alt "図Extra-5"][extra-05]

* Macの場合はファインダー上でアップロードするファイルを選んで二本指のタッチをすると開くメニューから「○項目を圧縮」

![alt "図Extra-6"][extra-06]

WindowsでもMacでも圧縮したファイルには自動で名前が付けられてしまいます。

日本語が使われているとトラブルが起きる可能性があるので、9leapにアップロードする前にアルファベットと数字だけを使ったファイル名に変更するとよいでしょう。

### 本格的な手順
gruntというツールを使うことで圧縮ファイルを作る手順を自動化することができます。

ただし、ここでの説明は省略させてもらいます。（使えるようにする準備がちょっと大変なので…）



-- 脚注

-- 図一覧
[lesson02-01]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson02-01.png "図2-1"
[lesson02-02]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson02-02.png "図2-2"
[lesson02-03]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson02-03.png "図2-3"
[lesson02-04]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson02-04.png "図2-4"
[lesson02-05]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson02-05.png "図2-5"
[lesson02-06]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson02-06.png "図2-6"
[lesson03-01]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson03-01.png "図3-1"
[lesson03-02]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson03-02.png "図3-2"
[lesson03-03]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson03-03.png "図3-3"
[lesson04-01]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson04-01.png "図4-1"
[lesson04-02]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson04-02.png "図4-2"
[lesson04-03]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson04-03.png "図4-3"
[lesson05-01]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson05-01.png "図5-1"
[lesson05-02]: https://github.com/kivatek/EnchantDojo/raw/master/images/lesson05-02.png "図5-2"
[extra-04]: https://github.com/kivatek/EnchantDojo/raw/master/images/extra-04.png "図Extra-4"
[extra-05]: https://github.com/kivatek/EnchantDojo/raw/master/images/extra-05.png "図Extra-5"
[extra-06]: https://github.com/kivatek/EnchantDojo/raw/master/images/extra-06.png "図Extra-6"


