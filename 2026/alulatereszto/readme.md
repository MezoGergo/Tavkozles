---

## 8. Mérés kiegészítése: Aktív aluláteresztő szűrő vizsgálata

Az alapkapcsolást kiegészítettük egy kondenzátorral a visszacsatoló ágban, így a kapcsolás frekvenciafüggővé vált.

### 8.1. Módosított kapcsolási elrendezés
A $99\text{ k}\Omega$-os visszacsatoló ellenállással ($R_2$) párhuzamosan egy $10\text{ nF}$-os kondenzátort ($C$) kötöttünk.

* **Kondenzátor értéke ($C$):** $10\text{ nF}$

<img width="1113" height="755" alt="kapcsolás 2" src="https://github.com/user-attachments/assets/76fcd5df-5f08-40ec-a49d-fc513addc583" />
    

### 8.2. Elméleti számítások (Határfrekvencia)
Az aluláteresztő szűrő határfrekvenciáját ($f_c$, más néven törésponti frekvencia) az a pont határozza meg, ahol az erősítés $3\text{ dB}$-t esik a kisfrekvenciás értékhez képest.

$$f_c = \frac{1}{2 \pi \cdot R_2 \cdot C}$$

Behelyettesítve az értékeket ($R_2 = 99\text{ k}\Omega$, $C = 10\text{ nF}$):

$$f_c = \frac{1}{2 \pi \cdot 99000\text{ }\Omega \cdot 10 \cdot 10^{-9}\text{ F}} \approx \mathbf{160,75\text{ Hz}}$$

Ezen a frekvencián a fázistolásnak az invertáló jelleg ($180^{\circ}$) miatt további $-45^{\circ}$-ot kell csökkennie, tehát elméletileg $135^{\circ}$-nál kell lennie.

### 8.3. Bode-diagram mérése (NI ELVISmx Bode Analyzer)
A frekvenciamenet vizsgálatát a Bode Analyzer műszerrel végeztük $20\text{ Hz}$ és $20\text{ kHz}$ között.

**Mérési eredmények a kurzor alapján:**
A kurzort a $-3\text{ dB}$-es ponthoz (a törésponti frekvenciához) igazítottuk.
* **Maximális erősítés (DC közelében):** $\approx 18,4\text{ dB}$ ($8,3$-szoros)
* **Mért határfrekvencia ($f_{c, mért}$):** $158,87\text{ Hz}$
* **Erősítés a határfrekvencián:** $15,40\text{ dB}$ (Ez pontosan $3\text{ dB}$ esés a $18,4$-hez képest)
* **Fázis a határfrekvencián:** $135,14^{\circ}$

<img width="922" height="737" alt="bode" src="https://github.com/user-attachments/assets/04ea9375-9d92-4399-b68f-82dba24e6ebd" />
    
---

## 9. A megépített áramkör fényképe

Az alábbi képen a laborgyakorlat során összeállított áramkör látható a próbapanelen:

![kep 2](https://github.com/user-attachments/assets/48726af8-ef23-4195-a56d-6b91674b0b07)


   
### 8.4. Kiértékelés (Szűrő vizsgálat)
Az aktív szűrő mérése során kapott eredmények szinte tökéletesen egyeznek az elméleti számításokkal.

* **Számított határfrekvencia:** $160,75\text{ Hz}$
* **Mért határfrekvencia:** $158,87\text{ Hz}$

A két érték közötti eltérés elhanyagolható ($\approx 1,2\%$), ami az alkatrészek (főleg a kondenzátor) szórásából adódik. A Bode-diagramon jól látható, hogy a határfrekvencia felett az erősítés csökken (meredeksége $-20\text{ dB/dekád}$), ami igazolja az aluláteresztő jelleg működését. A fázisgörbe $135^{\circ}$-os értéke a határfrekvencián szintén igazolja az elméletet.
