# Music Generator

画像を読み込んで, その画素情報から音楽を自動生成します.

Demo: http://nodaguti.usamimi.info/test/MusicGenerator/MusicGenerator.html

:warning: 古い [Audio Data API](https://developer.mozilla.org/en-US/docs/Archive/Mozilla/Introducing_the_Audio_API_Extension)
を使って作られたため, Firefox 28 **以下** でしか動作しません.

## 仕組み

画像を左上から右下に向かって走査し, 各画素から RGBA の情報を取り出して指定された数式に基づき以下の値を決定し, 音を作ります.

- Frequency (default: `Math.floor((R+G+B) / 3) + 100`)
- Sound Length (default: `(R+G)/1000`)
- Envelope (default: 0)
- Type of wave: Sin, Square, Triangle, Sawtooth (default: Sin wave)
