# UlakTraining
5g Çekirdek Şebeki Mimarisi:
UE: UE yani User Equipment yani kullanıcı ekipmanı dediğimiz kullanıcılarımızın networke bağlanmak için kullandığı cihazlara verilen genel isimdir.
gNB:gNB yani new generation NodeB dediğimiz şey 4g'deki eşdeğeri eNB olan radyo nodülümüzdür. gNB 5g kullanan UE'lerin 5G networküne 5g NR (New Radio/ Yeni Radyo) hava arayüzünü kullanarak bağlanmasına izin verir.
gNB 3 ana fonksiyonel modülden oluşur: CU(Control Unit/ Kontrol Ünitesi), DU(Distributed Unit/ Dağıtma Ünitesi), RU(Radio Unit/ Radio Ünitesi).
gNB-CU MC(Mobility Control/Mobilite Kontrol), RRM(Radio Resource Management/Radyo Kaynak Yönetimi) ve SM(Session Management/Oturum Yönetimi) özelliklerini yönetir ve kontrol eder. 
Bunun yanında gNB-DU ise PHY(Fiziksel Erişim) ve MAC(Ortam erişim kontrol) tabaka fonksiyonitelerini sağlar. gNB-DU ve gNB-CU arasındaki fonksiyonelite ayrımı implementasyona bağlıdır.
RAN: RAN(Radio Access Network/Radyo Erişim Ağı)
AMF: AMF (Access and Mobility Management Function/Erişim ve Mobilite Yönetim Fonksiyonu) aslında bütün 5g networkümüzdeki UE'ler için tek giriş noktası olarak davranır. AMF UE'den veya RAN'dan bağlantılara ve seansın kendisine dair bütün bilgileri alır ama sadece bağlantı ve hareketlilik yönetim ile ilgili görevlerle ilgilenir. Eğer seans yönetimiyle ilgili bir şey yapılması gerekirse bu SMF'e yönlendirilir. AMF 4G'deki MME'nin dekompose edildikten sonra bağlantı ve hareketlilik kısmıyla ilgilenen yeni komponenttir, fakat seans yönetimi kısmı içinse daha önce dediğim gibi MME vardır.
SMF:SMF(Session Management Function/Seans Yönetim Fonksiyonu) ise MME'nin işlerinin diğer kısmını devraldı ve Seansları yönetmek, oluşturmak, modifiye etmek, ve serbest bırakmaktan sorumludur. UE'ye IP address alokasyonu ve bunların yönetiminden sorumludur. DHPC fonksiyonlarından sorumludur(?).Seans yönetimiyle alakalı NAS(?) Sinyalleri termninasyonundan sorumludur. Aynı zamanda UPF'e düzgün trafik rotalaması için UPF'e trafik yönlendirme konfigurasyonundan sorumludur.
NAS Signalling:NAS(Non-Access Stratum/Erişilemeyen Tabaka(?, ismi tam anlayamadım)) UMTS ve LTE içindeki kablosuz telekom protokollerin tabakalarından biridir. NAS mesajalrına örnek olarak mesaj eklemek veya güncellemek, mesaj onaylanması, servis isteği vs.
UPF:UPF(User Plane Function/ Kullanıcı Düzlemi Fonksiyonu), paket rotaları ve yönlendirmeden, paket incelemekten, QoS'i handle etmek, Data Network(internet vs)'e bağlanmak için dışsal bir PDU seans bağlantı noktası olmak, gibi görevleri vardır.
UDM: AKA(Authentication and Key Agreement/Otantikasyon ve anahtar anlaşması) yeterliliklerinin üretimi, kullanıcı otantikasyon, erişim otorizasyonu ve abone yönetimi gibi konularda destek olur. 
PCF: PCF(Policy Control Function/Poliçe Kontrol Fonksiyonu) doğal olarak 4g'deki pcrf'in özelliklerinin bazılarını barındırır.
PCF'in en önemli işlerinden bazıları:
Birleşmiş Poliçe Frameworkünü desteklemek,CP fonksiyonlarına poliçe kurallarını aktarmak,UDR'daki poliçelerle lgili kararlar için abone bilgilerine erişim sağlama,
PCRF:Policy and Charging Rules Function() PCF'in 4G'deki ve daha kapsamlı halidir, fakat anladığım kadarıyla 5G'de bazı fonksiyoniteleri ayrıldı ve geriye de PCF kaldı.
NF: NF(Network Function/Şebeke Fonksiyonu) Yukarıda bahsettiğimiz bütün fonksiyonları referans eden terimdir.
Data Network: Herhangi bir çeşit internet veya bir data ağına referans etmek için şemalarda kullanılır.
PDU Session: Bir veya birden çok QoS akışını destekleyen ve bir UE'den Data Networke erişimi UPF üzerinden yapılan bağlantılarda kullandığımız şeydir.
NFV: NFV(Network Function Virtualization/Network Fonksiyonelite Sanallaştırılması) aslında anladığım kadarıyla 5g'nin en büyük özelliklerinden biri, normalde fiziksel olarak kurulması gereken tonla cihazı, mesela routerlar, dijital olarak çalışan yazılımlarla değiştirerek hem servis zamanlarını azaltacak hem de maliyetleri azaltacak ve bir nevi endüstri standardı getirecek sanırım. Telekom şirketlerinin artık gidip sürekli cihaz kurmasına vs gerek kalmayacak.
AUSF: AUSF(Authentication Server Function/ Doğrulama Sunucu Fonksiyonu) bir doğrulama sunucusu olarak iş görür, (EPC dünyasından HSS'in parçası olduğu yazıyor.)
AF:AF(Application Function/Aplikasyon Fonksiyonu) trafik rotalarında aplikasyon etkilerini kontrol etme, NEF'e erişim sağlama, poliçe frameworküyle poliçe kontrolu için etkileşim sağlar. (EPC dünyasındaki AF ile aynı işi görür.)
NEF: NEF(Network Exposure Function/ Şebeke Teşhir Fonksiyonu) capability ve eventlerin exposure'ı, dış applikasyonlardan 3GPP networküne güvenli bilgi akatarımı,içsel ve dışsal bilginin çevrimini destekler.
NEF'in neler yaptığını kafamda canlandıramadım.
NRF: NRF(NF Repository Function/NF Repozito Fonksiyonu) servis keşfetme fonksiyonunu destekler, NF profilini ve müsait olan NF instancelarını maintain eder.
NSSF:NSSF(Network Slice Selection Function/ Şebeke Parçası Seçme Fonksiyonu) Network Slicelarının UE'ye servis edilecek instancelarını seçmeden, izin verilen NSSAI'ları belirleme, ve UE'ye servis edilecek AMF setini ayırmadan sorumludur.