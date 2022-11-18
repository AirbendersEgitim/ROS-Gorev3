
# ROS-Gorev3
Bu görevde sizden telemetri verilerinizi eklemenizi ve bu verilerle bazı işlemler yapmanızı istiyoruz.
Bu verileri mavros topiclerinden çekmeniz gerekiyor. [Kaynak](http://wiki.ros.org/mavros).

İlk olarak bilgisayarda simülasyon ile mavrosun bağlantısının (drone üzerinde raspberry pi ile pixhawk) sağlanıp sağlanmadığını kontrol etmeniz gerekiyor eğer bağlanmadıysa kodun devam etmemesini sağlamalısınız.

Buradan sonra aşağıda verilen konumlar bir txt dosyasından okunarak dronun başlangıç noktasına göre lokal pozisyonu ekrana yazdırılmaldır. İpucu: bu kısımda WGS84 kütüphanesini kullanabilirsin.
```
(41.0854866,29.0408879)
(41.0856095,29.0404048)
(41.0852049,29.0413493)
```
Gazebonun başlangıç konumunu Uçaksavar kampüsü olarak ayarlamak için aşağıdaki komutları Gazebo'yu çalıştırdığın terminale yazabilirsin.
```
export PX4_HOME_LAT=41.0853187
export PX4_HOME_LON=29.0409626
```


Sonraki kısımda Qgroundcontrol üzerinden drona belli bir rota vererek bu sırada bazı bilgileri çekmenizi ve bu verileri terminale yazdırmanızı istiyoruz. Bunlar;
* Hız
* İvme
* Thrust
* Global konum
* Lokal konum
* Roll pitch yaw (İpucu: Quaternion-Euler açı dönüşümüne bak.)
Bu veriler saniyede 1 kez terminale basılmalıdır.

## Özet
Yazdığınız kod istenen global-lokal konum dönüşümünü hesaplamalı ve yukarıda istenen verileri drondan çekerek terminale yazdırmalıdır. Bunun için Qgroundcontrol ile dronun simülasyonda uçuşunu sağlayarak veri değişimlerini gözlemlemelisin.
