# ゲーム勉強会 議事録

## 2017-12-20
### 参加メンバー
- @kunichiko
- @schroedinger-tiger
- @yabuchin
- @hshiozawa
- @genie-rx
- @amake

### 内容
ゲームを作ってみる目標に合意しました。ジャンルやテーマなどはまだ決まっていません。全員初心者のため、まずはゲーム開発ツールの[Unity](https://unity3d.com/)の[チュートリアル](https://unity3d.com/learn/tutorials)を試してみるところからスタートします。

## 2018-1-10
### 参加メンバー
- @kunichiko
- @schroedinger-tiger
- @yabuchin
- @hshiozawa
- @genie-rx
- @amake

### 内容
@kunichiko さんは[玉転がし](https://unity3d.com/learn/tutorials/s/roll-ball-tutorial)チュートリアルを工夫して iOS にデプロイした成果を発表しました。

お互いの成果を参考にできるように、本 GitHub オーガニゼーションを拠点に作業することにしました。

次回に向けての目標は、もう少しチュートリアルをこなしてみることです。特に 3D のほかに 2D も味わってみること。

### 追加情報 (by @kunichiko)

iOS上で遊べるようにするために、Roll a Ballに CrossPlatformInput を導入しました。
Unity上で「Assets」-「Import Package」-「CrossPlatformInput」とするとプロジェクトに導入できます。

http://tsubakit1.hateblo.jp/entry/2014/10/09/035003

なお、iOSには Game Controller Frameworkというものが標準で用意されていて、Bluetoothなどで接続できるハードウェアゲームコントローラーを使うことができます。
https://developer.apple.com/documentation/gamecontroller

UnityもこのGame Controllerに標準対応していて、通常のInput.GetAxis("...")などを使っていれば、ゲームコントローラーで操作できるはずです（が、対応コントローラーを持っていないので未確認）。
https://docs.unity3d.com/jp/current/Manual/iphone-joystick.html

ただ、Appleのガイドラインには「ハードウェアコントローラーがなくても遊べなくてはいけない」と書かれているようなので、いずれにせよ、CrossPlatformInput かそれに準ずる入力方式はサポートする必要があります。

以下のページのサンプルでは、ハードウェアコントローラーが接続されたら、画面上のバーチャルコントローラーは削除するようにしています。(細かいところまで書かれていないですが、onlyTouchObjに CrossPlatformInputのコントローラーオブジェクトをアサインしておく感じだと思います)
http://westhillapps.blog.jp/archives/35679696.html

iOSの実機にデプロイする方法はググるとすぐに出て来ます。特に難しくは無いです。
https://unity3d.sakura.ne.jp/unity/unity-for-ios.html
