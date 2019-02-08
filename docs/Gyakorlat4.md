
# Gyakorlat 4. - OpenShift S2I

## Tudnivalók
[Fontos információk](Tudnivalok.md)

**Fontos:**
- Lokális OpenShift is használható a virtuális gépetekben!
_sudo systemctl status openshift_ paranccsal ellenőrizd, hogy fut-e.
- OpenShift konvenciók, ha a központi Openshifttel dolgoztok.
  - Felhasználónevetek legyen: studentxy - ahol x y a nevetek kezdőbetűi pl. studentnz (kisbetűk)
  - Projektek nevei: gyakorlatNxy - N a gyakorlat száma, x, y lsd. előbb, pl. gyakorlat2nz (kisbetűk)
- Mindenki a saját userét használja ezután, hogy izoláltan dolgozzatok!


## Feladat 1. - OpenShift S2I
**Időtartam: ~30 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy egy saját GitHub account alatti alkalmazást deployoljatok a PaaS-ra.

1. Az előző feladatban létrehozott példa alkalmazás alapján készítsetek a saját GitHub accountok alá egy klónozott forrás struktúrát. Lsd. [itt](Tudnivalok.md)   
2. Az előző feladatot ismételjétek meg ezzel az új Git URL-el és ezúttal CLI parancsok használatával.
3. Kövesd végig a build és deploy folyamatot (nézd a console-on, vagy a logokat). A végén böngészőből meg lehessen hívni!
4. Próbáld ki, hogy változtatsz a forráson commitolsz, pusholsz és újra buildelsz/deployolsz.

_Hint: git parancsok,  oc projects, oc project, oc new-app, oc get svc, oc expose, oc logs -f bc, oc get pods,oc status. oc start-build stb._
https://docs.openshift.org/latest/cli_reference/basic_cli_operations.html

### Jegyzőkönyvhöz
A használt oc parancsokat küldjétek el a jegyzőkönyvben. 
