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

## Unityのインストール方法

[こちら](/install-unity.md)を参考にしてください。

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

![unity msg](img/unity-msg.png)

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

	// こんにちは、と出力します
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

別の方法では、インスペクター部分にある「None」をクリックして、表示される画面の「Game Object」をクリックする方法もあります。

![unity 27](img/unity-27.png)

次に呼び出す関数を指定します。「On Click()」にある「No Function」 > 「NewBehaviourScript」 > 「Hello()」をクリックします。

![unity 28](img/unity-28.png)

さて、これで完了です。ゲームを動かしてみましょう。ボタンをクリックすると、コンソール部分に「こんにちは」と表示されました。

![unity 29](img/unity-29.png)

次のステップに行く前に、シーンの保存をしましょう。上のほうにある「File」 > 「Save Scene」をクリックします。

![unity 31](img/unity-31.png)

下のような画面が表示されるので、「Start.unity」という名前でシーンを保存します。

![unity 31](img/unity-32.png)

## 画面遷移

それではゲームの骨組みを作っていきます。下のような感じで画面を作ります。

![unity 30](img/unity-30.png)

### シーンの作り方

シーン(画面)の作り方をみていきます。プロジェクトの部分で右クリックして、「Create」 > 「Scene」をクリックします。

![unity 33](img/unity-33.png)

シーンの名前を「Stage」としましょう。

![unity 34](img/unity-34.png)

さて、スタート画面からステージ画面に移るようにしてみましょう。

プロジェクト部分にある「NewBehaviourScript」スクリプトをダブルクリックします。起動したエディタを使って、スクリプトに次のようなソースコードを追加します。

```cs
using UnityEngine;
using System.Collections;
using UnityEngine.SceneManagement;

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

	// 別の画面に移ります
	public void JumpScene (string scene)
	{
		SceneManager.LoadScene(scene);
	}
}
```

追加した`JumpScene()`関数は引数として受け取った名前(`string scene`の部分ですね)の画面(シーン)に移ります。`scene`に遷移する画面名を教えてあげることで遷移します。

Unityに戻ってボタンの「On Click()」部分の「NewBehaviourScript.Hello()」を「JumpScene」に変更します。

![unity 35](img/unity-35.png)

すると入力部分ができているので、そこに「stage」と入力しましょう。この部分が`JumpScene (string scene)`の引数に相当します。

![unity 36](img/unity-36.png)

さて、ゲームを実行してみましょう。しかし、うまくいきません。エラーが出ているようです。

![unity 37](img/unity-37.png)

各画面(シーン)は別々に独立しているので、お互いに画面があることを教えてあげる必要があります。

上の方にある「File」 > 「Build Settings」をクリックします。

![unity 38](img/unity-38.png)

使用するシーンを「Scens In Build」の部分にドラッグ&ドロップします。このときに注意することがあります。先にくるシーンを上のほうにくるようにしなければいけません。「Start」、「Stage」の順になるようにしましょう。

![unity 39](img/unity-39.png)

「Build」をクリックします。

![unity 40](img/unity-40.png)

次にような画面が表示されますので、適当な名前を入力して「Save」をクリックします。

![unity 41](img/unity-41.png)

ゲームを実行してみましょう。スタート画面のボタンをクリックすると、何もない画面に移りました。

![unity 42](img/unity-42.png)

課題です。画面遷移が以下の図になるようにしてみましょう。

![unity 30](img/unity-30.png)

## キャラクターを動かす

まず以下のリンクにある画像をダウンロードしましょう。

https://github.com/akimach/Enjoy-IoT/tree/master/materials/images

プロジェクトの部分に、画像をドラッグ&ドロップします。

![unity 43](img/unity-43.png)

Stageシーンの「Main Camera」をダブルクリックします。すると、シーン部分の中央にカメラがくるようになります。

![unity 44](img/unity-44.png)

シーン部分にロボットの画像をドラッグ&ドロップしましょう。サイズや位置を調節しましょう。

![unity 45](img/unity-45.png)

ロボットの画像を選択して、右側のインスペクター部分の「Add Component」をクリックします。そこから、「Physics 2D」 > 「Rigidbody 2D」をクリックします。

