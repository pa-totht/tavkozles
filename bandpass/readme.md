# MÉRÉSI JEGYZŐKÖNYV

---

### I. Adminisztrációs adatok

| Adat megnevezése | Részletek |
| :--- | :--- |
| **Készítette:** | **Tóth Tibor** |
| **Intézmény:** | Miskolci SC Kandó Kálmán Technikum |
| **Mérés helyszíne:** | V3 labor |
| **Mérés dátuma:** | 2026. február 5. |
| **Mérés tárgya:** | Aktív sávszűrő áramkör vizsgálata |

---

### II. A mérés leírása

#### 1. A mérés célja
Egy műveleti erősítővel felépített aktív sávszűrő áramkör összeállítása, valamint frekvenciamenetének (erősítés és fázis) vizsgálata Bode-diagram segítségével. A rezonanciafrekvencia és a maximális erősítés meghatározása.

#### 2. Felhasznált eszközök és szoftverek
* **Hardver:** NI myDAQ adatgyűjtő eszköz, próbapanel (breadboard).
* **Alkatrészek:**
    * Műveleti erősítő (Op-Amp)
    * Ellenállások: 2 db 220 $\Omega$, 1 db 10 k$\Omega$
    * Kondenzátorok: 2 db 100 nF
* **Szoftver:** NI ELVISmx (Bode Analyzer modul)

---

### III. A mérés menete és eredmények

#### 1. Kapcsolási rajz és összeállítás
Az áramkört az alábbi elrendezés szerint állítottuk össze a próbapanelen. A kapcsolás egy "Multiple Feedback" (többszörös visszacsatolású) sávszűrő topológiát követ.
* **Bemenet:** NI myDAQ Analog Output (AO 0)
* **Kimenet:** NI myDAQ Analog Input (AI 1)
* **Referencia:** Analog Input (AI 0)

**Kapcsolási rajz:**
<img width="698" height="392" alt="Képernyőkép 2026-02-05 095350" src="https://github.com/user-attachments/assets/cde2a563-a0b4-4711-83c9-6de2a8a30604" />


#### 2. Mérési beállítások (NI ELVISmx)
* **Start frekvencia:** 200 Hz
* **Stop frekvencia:** 20.00 kHz
* **Lépésköz:** 50 / decade
* **Peak Amplitude:** 0.10 V
* **Mapping:** Logaritmikus

#### 3. Mért eredmények (Bode diagram alapján)
A szoftveres mérés során kapott karakterisztika az alábbi ábrán látható:

**Mérési eredmény (Bode diagram):**
<img width="923" height="737" alt="safasdasas" src="https://github.com/user-attachments/assets/97e3b6ea-3b47-4bc8-ab1e-14b9679e813f" />


A kurzor segítségével leolvasott értékek a rezonanciaponton:

| Paraméter | Mért érték | Mértékegység | Megjegyzés |
| :--- | :--- | :---: | :--- |
| **Rezonanciafrekvencia ($f_0$)** | **1741,93** | **Hz** | A grafikon csúcspontja |
| **Maximális erősítés (Gain)** | **24,02** | **dB** | (kb. 15,89-szeres feszültségerősítés) |
| **Fázistolás ($f_0$-nál)** | **-176,21** | **fok** | |

---

### IV. Kiértékelés és összegzés

**Tapasztalatok:**
A mérés során sikeresen felvettük az aktív szűrő átviteli karakterisztikáját. A fenti Bode-diagramon jól látható a sávszűrő jelleg:
1.  Alacsony frekvencián az erősítés kicsi és növekszik.
2.  A **1,74 kHz** környéki rezonanciafrekvencián az erősítés eléri a maximumot (**24 dB**).
3.  A rezonanciafrekvencia felett az erősítés csökken.

A mért karakterisztika alakja megfelel az elméletileg várt haranggörbének. A fázisgörbe a rezonanciapont környezetében meredeken vált, ami szintén jellemző erre a kapcsolásra.

**Dátum:** Miskolc, 2026. február 5.

**Aláírás:**

__________________________
Tóth Tibor
