# Gyakorlat 1. - Docker

## Tudnivalók
[Fontos információk](Tudnivalok.md)
## Segédlet
## Docker parancsok
```shell
docker help
docker CMD --help
docker --debug CMD
```
[Legfontosabb Docker parancsok](https://www.cheatography.com/tobix10/cheat-sheets/docker-commands/)

## Hasznos linux parancsok
```shell
brctl show
ifconfig
ip link show
```


### Nginx
/usr/share/nginx/html alatt a főoldal
/etc/init.d/nginx stop|start|restart|status paranccsal lehet leállítani

---

## Feladat 1. - Docker alapműveletek 
**Időtartam: ~15-30 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy a legfontosabb Docker parancsokat megismerjétek. Ehhez a _docker help_ paranccsal mindent megtaláltok.

1. Listázd az elérhető Docker parancsokat, ismerkedj meg a help-jével, hogy könnyen megtalálj majd mindent a későbbiekben. (exec, images, info, inspect, logs, ps, pull, run, search, ...)
2. Nézd meg milyen image-ek vannak már lehúzva a helyi registry-be.
3. Keress egy cirros image-et és húzd a local repoba (Ez egy lightweight linux).
4. Indíts el egy az előbbi cirros image-ből készített container-t
  * Lépj be rá egy terminálba /bin/sh shell-be és győződj meg róla, hogy valóban egy izolált containerben vagy! (docker run -it kapcsolóra keress rá akár neten!)
  * Hasonlítsd össze a futó processzeket a containerben és a host gépen. (ps)
5. Ellenőrizd a következőket a futó containerben:
  * Mi a container host neve?
  * Milyen nameserver van beállítva?
  * Milyen hálózati interfészek vannak? 
  * Mi a gateway? 
  * Milyen IP-t kapott?   
  * Milyen a routing table? (pl. netstat -nr)
6. Fusson a cirros konténer és nyomozd ki, hogy a HOST gépen (tehát a VirtualBox-os image-en) melyik fájlban tárolódik a container "/etc/hostname" fájlja!

_Hint: ezek a parancsok lesznek hasznotokra: docker search, docker pull, docker run -it, docker ps, netstat -nr, docker inspect stb._
### Jegyzőkönyvhöz
A jegyzőkönyvhöz másold ki egy text fájlba az utolsó pontra adott választ ill. hogy melyik docker paranccsal jöttél rá!

---

## Feladat 2. - Docker www szerver
**Időtartam: ~15 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy egy futó konténernek valahogy a hasznát is vegyük. 
A feladat, hogy futtassatok Docker containerben egy web szervert. A host gépen megnyitva egy Firefoxot ezen az URL-en http://localhost írja ki, hogy Hello BME Paas labor! 80-as port ütközhet, ekkor válasszatok más portot.

Javasolt web szerver: nginx (de lehet más is)
A következőket biztosan meg kell oldani:

1. A konténer belső portjának megnyitása a host felé (_docker run -P_)
2. Figyeljétek meg a konténer státuszát! élettartamát! Ha megváltoztattok benne pl. egy index.html-et és leállítjátok, akkor egy új konténer indításánál nem lesz ott. Miért? El lehet-e indítani egy korábban módosított konténert (docker ps -a)?
3. (Opcionális) Esetleg köteg becsatolással is megoldható (docker run -v ...).

_Hint: ezek a parancsok lesznek hasznotokra: docker run -p, stb._
### Jegyzőkönyvhöz
A legfontosabb parancsokkal együtt egy 2-3 mondatos leírás legyen, hogy hogyan oldottátok meg.

---

## Feladat 3. - Docker hálózatok
**Időtartam: ~15 perc**

### Célja, leírás
Futtassuk az előbbi konténert, ami kinyitja a 80-as portot és ellenőrizzük a hálózati működést.

1. Állítsd le az összes futó konténert.
2. Ellenőrizd, listázd a host gépen, hogy milyen hálózati interfészek vannak.
3. Indítsd el pl. az előbbi feladat konténerét úgy, hogy nyisson egy portot a hoston.
4. Ellenőrizd, listázd a host gépen, hogy milyen hálózati interfészek vannak. Mi változott? 
   - Ellenőrizd a bridge-ket is!
5. Próbáld ki a docker network inspect parancsot. Figyeld meg, hogy milyen konténerek csatlakoznak a docker0 bridge-hez.
   - Akár több konténert is indíthatsz és az előbbi pontokat megnézheted ismét.

_Hint: ezek a parancsok lesznek hasznotokra: docker network, brctl, ifconfig_
### Jegyzőkönyvhöz
A jegyzőkönyvben szereplő kérdést válaszold meg!