![unity 46](img/unity-46.png)

ゲームを実行してみましょう。ロボットが落っこちました。

![unity 47](img/unity-47.png)

インスペクターから質量などの調整ができるので、いろいろと試してみましょう。

![unity 48](img/unity-48.png)

ロボットが落っこちないように床を作ってみましょう。グレーのブロック画像をシーンにドラッグ&ドロップします。ロボットが落ちるそうなところに画像を移動させます。

![unity 49](img/unity-49.png)

ブロックをコピー&ペーストして、ブロックを増やしてみましょう。

![unity 50](img/unity-50.png)

![unity 51](img/unity-51.png)

上のほうにある十字矢印のボタンをクリックして、ブロックを移動します。

![unity 52](img/unity-52.png)

ブロックを動かないように固定します。ブロックを選択して、「Add Component」 > 「Physics 2D」 > 「Box Collider 2D」をクリックします。

![unity 53](img/unity-53.png)

ロボットを選択して、「Physics 2D」 > 「Box Collider 2D」をクリックします。

![unity 55](img/unity-55.png)

ゲームを実行してみましょう。ブロックの上のロボットが乗りました。

![unity 54](img/unity-54.png)

## ロボットをジャンプさせる

今度は、ロボットをジャンプさせてみましょう。

「robot」を選択して、「Add Component」 > 「New Script」をクリックして、「Robot」という名前でスクリプトを作成します。

![unity 56](img/unity-56.png)

「Robot」スクリプトをダブルクリックして、エディタを起動します。以下のコードを追加します。スペースを押したら、ジャンプするようになります。

```cs
using UnityEngine;
using System.Collections;

public class Robot : MonoBehaviour {

	// Use this for initialization
	void Start () {
	
	}
	
	// Update is called once per frame
	void Update ()
	{
		// スペースを押したら、ジャンプしる
		// 上方向に初速度10
		if (Input.GetKeyDown(KeyCode.Space)) {
			this.GetComponent<Rigidbody2D>().velocity = new Vector2(0.0f, 10.0f);
		}
	}
}
```

![unity 57](img/unity-57.png)

しかし、これではジャンプ中でもジャンプすることが可能です。そこで、「ブロックについている間だけ、ジャンプできる」ようにします。

「ロボットとブロックについている」 = 「ロボットとブロックが衝突している」なので、衝突についてみてみましょう。

関数の`void OnCollisionEnter2D (Collision2D collision)`を追加することで、衝突したかどうかを知ることができます。

```cs
using UnityEngine;
using System.Collections;

public class Robot : MonoBehaviour {

	bool isGround = false;
	
	// Use this for initialization
	void Start () { }

	// Update is called once per frame
	void Update () {
		if (Input.GetKeyDown(KeyCode.Space) && isGround) {
			isGround = false;
			this.GetComponent<Rigidbody2D>().velocity = new Vector2(0.0f, 10.0f);
		}
	}

	// 物体が衝突した時に 呼び出されます
	void OnCollisionEnter2D (Collision2D collision) {
		print("衝突しました");
		isGround = true;
	}
}
```

ゲームを実行してみましょう。ブロックに触れていないとジャンプができないようになりました。

![unity 58](img/unity-58.png)

### 落下したらゲームオーバーにする

次に落下したらゲームオーバーの画面に移るようにしましょう。落下したことをどうやったら知ることができるでしょうか。

今回は、画面外の下に仮想的なブロックを用意してそれに衝突したらゲームオーバーの画面に遷移します。

まずHierarchy(ヒエラルキー)の部分で右クリックして、「Create Empty」をクリックします。

![unity 60](img/unity-60.png)

名前を「GameOverArea」として、「Add Component」 > 「Physics 2D」 > 「Box Collider 2D」をクリックします。

![unity 59](img/unity-59.png)

画面下いっぱいにブロックが来るように調節します。

![unity 61](img/unity-61.png)

「GameOverArea」にスクリプトを追加します。「Add Component」 > 「New Script」をクリックして、「GameOverArea」というスクリプトを追加します。

