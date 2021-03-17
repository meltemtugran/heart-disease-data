# heart-disease-data
Projenin konusu :  Makine Öğrenimi Algoritmalarıyla Kalp Hastalığını Tahmin Etme
Sınıflandırma projesi
Neler yaptık?
1-Veri analizi ile verideki eğilimleri ve korelasyonlarla incelendi. Kalp hastalığı teşhisinde Hangi özelliklerin en önemli olduğu belirlendi.
2-Model kısmı: Birden fazla sınıflandırma modeli  (Logistic Regression, K-NN (k-Nearest Neighbors), SVM (Support Vector Machine), Naives Bayes Classifier, Decision Trees, Random Forest.) kullanıldı.En yüksek doğruluk oranı  baz alındı.

VERİ: kaggle dan aldığımız bir veri seti. Veri setimizde kalp krizi tanısı konmuş  hasta ve sağlıklı 303  kişinin verilerinden  var.
Veri seti 303 satır 14 sütun.14 sütun içinde 13 nitelik ve 1 çıktı var.
Veri setinde 3 tip data var.

Continous:ölçülebilen nicel veriler(nümerik):age,trestbps(istirahat durumundaki kan basıncı), kolestrol,thalac(max nabız ),oldpeak(egzersize bağlı sp depresyonu),
Ordinal:sıra ile kategorik değişkenler(0,1,2,3) :cp(göğüs ağrısı şiddeti),restecg(ekg sonuçları ),slope(st segmentinin eğimi),ca(ana damar sayısı), thal(stres durumu )
Binary:iki olası durum olan atalar(0,1) :   Cinsiyet, fbs(açlık kan basıncı,  0=120 ve 120 den  küçük,  1= 120 den büyük) , Exang(egzersize bağlı anjin 0=yok 1=var) , 

 
Exployarty   data     analysis
Korelasyon matrisi amacı:bağımlı değişkenlerle bağımsız değişkenler arasındaki ilişkinin gücünü göstrerir.
Sayıların değeri:ilişkinin gücünü. 
Korelasyon matrisinde sayılar -1 ile +1 arasına değerler alır.
Sayı pozitif veya negatif yönden 0’a ne kadar yaklaşırsa  çıktı ile arasındaki ilişki azalır , kalp hastalığı olma durumu o kadar azalır.
Sayı ne kadar 0 ‘dan uzaklaşırsa (her iki yön için de) çıktı ile arasındaki ilişki artar.

Sayının işareti ise ilişkinin türünü gösterir.
İşaretler ne anlama geliyor?
Negatif korelasyon:değişkenlerin bir artarken diğeri azalıyorsa.ters orantı
Ör:(-0.39)CA(ana damar sayısı arttıkça) ↑ kalp hastası olmadurumu ↓
Pozitif korelsyon : değişkenlerin birlikte atma durumu. Doğru orantı
Ör: (0.43)CP(ağrı şiddeti arttıkça)↑   kalp hastası olma durumu  ↓



Machine Learning + Predictive Analytics
atamalar: 13 özellik, 1 sonuç
Eğitim seti ve test setinin ayrılması: %20 test seti
Normalleştirme, modellerin daha ‘rahat’ çalışması için


Modeling/Training

Model denemeleri, 6 model
	Lojistik regresyon
Lineer regresyon (-∞, +∞) arasında sonuçlar verir, lojistik regresyon ile bu sonucu (0,1) arasında indirgeyerek sınıflandırma problemini çözebiliriz(sigmoid). Verilen özellikler için sonuç 0.8 ise, 1 ile tanımlandırılan sınıfa dahil olma olasılığı %80. 
“Lojistik regresyonda parametreler Maximum Likelihood (MLE) yöntemiyle hesaplanıyor. MLE yönteminin amacı sonsuz parametre havuzundan veri setinin görülme olasılığını maksimize eden en iyi parametreleri seçmek.”
	K-NN (K-Nearest Neighbors)
Model 2, verilen özelliklerin, eğitim setinde benzeme oranının en yüksek olduğu özelliklere göre yorumlar.
	SVM (Support Vector Machine)
Destek Vektör Makineleri, girdileri grafik üzerinden yorumlayarak 0 ve 1 değerlerine dahil olan setleri birbirinden ayırmak için doğrusal veya doğrusal olmayan yardımcı vektörler çizer. Çizilen vektörün bir tarafında kalan (sağ/sol/üst/alt/iç/dış vb.) 0, diğer tarafındaki 1 olur.
	Naives Bayes Classifier
Bu modelde her özellik birbirinden bağımsız olarak kabul edilir.
P(A ┤|  B)=(P(B ┤|  A) .  P(A))/(P(B))
Sonuç olasılığını bulmak. Her bir veri için sonuç teker teker hesaplanarak, ortalama olasılık elde edilir.
	Decision Trees
Karar Ağaçları modeli, çalışma alanlarını birbirinden tekrar tekrar ayırarak, entropiyi(safsızlık ölçütü) en düşük seviyeye indirirerek, bir ağaç oluşturur. Yeni girilen değeri sınıflandırma kararı verirken de bu ağacı kullanır.
“Bilgi kazanımına dayalı olarak (verimli bir şekilde) bölme, karar ağacı modelinin anahtarıdır.”
Basit karar verme adımları uygulanarak, büyük miktarlardaki kayıtları, çok küçük kayıt gruplarına bölerek kullanılan bir yapıdır.



	Random Forest
Rastgele(Tesadüfi) Orman modeli, kolektif/topluluk öğrenme yöntemi. Model, eğitim setindeki özelliklerin alt kümelerinden rastgele karar ağaçları oluşturur(alt kümeler çakışabilir). Son kararı vermeden önce oluşturduğu ağaçlardan aldığı oyları kullanır. Oylamada ağırlık kavramı kullanılabilir. Bu kavram ile hata oranı fazla olan ağaçların oyları için düşük, hata oranı az olan ağaçlar için yüksek ağırlık verilir ve sonuca olan etkisi belirlenir.
Bu modellere göre elimizdeki en iyi sonuç Rastgele(Tesadüfi) Orman modeline ait.
Making the Confusion Matrix
Hata/Karışıklık Matrisi
[■(X1&Y1@Y2&X2)]
X1 – Gerçek 1 sayısı
Y1 - yanlış yapılan 1 tahmini sayısı
Y2 yanlış yapılan 0 tahmini sayısı
X2 – Gerçek 0 sayısı
Accuracy=(X1+X2)/(X1+X2+Y1+Y2)
Bizim hata matrisimiz:
[■(21&9@3&28)]
Accuracy=(21+28)/(21+28+9+3)=49/61≌0.80
Importance of Features

