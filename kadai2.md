課題2:階調数と疑似輪郭

画像「neko.png」を元画像とする．この画像は縦500×幅750の正方形のディジタルカラー画像である.
まず，画像を白黒の画像に変換する．

ORG=imread('freemen.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;  
imagesc(ORG); axis image; % 画像の表示  

によって表示された原画像は図1のようになった．

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai2-1.png?)  
画像1　原画像

この画像を2値化すると図2のようになる．

IMG = ORG>128; imagesc(IMG); colormap(gray); colorbar; axis image;

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai2-2.png)  
画像2　2値化した画像

この画像を4値化すると図3のようになる．

IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
imagesc(IMG); colormap(gray); colorbar; axis image;  

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai2-3.png)  
画像3　4値化した画像

この画像を8値化すると図4のようになる．

IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;  
imagesc(IMG); colormap(gray); colorbar; axis image;  

![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai2-4.png)  
画像4　8値化した画像

まとめ  
今回の課題によって、2階調、4階調、8階調と段々と増やしていくことによって、原画像に近づいていき、より鮮やかな画像になると分かった。
