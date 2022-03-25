# tutorial-9.1-9.2-9.3


 TUTORIAL 9.1: IMAGE HISTOGRAMS
 
 
##Question 1 Explain the drastic change of the Y-axis values when the histogram is displayed with fewer bins.

Aşağıda görüldüğü gibi 64-bin grafiğinde y eksenindeki değerler 1000'er artarken , 32-bin grafiğindeki y eksenindeki deeğerler 2000'er artmaktadır.Bu da x eksenindeki görüntü aralıklarını etkilemektedir.

![image](https://user-images.githubusercontent.com/49070852/160065985-a092c2c2-e179-4459-a870-ca892a9ce3ec.png)


##Question 2 What does the function numel do?

![image](https://user-images.githubusercontent.com/49070852/160069394-2874f1f4-b860-4d69-a80b-176a16963e81.png)


c_norm=c/ numel(I); I dizisindeki öğe sayısını, c_norm'u, prod(size(I)'ya eşdeğer) döndürür.


##Question 4 How would we change the width of the bars in a bar chart?

barwidth() komut satırı ile mümkündür.

barWidth = handles.slider1.Value; //0 ile 1 arasında kaydırıcı değer alınır,sonrasında bar() komutu ile çağırılır.
bar(x, y, 'BarWidth', barWidth);

##Question 5 Explore the properties of stem charts. How can we make the lines dotted instead of solid?


s = stem(1:10);
s.Color = 'red';



![image](https://user-images.githubusercontent.com/49070852/160072349-481c5306-219b-4783-b013-a286652a0f7a.png)



##Question 6 Alter the axes limits and tick marks to reflect the data being displayed in the stem plot.

Eksen sınırlamaları değişimleri ve kendi yaptığım diğer değişiklikler aşağıdaki gibidir.Bunlar için axis manual,auto,ij ; subplot(2,2,1),subplot(2,2,2); color olarak green i seçtim.


![image](https://user-images.githubusercontent.com/49070852/160073716-c944733f-c02e-4805-bd9a-7841da88522a.png)

![image](https://user-images.githubusercontent.com/49070852/160073768-a602d4f9-fa55-4856-88f6-cded3dd98186.png)

![image](https://user-images.githubusercontent.com/49070852/160074182-ef07f3a9-f428-48ee-9dad-3caba7b754fe.png)


 TUTORIAL 9.2: HISTOGRAM EQUALIZATION AND SPECIFICATION
 
 ##Question 1 Why must we include the second parameter (256) in the histeq function call?
 
 Histogramın yoğunluk görüntüsü,görüntü içindeki ayrık düzey sayısından çok daha küçük olduğunda daha iyi eşleşme sağlar.
 
 ##Question 2 What is the effect of histogram equalization on images with low contrast?
 
 Bu , daha düşük yerel kontrasta sahip alanların daha yüksek bir kontrast kazanmasına izin verir . Histogram eşitleme bunu, görüntü kontrastını azaltmak için kullanılan yüksek yoğunluktaki değerleri etkin bir şekilde yayarak gerçekleştirir.
 
##Question 3 Based on the tire image’s original histogram, what can be said about its overall brightness?

Equalized histogramda parlaklık görüntünün pixellerini 255 olarak değiştiğini veyahut yaklaştığını göstermektedir. göstermektedir.

![image](https://user-images.githubusercontent.com/49070852/160077650-673370da-efa0-45cd-886f-12d2e21fecd8.png)

##Question 4 How did histogram equalization affect the overall image brightness in this case?

Equalized histogramda 0-150 arası değer aralıkları artmış,150-250 arasın değer aralıkları sıklaşmıştır.

##Question 5 Why was there such a loss in image quality after histogram equalization?

![image](https://user-images.githubusercontent.com/49070852/160078457-7b4e7b87-e622-4224-92ce-5d53a4710253.png)





