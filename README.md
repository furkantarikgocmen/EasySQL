# EasySQL
## Spagetti PHP için SQL Query Framework'ü.
### Projeye Dahil Etmek için:
```
include('sql.php');
```
### Fonskiyonların Kullanımı :
* **Veri Listeleme**
```
$data = getData('kullanici');
$data = json_decode($data, true);
for($i = 0; $i < count($data); $i++)
{
	echo($data[$i]['k_adi']);
	echo($data[$i]['k_sifre']);
}
```
* **Opsiyonel Veri Listeleme**
```
$data = getDataOptionel('kullanici',"limit 1"); // veya where u_id = 1 veya join işlemleri
$data = json_decode($data, true);
for($i = 0; $i < count($data); $i++)
{
	echo($data[$i]['kullanici_adi']);
	echo($data[$i]['kullanici_sifre']);
}
```
* **Veri Ekleme**
```
veriEkle("kullanici","kullanici_adi,kullanici_sifre","yeni1#yeni2") // '#' ayraç operatörüdür (Tırnak işaretleri hariç);
```
* **Veri Güncelleme**
```
veriGuncelle("kullanici","kullanici_adi,kullanici_sifre","yeni3#yeni4","kullanici_id","9");
```
* **Veri Silme**
```
veriSil("kullanici","kullanici_id","9");
```
* **Login Kontrol**
```
loginAuthentication("DENEME","DENEME") // Boolean Döner. Tablo adı ve sütun isimleri kod üzerinde belirtilmiştir.
```
* **Kaç Satır Var**
```
howMany("kullanici");
```
* **Tek Bir Satıra Ait Veriler**
```
$veri = getInformation("kullanici","4"); //id 4
echo($veri['k_adi']);
echo($veri['k_sifre']);
```
