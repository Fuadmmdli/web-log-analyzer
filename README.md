Sistem Log Analizi və Təhlükəsizlik Hesabatı
Bu layihə, sistem log fayllarını analiz etmək, 404 status kodlarına sahib URL-ləri tapmaq və onları qara siyahıdakı domenlərlə müqayisə edərək təhlükəsizlik təhlili etmək üçün nəzərdə tutulmuşdur. Layihə, müxtəlif fayl formatlarında (mətn, CSV, JSON) hesabatlar yaradır və istifadəçinin təhlükəsizlik təhdidlərini müəyyən etməsinə kömək edir.

Layihənin Təsviri
Bu skript, sistem log faylını analiz edir, URL-ləri və onların uyğun status kodlarını çıxarır, 404 səhv kodları ilə URL-ləri müəyyən edir, onları sayır və qara siyahıdakı domenlərlə müqayisə edir. Həmçinin, istifadəçiyə nəticələri mətn faylları, CSV və JSON formatlarında təqdim edir.

Əsas Xüsusiyyətlər
Log Analizi: access_log.txt faylından URL-ləri və onların status kodlarını çıxarır.
404 Səhvləri: 404 status kodları ilə URL-ləri tapır və hər birinin neçə dəfə göründüyünü hesablayır.
Qara Siyahı Analizi: HTML faylındakı qara siyahıdakı domenləri tapır və bu domenlərlə uyğun URL-ləri çıxarır.
Hesabatların Yaradılması:
URL və status kodları haqqında mətn faylı (url_status_report.txt)
404 səhvli URL-lər və onların sayları haqqında CSV faylı (malware_candidates.csv)
Qara siyahıya alınmış URL-lər və onların statusu haqqında JSON faylı (alert.json)
Ümumi xülasə hesabatı (summary_report.json)
Tələblər
Python 3.x
beautifulsoup4 kitabxanası (HTML təhlili üçün)
lxml parseri (BeautifulSoup üçün)
re (Regex modulu, daxil edilmişdir)
csv (CSV faylları üçün)
json (JSON faylları üçün)
collections.Counter (URL-lərin sayını hesablamaq üçün)
Quraşdırma
Layihə fayllarını GitHub reposundan yükləyin və ya git clone əmri ilə əldə edin.
bash
git clone https://github.com/istifadəçi_adınız/repo_adı.git
Lazım olan Python kitabxanalarını quraşdırın.
bash
pip install beautifulsoup4 lxml
İstifadə
HTML Faylını və Log Faylını Yükləyin: threat_feed.html və access_log.txt fayllarını müvafiq olaraq layihə qovluğuna əlavə edin.

Skripti işlədin: Skripti işlətmək üçün terminalda aşağıdakı əmri yazın:

bash
python skript_adı.py
Çıxış Hesabatları: Skript aşağıdakı faylları yaradacaq:
url_status_report.txt – Bütün URL-ləri və status kodlarını saxlayacaq.
malware_candidates.csv – 404 səhvləri ilə URL-lər və onların saylarını CSV formatında saxlayacaq.
alert.json – Qara siyahıya alınmış uyğun URL-ləri və onların təfərrüatlarını saxlayacaq.
summary_report.json – Ümumi xülasə hesabatını saxlayacaq.
Nümunə Çıxış
url_status_report.txt:


http://example.com/page1 200
http://malicious-site.com/page2 404
http://example.com/page3 404

malware_candidates.csv:


URL,404 Count
http://malicious-site.com/page1,2
alert.json:

json
[
    {
        "url": "http://malicious-site.com/page1",
        "status_code": "404",
        "event_count": 2
    }
]
summary_report.json:

json
{
    "total_urls": 4,
    "404_errors": 2,
    "unique_404_urls": 1,
    "blacklisted_matches": 1
}
Əlavə Qeydlər
Bu skript, access_log.txt faylında HTTP status kodlarını və URL-ləri analiz edir.
HTML faylındakı qara siyahıya alınmış domenlərlə müqayisə aparılır və uyğun URL-lər müəyyən edilir.
Skriptin işini test etmək üçün thread_feed.html faylını və uyğun log faylını təmin etmək lazımdır.
Təşəkkürlər
Bu layihə ilə əlaqəli hər hansı bir sualınız və ya təklifləriniz varsa, mənimlə əlaqə saxlaya bilərsiniz.
