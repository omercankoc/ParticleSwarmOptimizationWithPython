# PSO
# Giriş
Optimizasyon; Verilen amaç için belirli işlem uygularken iyi çözüm elde etme sürecidir. Optimizasyon terminolojisinde her zaman en iyiye ulaşma söz konusudur. Optimizasyon problemleri daha önce matematiksel fonksiyonlarla tanımlanıyordu. Bu tür yöntemlerin esnek olmaması ve dezavantajlarının fazla olması sebebiyle yeni yöntemler geliştirilmeye başlanmıştır. Bu süreçte doğadaki olaylardan esinlenilmiştir. Doğadaki olaylar temel alınarak geliştirilen optimizasyon algoritmaları sezgisel algoritmalar olarak adlandırılmaktadır. Bu algoritmaların en yaygın olanlarından bir tanesi parçacık sürü optimizasyonu algoritmasıdır.

Parçacık Sürü Optimizasyonu; 1995 yılında Dr. Eberhart ve Dr. Kennedy tarafından geliştirilmiş popülasyon temelli sezgisel bir optimizasyon tekniğidir. Kuş ve balık sürülerinin sosyal davranışlarından esinlenilerek geliştirilmiştir.

PSO, Genetik Algoritmalar gibi evrimsel hesaplama teknikleri ile birçok benzerlik gösterir. Sistem rasgele çözümlerden oluşan bir popülasyonla başlatılır ve en iyi çözüm için jenerasyonları güncelleyerek arama yapar. Buna karşın Genetik Algoritmaların tersine, Parçacık Sürü Optimizasyonunda çaprazlama ve mutasyon gibi evrimsel operatörler yoktur. Parçacık Sürü Optimizasyonunda parçacık denilen potansiyel çözümler, mevcut en iyi çözümleri takip ederek problem uzayında gezinirler (uçuş yaparlar).

Genetik Algoritmalar ve Parçacık Sürü Optimizasyonu karşılaştırılması yapılırsa Parçacık Sürü Optimizasyonunun avantajı gerçekleştirilmesi kolay olması ve ayarlanması gereken çok az parametreye sahip olmasıdır. Parçacık Sürü Optimizasyonu birçok alanda başarılı uygulama sahasına sahiptir. Bunlardan bazıları yapay sinir ağları eğitimi, bulanık sistem kontrolü ve Genetik Algoritmaların uygulanabildiği diğer alanlarıdır.

Biyolojik Sistemlerden esinlenilen birçok hesaplama tekniği mevcuttur. Örnek olarak yapay sinir ağları, insan beyninin basitleştirilmiş bir modelidir. Genetik algoritmalar biyolojideki evrimsel süreçlerden esinlenir. Burada ise ele alınan konu biyolojik sistemlerin farklı bir türü olan sosyal sistemlerdir. Özellikle birbiriyle ve çevresiyle etkileşim içinde olan basit bireylerin birliktelik davranışları incelenmektedir. Bu kavram parçacık zekâsı olarak isimlendirilir.

Sayısal zekâ alanında parçacıklardan esinlenen iki popüler metot vardır. Karınca Koloni Optimizasyonu ve Parçacık Sürü Optimizasyonu. Karınca Koloni Optimizasyonu, karıncaların davranışlarından esinlenir ve ayrık optimizasyon problemlerinde birçok başarılı uygulaması vardır.

Parçacık Sürüsü kavramı basitleştirilmiş sosyal sistemin benzetimi olarak oluşturuldu. Asıl amaç bir kuş veya balık sürüsü koreografisinin grafiksel olarak benzetimini yapmaktı. Ancak parçacık sürüsü modelinin bir optimizasyon aracı olarak kullanılabileceği düşünüldü.

# PSO
Parçacık Sürü Optimizasyonunda amaç sürüdeki en iyi konuma sahip parçacığın yerinin tespit edilip diğer parçacıkların da o yöne hareketinin sağlanmasıdır. Parçacıklar bir sonraki konumunu geçmiş tecrübelerine ve sürüdeki en iyi pozisyona sahip bireye dayanarak iyileştirmeyi hedefler.

Daha öncede açıklandığı gibi Parçacık Sürü Optimizasyonu kuş veya balık sürüsünün davranışlarını benzetir. Bir alanda rasgele yiyecek arayan bir kuş grubunun olduğunu ve arama yapılan alanda yalnızca bir parça yiyecek olduğunu varsayalım. Kuşların hiçbiri yiyeceğin nerede olduğunu bilmesin. Fakat her bir iterasyon sonunda yiyeceğin ne kadar uzakta olduğunu bilsinler. Bu durumda en iyi strateji, yiyeceğe en yakın kuşu takip etmektir. Parçacık sürü Optimizasyonu bu senaryoya göre çalışır. Her bir çözüm arama uzayındaki bir kuştur ve bunlar parçacık olarak isimlendirilir. Tüm parçacıkların optimize edilecek uygunluk fonksiyonu tarafından değerlendirilen bir uygunluk değeri ve uçuşlarını yönlendiren hız bilgileri vardır. Parçacıkları problem uzayınca mevcut optimum parçacıkları takip ederek çözüme ulaşırlar.

Parçacık Sürü Optimizasyonu bir grup rasgele üretilmiş çözümle başlatılır ve jenerasyonlar güncellenerek en uygun değer araştırılır. Her iterasyon da her bir parçacık iki “en iyi” değere göre güncellenir. Bunlardan birincisi bir parçacığın o ana kadar bulduğu en iyi uygunluk değeridir. Ayrıca bu değer daha sonra kullanılmak üzere hafızada tutulur ve “pbest” yani parçacığın en iyi değeri olarak isimlendirilir. Diğer en iyi değer ise popülasyondaki herhangi bir parçacık tarafından o ana kadar elde edilmiş en iyi uygunluk değerine sahip çözümdür. Bu değer popülasyon için global en iyi değerdir ve “gbest” olarak isimlendirilir.