![unity 62](img/unity-62.png)

「GameOverArea」エディタをダブルクリックして、エディタを起動させます。下のようなソースコードを追加します。

```cs
using UnityEngine;
using System.Collections;
using UnityEngine.SceneManagement;

public class GameOverArea : MonoBehaviour {

	// 物体が衝突した時に 呼び出されます
	void OnCollisionEnter2D (Collision2D collision) {
		print("ゲームオーバーです");

		// ゲームオーバー画面に移ります
		SceneManager.LoadScene("GameOver");
	}
}
```

ロボットの初期位置をずらして、画面外に落としてみましょう。ゲームオーバー画面に移りましたか？

![unity 63](img/unity-63.png)

### 床の移動

床をたくさん並べて、横に移動させてみます。するとどうでしょうか。ロボットを移動しているように見えます。

まずは１つの床を移動させてみましょう。ブロックを選択して、「Add Component」 > 「New Script」をクリックして、「Ground」というスクリプトを追加します。

![unity 63](img/unity-63.png)

「Ground」スクリプトをダブルクリックして、エディタを起動させます。下のようなコードを追加します。

```cs
using UnityEngine;
using System.Collections;

public class Ground : MonoBehaviour {

	// 移動速度
	public float speed = 0.15f;
	// 初期位置
	public float xPosition = 0.0f;

	// Use this for initialization
	void Start () {
		// ブロックの初期位置を記憶します
		xPosition = this.transform.position.x;
	}
	
	// Update is called once per frame
	void Update () {
		// 毎回左に移動していきます
		Vector3 pos = new Vector3(0.5f, this.transform.position.y, 0);
		xPosition -= speed;
		pos.x = xPosition;
		this.transform.position = pos;
	}
}
```

実行するとブロックが移動していることが分かりますね。ブロックを選択して、インスペクターを見ると「Speed」を見るという項目が追加されました。ここから、ブロックの移動速度を調節することができます。

![unity 66](img/unity-66.png)

ブロックをコピペして増やします。

![unity 67](img/unity-67.png)

実行してみましょう。ロボットが移動しているように見えますね。

次にゴールを作ってみましょう。ゴール用のブロックに触れたら、ゲームクリア画面に遷移します。

まず、金色のブロックをシーンにドラッグ&ドロップしたあと、ブロックの位置を調整します。

![unity 68](img/unity-68.png)

ゴール用のブロックを選択して、「Add Component」 > 「Physics 2D」 > 「Box Collider 2D」をクリックします。次に「Add Component」 > 「New Script」をクリックして、「GoalGround」というスクリプトを追加します。エディタ上で「GoalGround」スクリプトに、次のソースコードを追加します。

```cs
using UnityEngine;
using System.Collections;
using UnityEngine.SceneManagement;

public class GoalGround : MonoBehaviour {

	// 移動速度
	public float speed = 0.15f;
	// 初期位置
	public float xPosition = 0.0f;

	// Use this for initialization
	void Start () {
		// ブロックの初期位置を記憶します
		xPosition = this.transform.position.x;
	}
	
	// Update is called once per frame
	void Update () {
		// 毎回左に移動していきます
		Vector3 pos = new Vector3(0.5f, this.transform.position.y, 0);
		xPosition -= speed;
		pos.x = xPosition;
		this.transform.position = pos;
	}
	
	void OnCollisionEnter2D (Collision2D collision) {
		// ステージ終了
		print("クリア");
		// ゲームクリア画面に移ります
		SceneManager.LoadScene("GameClear");
	}
}
```

ゲームを動かしてみましょう。ゴール用のブロックに触れると、ゲームクリア画面に移りました。ジャンプして乗り越えてしまわないように、ゴール用のブロックを増やしておきましょう。

![unity 69](img/unity-69.png)

普通のブロックを選択して削除して穴を作ります。ジャンプしないと落っこちてしまうような穴のほうが、スリルがあっていいですよ。

![unity 70](img/unity-70.png)

お疲れ様でした。これでゲームの骨組みが完成しました。次のステップとして、BGMや効果音を付けて、ゲームをお化粧させてみましょう。
