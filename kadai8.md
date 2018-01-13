課題8　ラベリング

標準画像「neko.png」を元画像とする．この画像はディジタルカラー画像である.  
まず，画像を白黒の画像に変換する．

ORG=imread('freemen.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

表示結果は図1のようになった．


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai8-1.png)  
図1　原画像

次に閾値128で二値化する．

IMG = ORG > 128; % 閾値128で二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

表示結果は図2のようになった．


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai8-2.png)  
図2　閾値128で二値化した画像

これを，colormap(jet)で調べると，図3のようになる.

IMG = bwlabeln(IMG);  
imagesc(IMG); colormap(jet); colorbar; % 画像の表示


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai8-3.png)  
図3　色調を分けた画像

まとめ  
ラベルは色によってつけられている.同色の部分が連結成分であることを理解した.
