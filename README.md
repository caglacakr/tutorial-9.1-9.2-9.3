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

Original ve Equalized histogramlarına bakacak olursak 0-75 arası gibi 255 pixel görüntüleri ,0 pixel görüntülere çevirmiştir.Yani teoride, eğer histogram eşitleme fonksiyonu biliniyorsa, orijinal histogram kurtarılabilir. Hesaplama, hesaplama açısından yoğun değildir. Yöntemin bir dezavantajı , gelişigüzel olmasıdır . Kullanılabilir sinyali azaltırken arka plan gürültüsünün kontrastını artırabilir.Aşağıdaki görüntünün sebebi de budur.

![image](https://user-images.githubusercontent.com/49070852/160078457-7b4e7b87-e622-4224-92ce-5d53a4710253.png)

##Question 6 What does the cumsum function do in the previous step?

B = cumsum(A), boyutu 1'e eşit olmayan A'daki ilk dizi boyutunun başlangıcından başlayarak A'nın kümülatif toplamını döndürür.

A bir vektörse, cumsum(A), A'nın öğelerinin kümülatif toplamını içeren bir vektör döndürür.

A bir matrisse, cumsum(A), A'nın her sütunu için kümülatif toplamları içeren bir matris döndürür.

A çok boyutlu bir diziyse, cumsum(A) ilk tek olmayan boyut boyunca hareket eder.


##Question 8 How do the different interpolation methods change the shape of the desired histogram curve?

Aşağıdaki figürlerden ikinci grafik ,birinci grafiğe göre dalgalanmaları çok olan bir grafiktir.(0,0.5) değerini (0,0) değerlerine dönüştürmüştür.


![image](https://user-images.githubusercontent.com/49070852/160097489-1d50c689-0bbf-4e0f-a46a-6185d3ef426f.png)



##Question 10 What does the ClipLimit setting do in the adapthisteq function?

'ClipLimit', özellikle homojen alanlarda görüntünün aşırı doygunluğunu önleyen bir kontrast faktörüdür. Bu alanlar, aynı gri seviye aralığına düşen birçok pikselden dolayı belirli görüntü döşemesinin histogramında yüksek bir tepe noktası ile karakterize edilir. Klip sınırı olmadan, uyarlanabilir histogram eşitleme tekniği, bazı durumlarda orijinal görüntüden daha kötü sonuçlar üretebilir.



 TUTORIAL 9.3: OTHER HISTOGRAM MODIFICATION TECHNIQUES
 
##Question 1 How did the histogram change after the adjustment?

x ekseni 0.3 noktasından 0.4 noktasına kaymıştır.

![image](https://user-images.githubusercontent.com/49070852/160100906-f25aa1a4-4746-4dbb-907f-66993b79eb35.png)

##Question 2 What does the variable bad_values contain?

bad_values = find(I3 > 1);
I3(bad_values) = 1;

Yukarıdaki komut satırına göre gama değeri doğrusal olarak seçilmiştir.

##Question 3 Why does the third plot show such an excessive number of pixels with a value of 1?

constrat değeri 0.5 seçilip fotoğrafa eklenerek pikseli arttırılmıştır.

![image](https://user-images.githubusercontent.com/49070852/160102554-581792fd-f273-448b-aa4b-de79bab4d31d.png)


##Question 4 How did the histogram change after the adjustment?

Değer aralığı x-ekseninde 0.3 ile 0.6 arasından , 0 ile 1 arasına çıkmış ve  görüntüye netlik verilmiştir.

![image](https://user-images.githubusercontent.com/49070852/160103564-07d59a87-a6be-420b-98b9-ceebfc055f87.png)

##Question 5 What is the purpose of using the stretchlim function?

LOW_HIGH = Stretchlim(I), kontrast gerdirme görüntüsü I için kullanılabilecek alt ve üst limitleri belirten iki elemanlı piksel değerleri vektörü olan LOW_HIGH değerini döndürür.
Varsayılan olarak, LOW_HIGH içindeki değerler, tüm piksel değerlerinin en alttaki %1'ini ve en üstteki %1'ini belirtir.
Döndürülen gri değerler, bir görüntünün kontrastını artırmak için imadjust işlevi tarafından kullanılabilir.

##Question 8 What do the above first two statements in the code do?

B = reshape(A,m,n) öğeleri A'dan sütun bazında alınan m'ye n matris B'yi döndürür. A'nın m*n öğesi yoksa bir hata oluşur.

B = reshape(A,m,n,p,...) veya B = reshape(A,[mnp ...]), A ile aynı öğelere sahip ancak m-by- boyutuna sahip olacak şekilde yeniden şekillendirilmiş bir ND dizisi döndürür n-by-p-by-... . Belirtilen boyutların ürünü, m*n*p*..., prod(beden(A)) ile aynı olmalıdır.

B = reshape(A,...,[],...) yer tutucu [] tarafından temsil edilen boyutun uzunluğunu hesaplar, öyle ki boyutların çarpımı prod(size(A)'ya eşittir). prod(size(A)) değeri, belirtilen boyutların çarpımı tarafından eşit olarak bölünebilir olmalıdır. [] öğesinin yalnızca bir oluşumunu kullanabilirsiniz.

B = reshape(A,siz), A ile aynı öğelere sahip ancak yeniden şekillendirilmiş dizinin boyutlarını temsil eden bir vektör olan boyuta yeniden şekillendirilmiş bir N-D dizisi döndürür. prod(siz) miktarı prod(size(A)) ile aynı olmalıdır.

##Question 9 What does the xlabel and ylabel functions do?

xlabel( txt ) geçerli eksenlerin veya bağımsız görselleştirmenin x eksenini etiketler. xlabel komutunun yeniden yayınlanması, eski etiketi yeni etiketle değiştirir. xlabel( target , txt ) etiketi belirtilen hedef nesneye ekler.
ylabel( txt ) geçerli eksenlerin veya bağımsız görselleştirmenin y eksenini etiketler. ylabel komutunun yeniden yayınlanması, yeni etiketin eski etiketin yerini almasına neden olur. ylabel( target , txt ) etiketi belirtilen hedef nesneye ekler.

##Question 10 The transformation function plot displays a gap from 0 to 12 (on the X axis) where there are no points. Why is this so?

Görüntü daraltma işlemi uygulanmıştır.

![image](https://user-images.githubusercontent.com/49070852/160108916-e0878c48-2e01-44b2-911d-767847ddf2f1.png)

