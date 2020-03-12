# pytorch_chatbot
このチャットボットは、[PyTorch公式チュートリアル](https://pytorch.org/tutorials/beginner/chatbot_tutorial.html)のコードをアレンジしたものです

## 使用技術
言語: Python  
ライブラリ: PyTorch→機械学習のため sentencepiece→文章を分かち書きに  
4層GRU+Attention

## 動機
Udemyにチャットボットの講座があり、昔やったメタルギアソリッドピースウォーカーに出てくる喋るAIを思い出して興味を持ったから  
また、機械と話せると単純に遊んでくれる人たちが驚いてくれると思ったから

## 仕様
会話ができる  
個人的に良くないと思われる言葉に関してはNGテーブルでモザイクかけてから出力している  
(5chは差別的な言葉が飛び交う場所なので、チャットボットが相手に刺さる文章を生成する可能性を考慮した)  
「ほな」または「グッバイ」と打ち込まれた場合、会話を終了する

## なぜPyTorch？
kerasはあまりに簡単すぎて、自分が今後機械学習の理論に関心を持たなくなる可能性が嫌だったため  
かといって、TensorFlowを触れるだけの数学力もないと感じたため。  
また、PyTorchでチャットボットを作成している人があまりいなかったため。

##苦労した点
#PyTorch
そもそもプログラミング自体素人の状態で始めたので、PyTorchを理解するだけでもかなり時間がかかった  
現在でもざっくりとした動きは理解できてはいるものの、細かい部分はまだまだなので、QiitaやUdemy等で理解できるようにしていきたい

## 今後改善したい点
#理論や機械学習コードの理解
今回はPyTorch公式のチュートリアルを日本語処理用にアレンジしたものを使った。  
パラメータの理解はできたが、正直全てを理解できているわけではないので、モデルの構築については、完璧にしておきたい  

###  数学の理解
この作品を通して数学の重要さがわかった  
内積、微積、テンソル、行列等自分の数学的素養のなさを思い知った  
こちらに関しては、現在基本情報技術者試験に向けた勉強や、Udemyで講座をとったりして学習中

### GPUのメモリ節約
隠れ層を2000にしたところメモリを溢れさせてしまった。  
調べたが最終的には解決しなかったので、stackoverflowやteratailを利用して解決したい

### sentencepieceのモデル変更
今回はwikipediaで学習したモデルを使用して分割したが、wikipediaの堅い文章は最も崩れた口語であるの5chの言語処理には不向きなのではないかと思う  
口語に近い文体の分割モデルを作ることができれば、より精度の高い文章生成につながるのではないかと思う。

### LINEボット化
やはり作ったものをいろんな人に触ってもらいたいと思っているので、webアプリ化する予定
LINEを選んだ理由としては、もはや使ってない人はいないというレベルで浸透しているからというのが最も大きい  
アプリを使用するためのハードルが低いため、より多くの人々が使ってくれると考えている
