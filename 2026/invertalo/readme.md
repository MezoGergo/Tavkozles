# Mérési Jegyzőkönyv: Műveleti erősítő vizsgálata (Invertáló alapkapcsolás)

**Készítette:** Mező Gergő  
**Dátum:** 2026.01.29.  
**Helyszín:** Miskolci SZC Kandó Kálmán Informatikai Technikum, V3 Labor  

---

## 1. Mérés célja
A TL071 típusú műveleti erősítővel felépített fázisfordító (invertáló) alapkapcsolás vizsgálata, az elméleti erősítés és a mért értékek összehasonlítása NI ELVISmx műszerek segítségével.

## 2. Felhasznált eszközök és komponensek
* **Műveleti erősítő:** TL071
* **Mérőrendszer:** NI ELVISmx (Function Generator, Oscilloscope)
* **Passzív alkatrészek:**
    * Bemeneti ellenállás ($R_1$): $11.9\text{ k}\Omega$
    * Visszacsatoló ellenállás ($R_2$): $99\text{ k}\Omega$
    * Kompenzáló ellenállás ($R_3$): $11.9\text{ k}\Omega$

## 3. Kapcsolási elrendezés
Az áramkör egy klasszikus invertáló erősítő kapcsolás. A nem invertáló (+) bemenet a földre van kötve egy ellenálláson keresztül, míg a bemenő jel az invertáló (-) bemenetre érkezik.

*(Ide töltsd fel a kapcsolási rajzot tartalmazó képet, pl: `circuit_diagram.png`)*
(<img width="1076" height="650" alt="kapcsolas" src="https://github.com/user-attachments/assets/ccb8aba1-8fd3-4491-9789-d28ca6c9a71f" />


## 4. Elméleti számítások

Az invertáló erősítő feszültségerősítése ($A_v$) az alábbi képlettel számolható:

$$A_v = - \frac{R_2}{R_1}$$

Behelyettesítve a komponensek értékeit:

$$A_v = - \frac{99\text{ k}\Omega}{11.9\text{ k}\Omega} \approx \mathbf{-8.319}$$

Ez azt jelenti, hogy a kimeneti jel amplitúdója kb. 8,3-szorosa lesz a bemenetinek, és a fázisa 180°-kal elfordul (invertálódik).

**Elméleti kimeneti feszültség ($1\text{ V}$ bemenet esetén):**
$$V_{out} = V_{in} \cdot |A_v| = 1\text{ V} \cdot 8.319 = 8.319\text{ V}$$

## 5. Mérési beállítások (Function Generator)
A bemeneti jelet az NI ELVISmx függvénygenerátorával állítottuk elő:
* **Jelalak:** Szinusz
* **Frekvencia:** $100\text{ Hz}$
* **Amplitúdó:** $1.00\text{ }V_{pp}$
* **DC eltolás (Offset):** $0.00\text{ V}$

![Függvénygenerátor beállításai](<img width="522" height="597" alt="fuggvenyg" src="https://github.com/user-attachments/assets/36abca26-db0a-410f-81d6-d722ee0f43ac" />

 )

## 6. Mérési eredmények (Oscilloscope)
Az oszcilloszkópon a sárga csatorna (CH0) a bemeneti jelet, a kék csatorna (CH1) a kimeneti jelet mutatja.

| Csatorna | Jelölés | Mért érték ($V_{p-p}$) | Frekvencia |
| :--- | :--- | :--- | :--- |
| **Bemenet (CH0)** | $V_{in}$ | $1.003\text{ V}$ | $100.000\text{ Hz}$ |
| **Kimenet (CH1)** | $V_{out}$ | $8.379\text{ V}$ | $99.999\text{ Hz}$ |

![Oszcilloszkóp mérés](<img width="1074" height="740" alt="scope" src="https://github.com/user-attachments/assets/ca19a4fd-da3c-4731-834b-1e84db54da73" />

 )

## 7. Kiértékelés
A mérés során kapott tényleges erősítés meghatározása:

$$A_{mért} = \frac{V_{out}}{V_{in}} = \frac{8.379\text{ V}}{1.003\text{ V}} \approx \mathbf{8.353}$$

**Összehasonlítás:**
* Elméleti erősítés: $8.319$
* Mért erősítés: $8.353$

Az oszcilloszkóp ábráján jól látható a fázisfordítás: amikor a sárga jel (bemenet) a pozitív tartományban van, a kék jel (kimenet) a negatívban, ami igazolja az invertáló működést. A mért és számított értékek közötti eltérés minimális, ami az ellenállások tűréshatárának és a mérési pontatlanságnak tudható be. A kapcsolás az elvárásoknak megfelelően működik.
