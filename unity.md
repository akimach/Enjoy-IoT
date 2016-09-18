# Unity

Unityは、初心者からプロまで使えるゲーム開発環境です。一度作ったゲームは、iOSやAndroid、Windows、Mac OSXといったスマホやパソコンをはじめ、PlayStation、Xbox、WiiUなどのゲーム機上でも動かすことができます。

有名なゲームだと以下のものがUnityを使って作られています。

* ポケモンGO
* 魔法使いと黒猫のウィズ
* スマホ版のドラゴンクエスト8

今回は、簡単なゲームを作りながらUnityについて学んでいきたいと思います。

![unity](img/unity-01.png)

* YouTube
    * https://www.youtube.com/watch?v=abzupULmfjk

## Unityでゲームを作る方法

Unityには、画像やBGM、効果音、テキストなどを簡単に扱うための仕組みが備わっています。

下の画像はUnityでゲームを作る仕組みを示したものです。

![unity-system](img/unity-system.png)

シーンは、ゲームの1つの画面に対応します。このシーン上に、画像やBGM、ボタンなどの登場人物を作り上げていきます。

スクリプトは、ゲームのルールやキャラクターの動きを決める部分です。例えば、「ジャンケンに3回勝ったら、ゲームクリア」、「スペースを押したらキャラクターをジャンプさせる」。こういったルールを作りには、スクリプトを書かないといけません。

## プロジェクトの作成

Unityを起動して、右上の「NEW」をクリックします。

![unity 02](img/unity-02.png)

ゲーム名、ゲームのファイルを置く場所を入力し、「2D」にチェック、Enable Unity Analyticsを「OFF」にします。「Create project」をクリックします。

![unity 03](img/unity-03.png)

下のような画面(Mac OSX)が表示されます。

![unity 04](img/unity-04.png)

下の画面はWindows版です。どうでしょうか。どちらの画面もほとんど同じですね。

![unity 05](img/unity-05.png)

### 画面

画面の説明をしましょう。まず上にある「▶ボタン」はゲームのスタートボタンで、一番使う機能です。

![unity 06](img/unity-06.png)

Gameという部分では、実際にゲーム時に表示される画面が表示されます。

![unity 13](img/unity-13.png)

上のほうにある「Scene」をクリックすると、シーンが表示されます。

![unity 14](img/unity-14.png)

Hierarchy(ヒエラルキー)と呼ばれる部分は、シーンで使われる画像やBGM、効果音が表示されます。

![unity 07](img/unity-07.png)

Inspector(インスペクター)は、画像のサイズや位置、テキストの色などゲームの登場人物の設定を行う部分です。

![unity 08](img/unity-08.png)

Project(プロジェクト)は、ゲームで使われるあらゆるパーツが表示される部分です。

![unity 09](img/unity-09.png)

Project(プロジェクト)の隣りにある「Console」(コンソール)をクリックすると、デバッグ情報が表示されます。変数の中身やエラー情報を確認したい場合は、こちらを確認してください。

![unity 15](img/unity-15.png)

### テキストの表示

シーンにテキストを追加してみましょう。Hierarchy(ヒエラルキー)の部分で、右クリックして「UI」 > 「Text」をクリックします。

![unity 10](img/unity-10.png)

別の方法では、上の方にある「GameObject」 > 「UI」 > 「Text」をクリックするとテキストを追加することができます。

![unity 11](img/unity-11.png)

テキストが追加されましたか。下のように表示されていると思います。

![unity 12](img/unity-12.png)

シーンを表示した状態で、Textをドラッグしてみたり、文字の大きさや色を変えてみましょう。

![unity 16](img/unity-16.png)

### イベント

ボタンを押したら、別の画面(シーン)に移動させてみましょう。

「ボタンが押された」、「スペースキーが押された」、「キャラクターが衝突した」といった出来事(イベント)が起きたら、何かしたいことがあると思います。画面とユーザの交流が生まれることで、ゲームがより楽しくなりますね。そういったことをやりたい場合は、GameObject(ゲームオブジェクト)と呼ばれる登場人物を作って、イベントとゲームオブジェクトを結びつける必要があります。

![unity msg](img/unity-mgs.png)

まずゲームオブジェクトを作成します。Hierarchy(ヒエラルキー)の部分で右クリックをして、「Create Empty」をクリックします。

![unity 19](img/unity-19.png)

まずゲームオブジェクトにスクリプトを加えます。Inspector(インスペクター)部分の「Add Component」をクリックし、「New Script」 > 「Create and Add」をクリックします。

![unity 20](img/unity-20.png)

Project(プロジェクト)の「NewBehaviourScript」をダブルクリックします。

![unity 21](img/unity-21.png)

すると、MonoDevelopというエディタが起動します。すでに下のようなソースコードが書かれています。ここにイベントが起きたら、やりたいことを書いていきます。

