# MDPlayer
VGMPlayer(メガドライブ音源チップなどのエミュレーションによる演奏ツール)  
  
[概要]  
  このツールは、鍵盤表示を行いながらVGMファイルの再生を行います。  
  (NRDファイルにも対応。)  
  
[注意]  
  再生時の音量に注意してください。バグによる雑音が大音量で再生される場合もあります。  
  (特に再生したことのないファイルを試す場合や、プログラムを更新した場合。)  
  
[対応フォーマット]  
  .VGM (所謂vgmファイル)  
  .VGZ (vgmファイルをgzipしたもの)  
  .NRD (NRTDRV)  
  
[機能、特徴]  
  ・現在、以下の主にメガドライブ系音源チップのエミュレーションによる再生が可能です。  
    AY8910 , YM2612 , SN76489 , RF5C164 , PWM , C140 , OKIM6258 , OKIM6295 , SEGAPCM , YM2151 , YM2203 , YM2413 , YM2608 , YM2610/B  
  
  ・現在、以下の鍵盤表示が可能です。  
    AY8910 , YM2612 , SN76489 , RF5C164 , C140 , SEGAPCM , YM2151 , YM2203 , YM2608 , YM2610/B  
  
  ・C#で作成されています。  
  
  ・VGMPlayのソースを参考、一部移植しています。  
  
  ・FMGenのソースを参考、移植しています。  
  
  ・SCCIを利用して本物のYM2612,SN76489,YM2608,YM2151から再生が可能です。  
  
  ・ボタンは以下の順に並んでいます。  
    設定、停止、一時停止、フェードアウト、前の曲、1/4速再生、再生、4倍速再生、次の曲、  
    プレイモード、ファイルを開く、プレイリスト、  
    情報パネル表示、ミキサーパネル表示、パネルリスト表示、表示倍率変更  
  
  ・チャンネル(鍵盤)を左クリックすることでマスクさせることができます。  
    右クリックすると全チャンネルのマスクを解除します。  
  
  ・音色パラメーターを左クリックするとクリップボードに音色パラメーターをテキストとしてコピーします。  
  パラメーターの形式はオプション設定から変更可能です。  
    FMP7 , MDX , MUSIC LALF , NRTDRV , MML2VGM , .TFIに対応しており、.TFIを選んだ場合はクリップボードの代わりにファイルに出力します。  
  
  ・出来は今一歩ですが、YM2612 , YM2151 の演奏データをMIDIファイルとして出力が可能です。  
  VOPMexを使用すれば、FM音源の音色情報も反映されることが可能です。  
  (VOPMではなく、VOPMexです。;-P )  
  
  ・PCMデータをダンプすることができます。SEGAPCMの場合のみWAVで出力します。  
  
  
[必要な動作環境]  
  ・恐らく、WindowsVista(32bit)以降のOS。64ビット環境では未検証。  
  XPでは動作しません。  
  ・.NET Framework4.5/4.5.2をインストールしている必要あり。  
  ・Visual Studio 2012 更新プログラム 4 の Visual C++ 再頒布可能パッケージ をインストールしている必要あり。  
  ・Microsoft Visual C++ 2015 Redistributable(x86) - 14.0.23026をインストールしている必要あり。  
  ・音声を再生できるオーディオデバイスが必須。  
  ・もしあれば、SPFM Light＋YM2612＋YM2608＋YM2151  
  ・YM2608のエミュレーション時、リズム音を鳴らすために以下の音声ファイルが必要です。  
      バスドラム      2608_BD.WAV  
      ハイハット      2608_HH.WAV  
      リムショット    2608_RIM.WAV  
      スネアドラム    2608_SD.WAV  
      タムタム        2608_TOM.WAV  
      トップシンバル  2608_TOP.WAV  
      (44.1KHz 16bitPCM モノラル 無圧縮Microsoft WAVE形式ファイル)  
  
[SpecialThanks]  
  本ツールは以下の方々にお世話になっております。また以下のソフトウェア、ウェブページを参考、使用しています。  
  本当にありがとうございます。  
  
 ・ラエル さん  
 ・とぼけがお さん  
 ・HI-RO さん  
 ・餓死3 さん  
 ・おやぢぴぴ さん  
 ・osoumen さん  
 ・なると さん  
 ・hex125 さん  
  
 ・Visual Studio Community 2015  
 ・MinGW/msys  
 ・SGDK  
 ・VGM Player  
 ・Git  
 ・SourceTree  
 ・さくらエディター  
 ・VOPMex  
 ・NRTDRV  
 ・hoot  
 ・ASLPLAY  
  
 ・SMS Power!  
 ・DOBON.NET  
 ・Wikipedia  
  
[同期のすゝめ]  
  ・SCCIとエミュレーション(以下EMUと略す)による音を同期させるのにはコツがいります。  
  環境にもよるので何が正解かはわからないのですが、私の環境での調整手順を紹介します。  
  
  １．まず、[出力]タブから音声の出力に使用するデバイスを選びます。  
  おすすめはWasapiOutで共有を選ぶ、又はASIOを選ぶパターンです。  
  
  ２．遅延時間は50msか100msを選びます。ここで一度[OK]を押してEMUのみを使用する曲を再生し  
  音がざらざらしたりプチプチといったノイズが混ざらないことを確認します。  
  (もし綺麗に再生されない場合は遅延時間をひとつ大きく設定します。)  
  
  ３．[音源]タブからYM2612のSCCIを選択し使用するモジュールを選択します。  
  チェックボックスは「Waitシグナル発信」と「PCMだけエミュレーションする」にチェックを入れてください。  
  「Waitシグナル発信」を行うとSCCIのテンポが安定するようです。  
  しかし「そのWait値を2倍」にチェックするとPCMの音質は上がりますがテンポが乱れる傾向があります。  
  
  ４．遅延演奏のグループはとりあえずSCCIもEMUも0msを設定し「日和見モード」にはチェックをいれてください。  
  「日和見モード」は、例えば演奏中に大きな負荷がかかり、SCCIの再生とEMUの再生が大きくずれた場合に  
  SCCIの再生スピードを調整してズレを軽減させる機能です。但し、遅延演奏で設定した(意図した)ズレは保ち続けます。  
  
  ５．SCCIとEMUの両方が使用されている曲を再生し、どちらが先に鳴っているか注意深く確認します。  
  SCCIとEMUのうち先に演奏されている方の遅延演奏時間を増やし曲再生を行い確認します。  
  
  ６．５の手順をズレがなくなるまで繰り返せば同期作業は完了です。楽しんで！  
  

