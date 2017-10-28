# このソフトウェアについて

純正律で長音階と短音階の構成音を各キーのときで算出した（手抜き）。

* 他の音階は算出できない
* 各キーは固定周波数から算出する（超適当な値）
* 音階以外の音は算出できない

純正律はわからないことだらけ。ネットで調査した比を固定入力し計算しただけ。根拠もよくわかっていない。

# 対象ファイル名

ファイル名|説明
----------|----
playJustIntonation2.py|純正律の長音階と短音階の構成音を各キーのときで算出して音声ファイル出力する
MusicTheory/temperament/JustIntonation.py|純正律

# 実行

```sh
$ python playJustIntonation2.py 
========== Major ==========
key:C  [256, 288.0, 320.0, 341.3333333333333, 384.0, 426.6666666666667, 480.0, 512]
key:C# [272, 306.0, 340.0, 362.66666666666663, 408.0, 453.33333333333337, 510.0, 544]
key:D  [288, 324.0, 360.0, 384.0, 432.0, 480.0, 540.0, 576]
key:D# [308, 346.5, 385.0, 410.66666666666663, 462.0, 513.3333333333334, 577.5, 616]
key:E  [326, 366.75, 407.5, 434.66666666666663, 489.0, 543.3333333333334, 611.25, 652]
key:F  [348, 391.5, 435.0, 464.0, 522.0, 580.0, 652.5, 696]
key:F# [370, 416.25, 462.5, 493.3333333333333, 555.0, 616.6666666666667, 693.75, 740]
key:G  [392, 441.0, 490.0, 522.6666666666666, 588.0, 653.3333333333334, 735.0, 784]
key:G# [414, 465.75, 517.5, 552.0, 621.0, 690.0, 776.25, 828]
key:A  [440, 495.0, 550.0, 586.6666666666666, 660.0, 733.3333333333334, 825.0, 880]
key:A# [466, 524.25, 582.5, 621.3333333333333, 699.0, 776.6666666666667, 873.75, 932]
key:B  [492, 553.5, 615.0, 656.0, 738.0, 820.0, 922.5, 984]
========== Minor ==========
key:C  [256, 288.0, 307.2, 341.3333333333333, 384.0, 409.6, 460.8, 512]
key:C# [272, 306.0, 326.4, 362.66666666666663, 408.0, 435.20000000000005, 489.6, 544]
key:D  [288, 324.0, 345.59999999999997, 384.0, 432.0, 460.8, 518.4, 576]
key:D# [308, 346.5, 369.59999999999997, 410.66666666666663, 462.0, 492.8, 554.4, 616]
key:E  [326, 366.75, 391.2, 434.66666666666663, 489.0, 521.6, 586.8000000000001, 652]
key:F  [348, 391.5, 417.59999999999997, 464.0, 522.0, 556.8000000000001, 626.4, 696]
key:F# [370, 416.25, 444.0, 493.3333333333333, 555.0, 592.0, 666.0, 740]
key:G  [392, 441.0, 470.4, 522.6666666666666, 588.0, 627.2, 705.6, 784]
key:G# [414, 465.75, 496.79999999999995, 552.0, 621.0, 662.4000000000001, 745.2, 828]
key:A  [440, 495.0, 528.0, 586.6666666666666, 660.0, 704.0, 792.0, 880]
key:A# [466, 524.25, 559.1999999999999, 621.3333333333333, 699.0, 745.6, 838.8000000000001, 932]
key:B  [492, 553.5, 590.4, 656.0, 738.0, 787.2, 885.6, 984]
```

`res/`配下に音声ファイルが出力される。

# 課題

* 和音パターンを調査し網羅したい
* 12平均律以外の音律でも構成音を算出したいが……
    * 純正律における中間の5音も算出したい。計算方法がよくわからない
* 純正律で綺麗な和音になる主要三和音とそれ以外の音痴な副和音を聴き比べてみたい
* ソースコードが整理できていない
    * 音楽理論がわからず、どうまとめていいのかもわからない

# 開発環境

* Linux Mint 17.3 MATE 32bit
* [libav](http://ytyaru.hatenablog.com/entry/2018/08/24/000000)
    * [各コーデック](http://ytyaru.hatenablog.com/entry/2018/08/23/000000)
* [pyenv](https://github.com/pylangstudy/201705/blob/master/27/Python%E5%AD%A6%E7%BF%92%E7%92%B0%E5%A2%83%E3%82%92%E7%94%A8%E6%84%8F%E3%81%99%E3%82%8B.md) 1.0.10
    * Python 3.6.1
        * [pydub](http://ytyaru.hatenablog.com/entry/2018/08/25/000000)
        * [PyAudio](http://ytyaru.hatenablog.com/entry/2018/07/27/000000) 0.2.11
            * [ALSA lib pcm_dmix.c:1022:(snd_pcm_dmix_open) unable to open slave](http://ytyaru.hatenablog.com/entry/2018/07/29/000000)
        * [matplotlib](http://ytyaru.hatenablog.com/entry/2018/07/22/000000)
            * [matplotlibでのグラフ表示を諦めた](http://ytyaru.hatenablog.com/entry/2018/08/05/000000)

# 参考

感謝。

## 440Hz, 432Hz

* http://tabi-labo.com/156689/music-a432

## 和音の生成

* http://ism1000ch.hatenablog.com/entry/2013/11/15/182442
* https://ja.wikipedia.org/wiki/%E4%B8%89%E5%92%8C%E9%9F%B3
* https://ja.wikipedia.org/wiki/%E3%83%91%E3%83%AF%E3%83%BC%E3%82%B3%E3%83%BC%E3%83%89

## 音名

* https://ja.wikipedia.org/wiki/%E9%9F%B3%E5%90%8D%E3%83%BB%E9%9A%8E%E5%90%8D%E8%A1%A8%E8%A8%98

## 音階

* https://ja.wikipedia.org/wiki/%E9%9F%B3%E9%9A%8E

### 五度圏

* http://dn-voice.info/music-theory/godoken/

## 音高の算出

* http://www.asahi-net.or.jp/~HB9T-KTD/music/Japan/Research/DTM/freq_map.html
* http://www.nihongo.com/aaa/chigaku/suugaku/pythagoras.htm

## サイン波のスピーカ再生

* http://www.non-fiction.jp/2015/08/17/sin_wave/
* http://aidiary.hatenablog.com/entry/20110607/1307449007
* http://ism1000ch.hatenablog.com/entry/2013/11/15/182442

# ライセンス

このソフトウェアはCC0ライセンスである。

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")](http://creativecommons.org/publicdomain/zero/1.0/deed.ja)

Library|License|Copyright
-------|-------|---------
[pydub](https://github.com/jiaaro/pydub)|[MIT](https://github.com/jiaaro/pydub/blob/master/LICENSE)|[Copyright (c) 2011 James Robert, http://jiaaro.com](https://github.com/jiaaro/pydub/blob/master/LICENSE)
[pygame](http://www.pygame.org/)|[LGPL](https://www.pygame.org/docs/)|[pygame](http://www.pygame.org/)

