課題3　ダイナミックレンジの拡大

標準画像「neko.png」を元画像とする．この画像はディジタルカラー画像である.  
まず，画像を白黒の画像に変換する．

ORG=imread('freemen.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

表示結果は図1のようになった．


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai7-1.png)  
図1　原画像

濃度ヒストグラムは図2のようになった．

imhist(ORG); % 濃度ヒストグラムを生成、表示


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai7-2.png)  
図2　濃度ヒストグラム

これを平衡化すると図3のようになる．また，濃度ヒストグラムは図4のようになる．

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  
ORG = uint8(ORG);  
imhist(ORG); % 濃度ヒストグラムを生成、表示  


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai7-3.png)  
図3　平衡化した画像


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai7-4.png)  
図4　平衡化した画像のヒストグラム

まとめ  
関数unit8は8ビット符号なし整数への変換を行っている．これはimhist関数はにおける引数がsingle，double，int8，int16，int32，uint8，uint16，uint32，logicalのデータ型でなければならない為だと考えられる．
