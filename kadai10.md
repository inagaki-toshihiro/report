課題10 画像のエッジ抽出  

画像「n3ko.png」を元画像とする．この画像はディジタルカラー画像である.  
まず，画像を白黒の画像に変換する．

ORG=imread('freemen.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

表示結果は図1のようになった．


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai10-1.png)  
図1　原画像

次にプレウィット法エッジ抽出を行う．

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  

表示結果は図2のようになった．


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai10-2.png)  
図2　プレウィット法によるエッジ抽出の結果

次にソベル法によるエッジ抽出を行う

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

表示結果は図3のようになった．


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai10-3.png)  
図3　ソベル法によるエッジ抽出の結果

次にキャニー法によるエッジ抽出を行う

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

表示結果は図4のようになった．


![原画像](https://github.com/inagaki-toshihiro/report/blob/master/image/kadai10-4.png)  
図4　キャニー法によるエッジ抽出の結果

まとめ  
以上の結果よりそれぞれのエッジ抽出によりどのような画像になるかを理解した．また，同じエッジ抽出でも差があり，背景の横の線なども抽出できていることなどから，キャニー法を用いたエッジ抽出がもっとも上手く抽出できていると考えられる．
