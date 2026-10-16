Tarayıcı tabanlı, WebAssembly (Wasm) SQLite motoru ve otomatik tetikleyiciler (Triggers) ile çalışan interaktif E-Ticaret Yönetim ve Takip Paneli.

 Proje Genel Bakış

Bu proje; klasik bir ön yüz uygulamasının ötesinde, ilişkisel veritabanı yönetim sistemi (RDBMS) mantığını tarayıcı üzerinde Client-Side (İstemci Taraflı) olarak çalıştıran bir E-Ticaret yönetim platformudur.

Backend veya harici bir sunucu kurulumu gerektirmeden, WebAssembly derlemesi olan sql.js kullanılarak bellek içi (in-memory) tam teşekküllü bir SQLite veritabanı oluşturulur. Sistemde veri tutarlılığı doğrudan yazılım katmanında değil, veritabanı tetikleyicileri (Triggers) ve ilişkisel tablolar aracılığıyla garanti altına alınmıştır.

 Öne Çıkan Özellikler

WebAssembly Tabanlı SQLite: Tarayıcı içerisinde izole, hızlı ve gerçek zamanlı SQL sorgu işleme kabiliyeti.

Otomatik Veritabanı Tetikleyicileri (Triggers):

trg_stok_kontrol: Sipariş girişi öncesinde stok miktarını denetler, yetersiz stokta işlemi RAISE(ABORT) ile engeller.

trg_stok_dusur: Başarılı sipariş sonrası ilgili ürünün stok miktarını otomatik olarak günceller.

trg_tutar: Sipariş detayları, ürün fiyatı ve indirim oranı üzerinden toplam sipariş tutarını anlık hesaplar.

İlişkisel Veri Mimarisi (RDBMS): 8 ilişkisel tablo, 50'den fazla örnek veri ve Foreign Key yapısına uygun sorgulama.

Dinamik Yönetim Modülleri:

 Özet / Dashboard: Ciro, kritik stok, sipariş hacmi gibi temel KPI metrikleri.

 Müşteri Analitiği: Harcama geçmişi, teslimat/iptal oranları ve müşteri bazlı sipariş detay modalı.

 Stok ve Kategori Yönetimi: Dinamik arama, kategori filtresi ve eşik değerine göre renk kodlu stok barı.

 Kargo & Lojistik Takip: Durum bazlı (Onaylandı, Kargoda, Teslim Edildi) aşamalı takip sistemi.

 İşlem & Tetikleyici Log Konsolu: Verilen yeni siparişin veritabanı trigger akışını anlık izleme olanağı.



Kullanılan Teknolojiler

Core: HTML5, Modern CSS (CSS Variables, Flexbox, Grid), Vanilla JavaScript (ES6+)

Veritabanı / Motor: SQLite (via sql.js WebAssembly)

İkon Seti: Tabler Icons
