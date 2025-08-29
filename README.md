# Türkiye İl, İlçe, Mahalle/Köy Veritabanı

Bu repository, Türkiye'nin tüm il, ilçe, mahalle ve köy bilgilerini JSON formatında içermektedir.

## Dosyalar

### `turkiye-il-ilce-mahalle-koy.json`
Bu dosya, [il-ilce-mahalle-geolocation-rest-api](https://github.com/melihkorkmaz/il-ilce-mahalle-geolocation-rest-api) projesinden alınan veriler JSON formatına dönüştürülerek oluşturulmuştur.

**İçerik:**
- İl, ilçe, mahalle ve köy hiyerarşik yapısı
- Türkiye'nin tüm idari bölünüş bilgileri

### `turkiye-il-ilce-mahalle.json`
Bu dosya, [turkey-city-data](https://github.com/mhmmdglc/turkey-city-data) projesinden alınan veriler JSON formatına dönüştürülerek oluşturulmuştur.

**İçerik:**
- İl, ilçe ve mahalle hiyerarşik yapısı

## Kullanım

```python
import json

with open('turkiye-il-ilce-mahalle-koy.json', 'r', encoding='utf-8') as f:
    turkiye_veri = json.load(f)

# Belirli bir ilin ilçelerini alma
ankara_ilceleri = list(turkiye_veri['Ankara'].keys())

# Belirli bir ilçenin mahallelerini alma
cankaya_mahalleleri = turkiye_veri['Ankara']['Çankaya']

print(cankaya_mahalleleri)  # Liste olarak mahalle listesi
```

## Veri Yapısı

```json
{
  "il_adi": {
    "ilce_adi": [
      "mahalle_adi1",
      "mahalle_adi2",
      "mahalle_adi3"
    ]
  }
}
```

**Yapı Açıklaması:**
- **İl seviyesi:** Türkiye'nin 81 ili
- **İlçe seviyesi:** Her ile bağlı ilçeler
- **Mahalle/Köy seviyesi:** Her ilçeye bağlı mahalle ve köy isimleri dizi (array) formatında

## 🤝 Katkıda Bulunanlar

- Orijinal veri kaynakları:
  - [@melihkorkmaz](https://github.com/melihkorkmaz) 
  - [@mhmmdglc](https://github.com/mhmmdglc) 

**Not:** Bu veriler üçüncü parti kaynaklardan derlenmiştir. Verilerdeki eksiklik, hata veya güncel olmayan bilgiler için herhangi bir sorumluluk kabul edilmemektedir. Kritik uygulamalarda kullanımdan önce verilerin doğruluğunu mutlaka resmi kaynaklardan kontrol ediniz.
