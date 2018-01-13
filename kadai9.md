課題9　メディアンフィルタと先鋭化

標準画像「neko.png」を元画像とする．この画像ディジタルカラー画像である.  
まず，画像を白黒の画像に変換する．

ORG=imread('freemen.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

表示結果は図1のようになった．

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai9-1.png)  
図1　原画像

次にこの画像にノイズを乗せる

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

表示結果は図2のようになった．

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai9-2.png)  
図2　ノイズを添付した画像

次に平滑化フィルタで雑音除去を使い，ノイズを減らす  

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

表示結果は図3のようになった.

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai9-3.png)  
図3　平滑化フィルタで雑音除去を行った画像

また，メディアンフィルタを利用してノイズを減らす

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

表示結果は図4のようになった.

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai9-4.png)  
図4　メディアンフィルタで雑音除去を行った画像

自分でフィルタを設計すると図5のようになった．

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

<div align="center">
![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai9-5.png)  
図5　フィルタを設計した画像

まとめ  
以上のそれぞれ結果を比較し，メディアンフィルタによる雑音除去の性能が一番よく，雑音が綺麗に除去されるということを理解した．また，設計したフィルタでは全体的に灰色っぽくなってしまったが雑音は目立たなくなっていることを理解した．
