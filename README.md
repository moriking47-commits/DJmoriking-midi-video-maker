# moriking MIDI Video Maker

MIDIとミックス音源（WAV）を入れるだけで、ピアノロールとキャラクターが音に合わせて動く動画を作れるブラウザツールです。
#深夜の2時間DTM の投稿用に作りました。インストール不要・無料・ファイルは自分のPCの中だけで処理されます。

▶ **使う：https://moriking47-commits.github.io/DJmoriking-midi-video-maker/**

## できること
- MIDIのピアノロール表示（鳴った瞬間に光る・波紋が出る）。色は「音の高さ」か「トラック」で
- ドラム／パーカッションと重複レイヤーのトラックを自動でオフ
- 音源の最初の音を検出して、ノートと音の頭を自動で合わせる（½拍・50ms単位の微調整ボタンつき）
- DJ morikingが拍に合わせてうなずき、キックで跳ねる
- 音に反応して動き回るキャラ：ヘッドホン猫、UFO、宇宙人、火を吹く怪獣、とぼとぼ犬、横歩きカニ、ローライダー（各0〜3体）
- 自分の画像をキャラとして追加（歩く／地面を往復／空を飛ぶ／その場でノる）
- ハッシュタグ＋お題の見出し、BAR・BPM表示、クレジット
- 16:9／9:16（Shorts）／1:1、1080p／720p
- 最後の余白（残響を残して終わる）
- MP4（またはWebM）で書き出し

## 使い方
1. DAWからMIDI（SMF）と、小節1から書き出したWAVを用意
2. ツールにMIDIとWAVを入れる
3. ▶プレビューで確認、ズレていたら「½拍早く」などで調整
4. 開始・終了を決めて「● 動画を書き出す」→「動画を保存」

※書き出しは実時間で再生しながら録画します。終わるまでタブを前面にしておいてください。
※Chrome／Safariの最新版を推奨。

## 改造・進化、大歓迎
コードは `index.html` 1ファイルだけです（ライブラリなし、Canvas＋Web Audio API＋MediaRecorder）。
キャラを増やしたり、演出を足したり、自由にフォークして進化させてください。
「こんなの作った」と #深夜の2時間DTM や @DJmoriking で教えてもらえるとうれしいです。

- キャラの描画：`drawUFO` / `drawKaiju` / `drawCrab` などの関数
- 動きのパターン：`plan()`（テンポから決まるので、プレビューと書き出しが同じ動きになります）
- 音への反応：`analyse()`（低音のキック検出と音量）

## ライセンス
コードは MIT License です（LICENSE を参照）。
ただし、DJ morikingのキャラクター画像（`index.html` 内に埋め込まれている標準のDJ画像）は著作物としてDJ morikingに帰属し、MITの対象外です。フォークして配布する場合は、ご自身の画像に差し替えてください。

---

**English:** A browser tool that turns a MIDI file + your mix (WAV) into a piano-roll music video with characters that dance to the beat. Single `index.html`, no build step. Code is MIT licensed; the bundled DJ moriking character image is not — please replace it if you redistribute.

Made by **DJ moriking** (X: @DJmoriking)
