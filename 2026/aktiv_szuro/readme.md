# Mérési Jegyzőkönyv: Műveleti erősítő vizsgálata II. (Aktív sávszűrő)

**Készítette:** Mező Gergő  
**Dátum:** 2026.01.29.  
**Helyszín:** Miskolci SZC Kandó Kálmán Informatikai Technikum, V3 Labor  

---

## 1. Mérés célja
Többszörös visszacsatolású (Multiple Feedback - MFB) aktív sávszűrő áramkör vizsgálata, a középfrekvencia és az erősítés meghatározása, valamint a frekvenciamenet ellenőrzése.

## 2. Felhasznált eszközök és komponensek
* **Műveleti erősítő:** TL071
* **Mérőrendszer:** NI ELVISmx
* **Passzív alkatrészek:**
    * Ellenállások ($R_1, R_2, R_3$): $220\text{ }\Omega$  $10\text{ k}\Omega$
    * Kondenzátorok ($C_1, C_2$): $10\text{ }\mu\text{F}$

## 3. Kapcsolási elrendezés
Az áramkör egy invertáló bemenetre épülő MFB sávszűrő topológia. A bemeneti jel és a kimeneti visszacsatolás egy közös csomópontba fut, amely frekvenciafüggő módon vezérli az erősítőt.

<img width="889" height="546" alt="image" src="https://github.com/user-attachments/assets/4f880f7e-ad95-464f-9dd0-56c0fff4a890" />


## 4. Elméleti számítások

A kapcsolás paraméterei alapján ($R_1 = R_2 = R_3 = 1\text{ k}\Omega$ és $C_1 = C_2 = 10\text{ }\mu\text{F}$) a középfrekvencia ($f_0$) az alábbi képlettel számolható:

$$f_0 = \frac{1}{2\pi C} \sqrt{\frac{R_1 + R_2}{R_1 R_2 R_3}}$$

Mivel minden ellenállás egyforma ($R$), a képlet egyszerűsödik:

$$f_0 = \frac{\sqrt{2}}{2\pi \cdot R \cdot C}$$

Behelyettesítve ($R=1000\text{ }\Omega, C=10^{-5}\text{ F}$):

$$f_0 = \frac{1.4142}{2\pi \cdot 1000 \cdot 0.00001} \approx \frac{1.4142}{0.0628} \approx \mathbf{22.5\text{ Hz}}$$

**Elméleti feszültségerősítés a középfrekvencián ($A_0$):**
$$A_0 = - \frac{R_3}{2 \cdot R_1} = - \frac{1\text{ k}\Omega}{2\text{ k}\Omega} = \mathbf{-0.5}$$
*(Ez azt jelenti, hogy a kimeneti jel a középfrekvencián fele akkora lesz, mint a bemenő jel.)*

## 5. Mérési beállítások
A vizsgálathoz frekvencia-sweep (Bode) mérést alkalmazunk, mivel a szűrő karakterisztikája így látható a legjobban.

* **Start frekvencia:** $10\text{ Hz}$ (mivel a számított középfrekvencia nagyon alacsony)
* **Stop frekvencia:** $20\text{ kHz}$
* **Amplitúdó:** $2\text{ }V_{pp}$ (hogy a csillapítás ellenére mérhető legyen a kimenet)

## 6. Mérési eredmények (Bode Analyzer)

<img width="917" height="729" alt="image" src="https://github.com/user-attachments/assets/9137163b-7ead-4f54-b7d2-2469678d2c6b" />