D adet parametreden oluşan n adet parçacık için popülasyon matrisi aşağıdaki gibidir.
x=[a11 a12 a1n; a21 a22 a2n; ... ... ...; an1 an2 ann]
Matrise göre i. parçacık xi=[xi1,xi2,… ,xin] olup local en iyi çözüm pbesti=[pi1,pi2,…,pin], global en iyi çözüm gbesti=[p1,p2,… ,pn] şeklinde gösterilir ve i. parçacığın her konumdaki değişim miktarını gösteren hız vektörü vi=[vi1,vi2,… ,vin] olarak ifade edilir. Bu iki en iyi değer bulunduktan sonra parçacık sırasını ve konumunu sırasıyla aşağıdaki denkleme göre günceller.

    Vid = W * Vid + c1 * rand1 * (Pid-Xid) + c2 *rand2 * (Pgd - Xid) 
    Xid = Xid - Vid

Burada rand (0,1) arasında üretilen rasgele bir değeri, i parçacık numarasını, k iterasyon sayısını gösterir. C1 ve C2 öğrenme faktörleridir. C1 parçacığın kendi tecrübelerine göre, C2 ise sürüdeki diğer parçacıkların tecrübelerine göre hareketi yönlendirir. Düşük değerler seçilmesi parçacıkların hedef bölgeye doğru çekilmeden önce bu bölgeden uzak yerlerde dolaşmasına imkân verir. Ancak hedefe ulaşma süresi uzayabilir. Diğer yandan yüksek değerler seçilmesi hedefe ulaşmayı hızlandırırken beklenmedik hareketlerin oluşmasına ve hedef bölgenin es geçilmesine sebep olabilir. Formülden devam edecek olursak Pgd problemimiz için en iyi değere sahip konum vektörünü (gbest), Xid parçacığın şu anki konum vektörünü, Pid i. parçacığın en iyi olduğu konumu (pbest), Vid i. bireyin şu anki hız vektörünü ve W momentum katsayısını temsil eder.

# PSO Parametreleri
Parçacık Sürü Optimizasyonu avantajlarından birisi reel sayılarla çalışıyor olmasıdır. Genetik algoritmalardaki gibi hesaplama yapabilmek için ikili kodlamadan dönüştürme yapılması ya da bazı özel zorunlu operatörlere ihtiyaç duymamasıdır. Örneğin  f(x)=x1^2+x2^2+x3^2 fonksiyonu için çözüm bulmayı deneyelim. Burada 3 bilinmeyen olduğundan dolayı D=3 ve parçacık (x1,x2,x3) şeklinde ayarlanır. f(x) fonksiyonu da uygunluk fonksiyonu olarak kullanılır. Daha sonra yukarıda verilen standart prosedür optimumu bulmak için uygulanır. Sonlama kriteri olarak maksimum iterasyon sayısı veya minimum hata koşulu sağlanması beklenir. Görüldüğü gibi PSO’ da ihtiyaç duyulan çok az sayıda parametre vardır. Bu parametrelerin listesi tipik olarak aldıkları değerler aşağıda verilmektedir.

    Parçacık Sayısı: Genellikle 20 ile 40 arasında alınır. Alında Çoğu problem için sayıyı 10 almak iyi çözümler elde etmek için    yeterlidir. Bazı zor veya özel problemler için 100 veya 200 parçacık kullanılması gerekebilir.
    Parçacık Aralığı: Optimize edilecek probleme göre değişmekle birlikte farklı boyutlarda ve aralıklarda parçacıklar tanımlanabilir.
    VMax: Bir iterasyonda, bir parçacıkta meydana gelecek maksimum değişikliği (hız) belirler. Genellikle parçacık aralığına göre   belirlenir. Örneğin x1 parçacığı (10,10) aralığında ise VMax=20 ile sınırlandırılabilir.
    Öğrenme Faktörleri: c1 ve c2 genellikle 2 veya c1=c2 olarak [0,4] aralığında seçilir.
    Durma Koşulu: Maksimum iterasyon sayısına ulaşıldığında veya değer fonksiyonu istenilen seviyeye ulaştığında algoritmayı durdurur.

# PSO Algoritması

    for her parçacık için
      parçacığı başlangıç konumuna getir
    end
    for her parçacık için 
      uygunluk değerini hesapla
       if uygunluk değeri pbest’den daya iyi ise
        şimdiki değeri yeni pbest olarak ayarla
    end
    tüm parçacıkların bulduğu pbest değerlerinin en iyisini, tüm parçacıkların gbest’i olarak ayarla
     for her parçacık için
      denklem(1)’e göre parçacık hızını hesapla
      denklem(2)’ye göre parçacık konumunu güncelle
     end
    for maksimum iterasyon sayısına veya minimum hata koşulunu sağlanana kadar devam et

# Sonuç
Geçtiğimiz birkaç yıl içinde PSO, birçok araştırma ve uygulama alanında başarıyla uygulanmıştır. PSO, diğer yöntemlerle karşılaştırıldığında daha hızlı ve daha ucuz bir şekilde daha iyi sonuçlar aldığı gözlemlenmiştir. 
PSO’nun çekici olmasının bir başka nedeni ayarlanacak az sayıda parametresinin bulunmasıdır. Parçacık Sürü Optimizasyonu, geniş bir uygulama yelpazesinde ve belirli bir gereksinime odaklı uygulamalar için rahatça kullanılabilen bir yaklaşımdır.
