# MÉRÉSI JEGYZŐKÖNYV

**Mérés tárgya:** Műveleti erősítő vizsgálata (Fázisfordító alapkapcsolás)  
**Mérés helyszíne:** Miskolci SC Kandó Kálmán Technikum, V3 labor  
**Mérés időpontja:** 2026. január 29.  
**Mérést végezte:** Tóth Tibor   

---

## 1. A mérés célja
A műveleti erősítővel felépített fázisfordító (invertáló) alapkapcsolás működésének vizsgálata, a feszültségerősítés meghatározása méréssel és számítással, valamint a bemeneti és kimeneti jelalakok összehasonlítása.

## 2. Felhasznált eszközök és szoftverek
* **Mérőrendszer:** NI ELVIS II+ (National Instruments Educational Laboratory Virtual Instrumentation Suite)
* **Szoftver:** NI ELVISmx Instrument Launcher (Függvénygenerátor, Oszcilloszkóp)
* **Áramköri elemek:**
    * Műveleti erősítő
    * Ellenállások (R1, R2, R3)
    * Próbapanel és mérőzsinórok

## 3. Kapcsolási elrendezés és paraméterek
A mérés során egy fázisfordító erősítő kapcsolást vizsgáltunk az alábbi kapcsolási rajz alapján:

<img width="841" height="481" alt="image" src="https://github.com/user-attachments/assets/d45935ad-0e35-4639-a803-fd218da5fcf8" />



**Alkatrészértékek:**
* **R1 (Bemeneti ellenállás):** 11,8 kΩ
* **R2 (Visszacsatoló ellenállás):** 99,9 kΩ
* **R3 (Kompenzáló ellenállás):** 11,9 kΩ

## 4. Mérési beállítások (Függvénygenerátor)
A bemeneti jelet az NI ELVISmx függvénygenerátorával állítottuk elő. A beállított paraméterek az alábbi képernyőképen láthatók:

<img width="522" height="591" alt="unnamed" src="https://github.com/user-attachments/assets/f96cf92e-1821-44a4-9f33-d1106a869126" />


**Beállítások részletezése:**
* **Jelalak:** Szinusz
* **Frekvencia:** 100 Hz
* **Amplitúdó (Vpp):** 1,00 V
* **DC offszet:** 0,00 V

## 5. Mérési eredmények (Oszcilloszkóp)
A bemeneti és kimeneti jelek vizsgálata oszcilloszkóppal történt. A kapott hullámformák és a mért adatok:

<img width="1076" height="738" alt="unnamed (1)" src="https://github.com/user-attachments/assets/8b60cbf3-b95a-429f-9d21-573ed5815678" />


Az oszcilloszkóp `Scope` műszerével rögzített értékek:

| Csatorna | Jelölés | Funkció | Mért Vpp (Csúcs-csúcs feszültség) | Frekvencia |
| :--- | :--- | :--- | :--- | :--- |
| **CH 0 (Zöld)** | $U_{be}$ | Bemeneti jel | 999,56 mV (~1,0 V) | 100,001 Hz |
| **CH 1 (Kék)** | $U_{ki}$ | Kimeneti jel | 8,488 V | 100,000 Hz |

**Megfigyelés:**
Az oszcilloszkóp ábráján látható, hogy a kimeneti jel (kék) és a bemeneti jel (zöld) fázisa ellentétes ($180^{\circ}$-os fáziseltolás), ami igazolja az invertáló működést. A kimeneti jel amplitúdója jelentősen nagyobb a bemenetinél.

## 6. Számítások és kiértékelés

### Elméleti erősítés ($A_{elm}$) számítása:
Az invertáló erősítő feszültségerősítését az ellenállások aránya határozza meg:
$$A_{elm} = -\frac{R_2}{R_1}$$

Behelyettesítve az alkatrészértékeket:
$$A_{elm} = -\frac{99,9 \text{ k}\Omega}{11,8 \text{ k}\Omega} \approx -8,466$$

### Mért erősítés ($A_{mért}$) számítása:
A mért csúcs-csúcs feszültségek hányadosa (az előjelet a fázisfordítás adja):
$$|A_{mért}| = \frac{U_{ki (Vpp)}}{U_{be (Vpp)}} = \frac{8,488 \text{ V}}{0,99956 \text{ V}} \approx 8,491$$

Tehát: $A_{mért} \approx -8,491$ (a fázisfordítás miatt negatív).



## 7. Összegzés
A mérés során sikeresen összeállítottuk és megvizsgáltuk a fázisfordító alapkapcsolást.
1.  A beállított 100 Hz-es, 1 V-os bemeneti jelet az áramkör fázisában megfordította és felerősítette.
2.  A számított elméleti erősítés (-8,466) és a mérésből származó erősítés (-8,491) közötti eltérés minimális (kb. 0,3%), ami a műszerek pontosságának és az ellenállások tűrésének tudható be.
3.  Az áramkör az elvárásoknak megfelelően működött.

---
**Aláírás:**
Tóth Tibor