```cs
using UnityEngine;
using System.Collections;

public class NewBehaviourScript : MonoBehaviour {

	// Use this for initialization
	void Start () {
	
	}
	
	// Update is called once per frame
	void Update () {
	
	}
}
```

![unity 22](img/unity-22.png)

Windowsの場合、Visual Stdioというエディタが起動します。

![unity 23](img/unity-23.png)

プログラミングをやる前に、スクリプトの仕組みをみてみましょう。Arduinoのソースコードと似ていないでしょうか。`Start()`と`Update()`という関数があります。最初に一度だけ実行される`Start()`関数、繰り返し実行される`Update()`関数があります。ちなみに、`Start()`と前に`Awake()`という関数が呼び出されています。

![unity script](img/unity-script-system.png)

実際にコードを書いてみましょう。

```cs
using UnityEngine;
using System.Collections;

public class NewBehaviourScript : MonoBehaviour {

	// Use this for initialization
	void Start () {
	
	}
	
	// Update is called once per frame
	void Update () {
	
	}

	// こんいちは、と出力します
	public void Hello ()
	{
		print("こんにちは");
	}
}
```

![unity 24](img/unity-24.png)

今度は、Unityに戻りましょう。シーンにボタンを追加して、ボタンを好きな場所に移動させます。

![unity 17](img/unity-17.png)

ボタンを選択肢、Inspector(インスペクター)の下の方にある「On Click()」の「＋」をクリックします。

![unity 25](img/unity-25.png)

シーンの部分にある「GameObject」を、インスペクター部分にある「None」にドラッグ・アンド・ドロップします。

![unity 26](img/unity-26.png)

## インストール方法

### Windows

以下のサイトを参考にインストールしてください。

* https://unity3d.sakura.ne.jp/unity/install-windows.html
* http://qiita.com/decchi/items/9ea7af993825c1b46023

### Mac OSX

以下のサイトの「ダウンロード（Mac）」をクリックしてUnityをダウンロードします。

https://unity3d.com/jp/unity/qa/patch-releases/5.4.0p1

![unity-osx-01](img/unity-osx-01.png)

ダウンロードが完了したら、「UnityDownloadAssistant-5.4.0p1.dmg」をクリックします。以下のような画面が表示されるので、「Unity Download Assistant.app」をクリックします。

![unity-osx-02](img/unity-osx-02.png)

「開く」をクリックします。

![unity-osx-03](img/unity-osx-03.png)

「Continue」をクリックします。

![unity-osx-04](img/unity-osx-04.png)

「Continue」をクリックします。

![unity-osx-05](img/unity-osx-05.png)

「Agree」をクリックします。

![unity-osx-06](img/unity-osx-06.png)

「Continue」をクリックします。

![unity-osx-07](img/unity-osx-07.png)

パスワードを入力して、OKをクリックします。

![unity-osx-08](img/unity-osx-08.png)

「Continue」をクリックします。

![unity-osx-09](img/unity-osx-09.png)

Unityのダウンロードが開始します。

![unity-osx-10](img/unity-osx-10.png)

Unityのダウンロードが完了しました。

![unity-osx-11](img/unity-osx-11.png)

次にUnityを起動させましょう。下のような画面が出たら、「許可」をクリックしましょう。

![unity-osx-12](img/unity-osx-12.png)

Unityにログインします。IDとパスワードをお持ちのかたは入力し、「Sign In」をクリックします。

![unity-osx-13](img/unity-osx-13.png)

お持ちでない方は、Unityのアカウントを作成します。

![unity-osx-14](img/unity-osx-14.png)

ブラウザが起動し、以下のようなページが表示されます。メールアドレス、パスワード、ユーザー名、お名前、国名、ロボット対策の認証、ポリシーに同意するか、Unityからのお知らせをうけとるか(左上から順)を入力します。入力が完了したら、「Create a Unity ID」をクリックします。

![unity-osx-15](img/unity-osx-15.png)

確認のメールが送信されました。

![unity-osx-16](img/unity-osx-16.png)

PCまたはケータイからメールを確認しましょう。メールに「Link to confirm email」とあるのでクリックします。

![unity-osx-17](img/unity-osx-17.png)

アカウントの作成が完了しました。さきほどの画面に戻って、Unityにログインします。

![unity-osx-18](img/unity-osx-18.png)

IDとパスワードを入力し、「Sign In」をクリックします。

![unity-osx-13](img/unity-osx-13.png)

「Unity Personal」にチェックを入れて、「Next」をクリックします。

![unity-osx-19](img/unity-osx-19.png)

「I don't use Unity in a professional capacity.」にチェックを入れて、「Next」をクリックします。

![unity-osx-20](img/unity-osx-20.png)

アンケート画面になります。面倒でしたら、一番下にスクロールして「OK」をクリックしましょう。

![unity-osx-21](img/unity-osx-21.png)

「Start Using Unity」をクリックして、登録の完了です。

![unity-osx-22](img/unity-osx-22.png)
