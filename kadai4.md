課題4　画像のヒストグラム

画像「neko.png」を元画像とする．この画像は縦500×幅750の正方形のディジタルカラー画像である.  
まず，画像を白黒の画像に変換する．

ORG=imread('freemen.png'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;  

表示された画像は図1のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai4-1.png)  
図1　原画像

次にヒストグラムを表示する

imhist(ORG);

結果は図2のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai4-2.png)  
図2　ヒストグラム  
  

まとめ  
MATLABでは，imhist(ORG);のコードを利用することで，ヒストグラムを表示できることを理解した． これにより，画像の輝度を決める際などに，どの値が適しているかを見ることができるのではないかと考えた．
