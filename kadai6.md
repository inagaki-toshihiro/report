課題6　画像の2値化

標準画像「neko.png」を元画像とする．この画像はディジタルカラー画像である.  
まず，画像を白黒の画像に変換する．

ORG=imread('neko.png'); % 原画像の入力  
ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

表示結果は図1のようになる．

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai6-1.png)  
図1　原画像

次に輝度値を128に設定した場合の2値化を行う

IMG = ORG>128; % 128による二値化

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai6-2.png)  
図2　128による二値化の画像

最後にディザ法による2値化を行う

IMG = dither(ORG); % ディザ法による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai6-3.png)  
図3　ディザ法による2値化の画像

まとめ  
以上の結果より輝度値128による二値化とディザ法による二値化を比較し，同じ二値化でもディザ法の方がより元の画像に近く，形が分かりやすいと感じた．また，ディザ法がどのようなものであり，人間の錯覚などを利用していると理解した．
