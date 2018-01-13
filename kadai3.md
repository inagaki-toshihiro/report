課題3　閾値処理

画像「neko.png」を元画像とする．この画像は縦500×幅750の正方形のディジタルカラー画像である.

まず，画像を白黒の画像に変換する．

ORG=imread('freemen.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  

表示結果は図1のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai3-1.png)  
図1　原画像

次に，輝度値が64以上の画素を1，その他を0に変換する．

IMG = ORG > 64;  
imagesc(IMG); colormap(gray); colorbar;

表示結果は図2のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai3-2.png)  
図2　輝度値を64に設定した画像

次に，輝度値が96以上の画素を1，その他を0に変換する．

IMG = ORG > 96;  
imagesc(IMG); colormap(gray); colorbar;

表示結果は図3のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai3-3.png)  
図3　輝度値を96に設定した画像

次に，輝度値が128以上の画素を1，その他を0に変換する．

IMG = ORG > 128;  
imagesc(IMG); colormap(gray); colorbar;  

表示結果は図4のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai3-4.png)  
図4　輝度値を128に設定した画像

次に，輝度値が192以上の画素を1，その他を0に変換する．

IMG = ORG > 192;
imagesc(IMG); colormap(gray); colorbar;

表示結果は図5のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai3-5.png)  
図5　輝度値を192に設定した画像

まとめ  
2値化において，設定する輝度値を変えることによって，次第に画像の黒い範囲が増えていることがわかる．
画像の2値化を行った際に，設定する輝度によって画像の見やすさが変化することを念頭に置き，設定しなければ画像の見やすさが変化してしまうと考えた．
