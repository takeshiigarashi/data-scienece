<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.min.js">
</script>
<script type="text/x-mathjax-config">
 MathJax.Hub.Config({
 tex2jax: {
 inlineMath: [['$', '$'] ],
 displayMath: [ ['$$','$$'], ["\\[","\\]"] ]
 }
 });
</script>

# 4.8 生成AI

テキスト以外にも、画像、動画、音声などがあることに注意（つい、ChatGPTの大規模言語モデルによるテキスト生成を思い浮かべるが）

## 生成AIの特徴

従来のAI（機械学習）は、回帰、分類といった、学習データから特徴やパターンを見つけ、新しいデータに対する予測を行う、というもの。出力されるのは予測値であって、新しい形でデータを作り出すことではない。

生成AIも、値の予測をしている。GPTは単語を逐次的に予測することで文を完成させる。画像生成AIであれば、画像のピクセルの値を予測している。

生成AIは、実質的に予測を行うものの、新しいデータを生成することを目的としているという点で、従来の機械学習とは異なるといえる。

主なサービス

- 画像生成AI
  - Style-GAN(NVIDIA)
  - DALL-E (OpenAI)
  - Imagen (Google)
  - Stable Diffusion (Statility AI)
  - Midjourney (Midjourney)
- 音声生成AI
  - Jukebox (OpenAI)
  - MusicLM (Google)
- 大規模言語処理AI
  - GPT, ChatGPT (OpenAI)
  - PaLM 2, Bard, Gemini (Google)
  - LLaMA (Meta AI)

## 生成AIに命令を与える

プロンプト、プロンプトエンジニアリング

- Zero-shot prompting
- Few-shot prompting
- Chain-of-Thought prompting
- 知識生成prompting ... プロンプトの一部に知識や情報を組み込む
- 方向性刺激prompting ... 正しい方向に誘導するためのヒントを与える

## 文章生成AI

ChatGPTなど

ChatGPTのファインチューニングは以下の３つのステップで行われる

- 教師あり学習
- 報酬モデルの学習
- 強化学習

RLHF (Reinforcement Learning from Human Feedback)。Reinforcement Learningは強化学習のこと。RLHFは人間のフィードバックに基づいた強化学習。

## 画像生成AI

**変分オートエンコーダー(VAE: Variational Auto-Encoder)** は生成モデルの一種。入力データの背後にある潜在的な構造やパターンを学習し、新しいデータを生成するために使われる。エンコーダーとデコーダーの２つのネットワークから構成され、エンコーダーは入力データを潜在空間と呼ばれる低次元の潜在変数に変換する。デコーダーは、潜在変数から元のデータ空間に近いデータを再構成する。サンプリングされた潜在変数から元データに近い新しいデータを生成する役割も果たす。

**敵対的生成ネットワーク(GAN: Generative Adversarial Network)** は、データを生成するための深層学習モデルで、２つのニューラルネットワークが互いに競い合いながら学習する仕組みを持っている。

**Diffusion Model**は、、「データをノイズで破壊し、元のデータに復元する」という手法で生成を行う。学習時は、データにノイズをジョジョに加えていく「拡散過程」と、その逆の「生成過程」を学習することで、ノイズからリアルなデータを精製できるようになる。初期状態のノイズから段階的にノイズを除去することで、最終的にはデータを精製するという手順。

画像生成の分野ではDiffusion Modelが急速に採用されつつある。GANやVAEよりも精製品質が高いと評価されている。