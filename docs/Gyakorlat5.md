# Gyakorlat 5. - POD skálázás

## Tudnivalók
[Fontos információk](Tudnivalok.md)

**Fontos:**
- OpenShift konvenciók:
  - Felhasználónevetek legyen: studentxy - ahol x y a nevetek kezdőbetűi pl. studentnz (kisbetűk)
  - Projektek nevei: gyakorlatNxy - N a gyakorlat száma, x, y lsd. előbb, pl. gyakorlat2nz (kisbetűk)
- Mindenki a saját userét használja ezután, hogy izoláltan dolgozzatok!


## Feladat 1. - OpenShift manuális skálázás
**Időtartam: ~20 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy kipróbáljuk a POD-ok skálázását.

1. Telepíts egy tetszőleges olyan alkalmazást, amely HTTP forgalmat fogad, mindenképp legyen egy böngészőből megszólítható alkalmazásod a PaaS-ban. Lehet az előző feladatokból megmaradt alkalmazás!
2. Eddig 1 db POD-ot indított el a ReplicationController, próbáld ki, hogy manuálisan növelitek a POD számot (DeploymentConfig szinten).
_Hint: oc get rc, oc get dc, oc scale_

## Feladat 2. - OpenShift automatikus skálázás
**Időtartam: ~20 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy kipróbáljuk a POD-ok automatikus skálázását. Az előző feladatból indulj ki.

- Módosítsd a DeploymentConfig-ot, ahol megadod pl. a CPU request-et.
```shell
oc edit dc
#containers részbe kell írni
# ports:
#        - containerPort: 8080
#          protocol: TCP
#        resources:
#          limits:
#            cpu: 200m
#          requests:
#            cpu: 50m
```
- Állítsd be az autoscalinget (oc autoscale) a DeploymentConfigra
```shell
oc autoscale dc/nodejs-ex --min=1 --max=10 --cpu-percent=10
```
- Generálj hálózati forgalmat:
```shell
ab -n 100000 -c 1 http://test-gyakorlat3xy.apps.openshift.local/
```
- Figyeld mi történik a POD-okkal
```shell
watch oc get pods
oc get hpa --watch
```

### Jegyzőkönyvhöz
Nincs feladat.
