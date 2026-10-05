# Quiz: Seriile lui Gauss — Clasa a 5-a

> **Ideea de bază:** când numerele unui șir cresc mereu cu același pas (1, 2, 3, 2, 4, 6, 8...), nu trebuie să le adunăm unul câte unul. Le grupăm în perechi care dau mereu același rezultat și înmulțim.

---

# Partea 0 — Cum funcționează (de citit înainte de întrebări)

## Ce este un șir cu pas constant?

Un șir în care, de la un număr la următorul, adaugi mereu **aceeași** cantitate. Acea cantitate se numește **pasul** șirului.

| Șirul | Primul | Ultimul | Pasul |
|---|---|---|---|
| 1, 2, 3, ..., 100 | 1 | 100 | 1 |
| 7, 8, 9, ..., 20 | 7 | 20 | 1 |
| 2, 4, 6, ..., 20 | 2 | 20 | 2 |
| 11, 13, 15, ..., 99 | 11 | 99 | 2 |
| 15, 20, 25, ..., 100 | 15 | 100 | 5 |

Toate se rezolvă cu **aceleași trei reguli**. Nu contează de unde începe șirul!

## Regula 1 — Câte numere are șirul?

$$\text{numărul de termeni} = \frac{\text{ultimul} - \text{primul}}{\text{pasul}} + 1$$

**De ce acel „+1"?** Pentru că scăderea numără *distanțele*, nu *numerele*.

```
    7     8     9    10
    |-----|-----|-----|
       1     2     3        ← 3 distanțe (10 − 7 = 3)
    1     2     3     4     ← dar 4 numere!
```

Gândește-te la un gard: dacă ai 3 spații între stâlpi, ai 4 stâlpi. De la etajul 7 la etajul 10 urci 3 etaje, dar treci prin 4 etaje. **Întotdeauna cu unul mai mult decât scăderea.**

> ⚠️ Aceasta este greșeala nr. 1 la șirurile care nu încep de la 1. De la 7 la 20 **nu** sunt 13 numere, sunt **14**.

## Regula 2 — Perechile dau mereu același total

Luăm primul cu ultimul, al doilea cu penultimul și așa mai departe:

```
   7   8   9   10   11   ...   16   17   18   19   20
   └───────────────────────────────────────────────┘  7 + 20 = 27
       └───────────────────────────────────────┘      8 + 19 = 27
           └───────────────────────────────┘          9 + 18 = 27
```

Merge pentru că, atunci când primul număr **crește** cu un pas, celălalt **scade** cu exact același pas — suma nu se schimbă. Fiecare pereche valorează `primul + ultimul`.

## Regula 3 — Formula generală

$$S = \frac{(\text{primul} + \text{ultimul}) \times \text{numărul de termeni}}{2}$$

**De ce împărțim la 2?** Pentru că o pereche „înghite" două numere. Dacă ai 14 numere, ai 14 ÷ 2 = 7 perechi, fiecare de 27 → 7 × 27 = 189.

**Altă citire a aceleiași formule (mai utilă!):**

$$S = \underbrace{\frac{\text{primul} + \text{ultimul}}{2}}_{\text{media}} \times \text{numărul de termeni}$$

Adică: **suma = media × câte numere sunt.** Este ca și cum toate numerele ar fi egale cu cel din mijloc. Pentru 7, 8, ..., 20 media este (7+20)/2 = 13,5 → 13,5 × 14 = 189. ✓

Această citire explică și cazul neplăcut: **ce fac dacă numărul de termeni este impar?** Atunci nu pot forma perechi perfecte — dar nici nu am nevoie, pentru că media este exact numărul din mijloc. Pentru 100, 101, ..., 200 sunt 101 numere, media este (100+200)/2 = **150**, care este chiar numărul din mijloc → 150 × 101 = 15150.

## Cazul special: șirul 1, 2, 3, ..., n

Aici primul = 1, ultimul = n, pasul = 1, deci numărul de termeni este chiar n. Formula devine cea pe care a descoperit-o Gauss:

$$S = \frac{n \times (n + 1)}{2}$$

Este doar formula generală, scrisă pentru un caz particular. **Dacă ții minte una singură, ține-o minte pe cea generală.**

---

# Partea I — Șiruri de la 1 la n

## Întrebarea 1
**Micul Gauss avea 10 ani când profesorul i-a cerut să adune toate numerele de la 1 la 100. El a găsit răspunsul în câteva secunde. Care este suma?**

<details>
<summary>Răspuns</summary>

**5050**

Gauss a observat că poate forma perechi: 1+100=101, 2+99=101, 3+98=101 ... și așa mai departe. Sunt 50 de perechi, deci 50 × 101 = **5050**.

</details>

---

## Întrebarea 2
**Care este trucul lui Gauss? Cum putem aduna rapid numerele de la 1 la n?**

<details>
<summary>Răspuns</summary>

Formula lui Gauss este:

$$S = \frac{n \times (n + 1)}{2}$$

Adică înmulțești ultimul număr cu următorul lui și împarți la 2.

> **Cum funcționează pentru n impar?** Când n este impar, nu poți forma perechi perfecte — rămâne un număr singur la mijloc. De exemplu, pentru 1 la 11: perechile 1+11, 2+10, 3+9, 4+8, 5+7 dau fiecare 12, iar 6 rămâne la mijloc. Numărul din mijloc este exact jumătate din suma unei perechi (12÷2=6), deci este ca o „jumătate de pereche": 5,5 perechi × 12 = **66**. Formula funcționează la fel: n/2 × (n+1) = 5,5 × 12 = 66 ✓

</details>

---

## Întrebarea 3
**Folosind formula lui Gauss, cât face suma numerelor de la 1 la 10?**

<details>
<summary>Răspuns</summary>

$$S = \frac{10 \times 11}{2} = \frac{110}{2} = \mathbf{55}$$

Verificare: 1+2+3+4+5+6+7+8+9+10 = 55 ✓

</details>

---

## Întrebarea 4
**De ce adunăm perechile 1+100, 2+99, 3+98? Ce au ele special?**

<details>
<summary>Răspuns</summary>

Toate perechile dau **același rezultat** (101). Asta se întâmplă pentru că pe măsură ce primul număr crește cu 1, al doilea scade cu 1 — suma rămâne constantă.

</details>

---

## Întrebarea 5
**Câte perechi se formează când aduni numerele de la 1 la 100?**

<details>
<summary>Răspuns</summary>

Se formează **50 de perechi**: (1,100), (2,99), (3,98), ..., (50,51).

În general, pentru numerele de la 1 la n, se formează **n/2** perechi.

</details>

---

## Întrebarea 6
**Cât face suma numerelor de la 1 la 20?**

<details>
<summary>Răspuns</summary>

$$S = \frac{20 \times 21}{2} = \frac{420}{2} = \mathbf{210}$$

</details>

---

## Întrebarea 7
**O clasă are 8 elevi. Fiecare elev dă mâna cu toți ceilalți o singură dată. Câte strângeri de mână au loc în total?**

> *Indiciu: gândește-te la suma 1+2+3+...+7*

<details>
<summary>Răspuns</summary>

Primul elev dă mâna cu 7 colegi, al doilea cu 6 (restul), al treilea cu 5... și tot așa:

$$S = 1+2+3+4+5+6+7 = \frac{7 \times 8}{2} = \mathbf{28} \text{ strângeri de mână}$$

</details>

---

## Întrebarea 8
**Dacă suma numerelor de la 1 la n este 15, care este n?**

<details>
<summary>Răspuns</summary>

$$\frac{n \times (n+1)}{2} = 15 \implies n \times (n+1) = 30$$

Încercăm: 5 × 6 = 30 ✓

Deci **n = 5**. Verificare: 1+2+3+4+5 = 15 ✓

</details>

---

# Partea II — Șiruri care NU încep de la 1 (pas 1)

## Întrebarea 9
**Câte numere sunt de la 7 la 20?**

<details>
<summary>Răspuns</summary>

$$20 - 7 + 1 = \mathbf{14} \text{ numere}$$

**Atenție la capcană:** 20 − 7 = 13, dar asta numără doar *pașii* de la 7 la 20. Numerele sunt cu unul mai multe, pentru că îl numărăm și pe 7 însuși.

Scrie-le ca să te convingi: 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20 → 14 numere ✓

> **Regulă de ținut minte:** numărul de termeni = ultimul − primul + 1 (pentru pas 1).

</details>

---

## Întrebarea 10
**Cât face 7 + 8 + 9 + ... + 20?**

<details>
<summary>Răspuns</summary>

**Metoda 1 — perechile lui Gauss**

Câte numere? 20 − 7 + 1 = 14 numere → 14 ÷ 2 = **7 perechi**.

Cât valorează o pereche? 7 + 20 = **27**. (Verifică: 8+19 = 27, 9+18 = 27 ✓)

$$S = 7 \times 27 = \mathbf{189}$$

**Metoda 2 — scad ce nu-mi trebuie**

Pornesc de la 1 și arunc începutul care nu face parte din șir:

$$S = (1+2+...+20) - (1+2+...+6) = \frac{20 \times 21}{2} - \frac{6 \times 7}{2} = 210 - 21 = \mathbf{189}$$

Ambele metode dau același rezultat ✓

> **Când folosesc care?** Metoda 1 merge mereu. Metoda 2 este utilă când ții minte deja formula lui Gauss și vrei să nu numeri termenii. **Atenție:** scazi suma până la numărul **de dinaintea** primului (aici 6, nu 7!).

</details>

---

## Întrebarea 11
**Cât face 20 + 21 + 22 + ... + 50?**

<details>
<summary>Răspuns</summary>

Câte numere: 50 − 20 + 1 = **31 numere**.

Numărul de termeni este **impar**, deci nu pot forma perechi perfecte. Folosesc formula cu media:

$$S = \frac{(20 + 50) \times 31}{2} = \frac{70 \times 31}{2} = 35 \times 31 = \mathbf{1085}$$

> Media este (20+50)/2 = 35, care este exact numărul din mijlocul șirului. Deci 35 × 31 = 1085.

Verificare prin scădere: (1+...+50) − (1+...+19) = 1275 − 190 = **1085** ✓

</details>

---

## Întrebarea 12
**Într-un bloc, apartamentele de la etajul 4 sunt numerotate de la 31 la 60. Care este suma tuturor acestor numere?**

<details>
<summary>Răspuns</summary>

Câte apartamente: 60 − 31 + 1 = **30**.

$$S = \frac{(31 + 60) \times 30}{2} = \frac{91 \times 30}{2} = 91 \times 15 = \mathbf{1365}$$

Verificare: (1+...+60) − (1+...+30) = 1830 − 465 = **1365** ✓

</details>

---

## Întrebarea 13
**Cât face suma numerelor de la 100 la 200?**

<details>
<summary>Răspuns</summary>

Câte numere: 200 − 100 + 1 = **101 numere** (nu 100!).

$$S = \frac{(100 + 200) \times 101}{2} = 150 \times 101 = \mathbf{15150}$$

> Aici media (150) este chiar numărul din mijloc al șirului — al 51-lea număr. De-o parte și de alta a lui sunt câte 50 de numere, care se împerechează frumos: 100+200, 101+199, ..., 149+151. Deci 50 de perechi de 300, plus 150 rămas la mijloc: 15000 + 150 = 15150 ✓

</details>

---

## Întrebarea 14
**Suma a cinci numere naturale consecutive este 100. Care sunt numerele?**

<details>
<summary>Răspuns</summary>

Folosim invers ideea de medie: **suma = media × numărul de termeni**, deci

$$\text{media} = 100 \div 5 = 20$$

La un șir cu pas constant și un număr impar de termeni, media **este** numărul din mijloc. Deci numărul din mijloc este 20:

$$18 + 19 + \mathbf{20} + 21 + 22 = 100$$

> **De ce funcționează?** 18 este cu 2 mai mic decât 20, iar 22 este cu 2 mai mare — se compensează. La fel 19 și 21. Rămâne ca toate cinci să fie „în medie" 20.

</details>

---

# Partea III — Șiruri cu pas mai mare de 1

## Întrebarea 15
**Poți folosi formula lui Gauss și pentru numere pare? Cât face 2+4+6+...+20?**

<details>
<summary>Răspuns</summary>

Da! Observăm că fiecare număr este dublul unui număr din șirul 1, 2, ..., 10:

$$S = 2 \times (1+2+3+...+10) = 2 \times \frac{10 \times 11}{2} = 2 \times 55 = \mathbf{110}$$

Sau direct cu formula generală: 10 numere, prima + ultima = 22 → (22 × 10)/2 = **110** ✓

</details>

---

## Întrebarea 16
**Cât face suma multiplilor de 3 de la 3 la 30? (3+6+9+...+30)**

<details>
<summary>Răspuns</summary>

Fiecare număr din șir este de 3 ori un număr din șirul 1, 2, ..., 10:

$$S = 3 \times (1+2+3+...+10) = 3 \times \frac{10 \times 11}{2} = 3 \times 55 = \mathbf{165}$$

> **Același lucru cu perechile lui Gauss:** 3+30=33, 6+27=33, ..., 15+18=33 → 5 perechi × 33 = **165** ✓

Trucul general: dacă seria merge din k în k (din 2 în 2, din 3 în 3 etc.) **și începe de la k**, dai factor comun k și aplici formula lui Gauss pentru șirul 1,2,...,n.

</details>

---

## Întrebarea 17
**Câte numere sunt în șirul 15, 20, 25, ..., 100? Și cât fac ele adunate?**

<details>
<summary>Răspuns</summary>

Aici pasul este **5**, iar șirul nu începe de la 5. Aplicăm Regula 1 cu pasul:

$$\text{numărul de termeni} = \frac{100 - 15}{5} + 1 = \frac{85}{5} + 1 = 17 + 1 = \mathbf{18}$$

$$S = \frac{(15 + 100) \times 18}{2} = 115 \times 9 = \mathbf{1035}$$

> **De ce împărțim la pas?** Pentru că fiecare „săritură" valorează 5. De la 15 la 100 am urcat 85, adică 85 ÷ 5 = 17 sărituri — și, ca la gard, 17 sărituri înseamnă 18 numere.

Verificare prin factor comun: 15+20+...+100 = 5 × (3+4+...+20) = 5 × (210 − 3) = 5 × 207 = **1035** ✓

</details>

---

## Întrebarea 18
**Cât face 11 + 13 + 15 + ... + 99? (numerele impare de la 11 la 99)**

<details>
<summary>Răspuns</summary>

Pasul este **2**, primul este 11, ultimul 99.

$$\text{numărul de termeni} = \frac{99 - 11}{2} + 1 = 44 + 1 = \mathbf{45}$$

$$S = \frac{(11 + 99) \times 45}{2} = \frac{110 \times 45}{2} = 55 \times 45 = \mathbf{2475}$$

> Aici **nu** putem da factor comun 2, pentru că numerele sunt impare. Dar formula generală funcționează oricum — ea nu are nevoie ca șirul să înceapă de la ceva anume.

Verificare: suma imparelor de la 1 la 99 este 2500 (vezi Întrebarea 20), iar 1+3+5+7+9 = 25, deci 2500 − 25 = **2475** ✓

</details>

---

# Partea IV — Provocări ⭐

## Întrebarea 19 ⭐
**Cât face suma numerelor de la 1 la 1000?**

<details>
<summary>Răspuns</summary>

$$S = \frac{1000 \times 1001}{2} = 500 \times 1001 = \mathbf{500\,500}$$

</details>

---

## Întrebarea 20 ⭐
**Cât face suma numerelor impare de la 1 la 99? (1+3+5+...+99)**

<details>
<summary>Răspuns</summary>

Sunt **50 de numere impare** de la 1 la 99.

> **De ce sunt 50?** Fiecare număr impar are un „prieten" par chiar după el: 1→2, 3→4, 5→6, ..., 99→100. Numerele de la 1 la 100 se împart perfect în 50 de perechi (impar + par), deci sunt exact **50 de numere impare**.
>
> Sau cu Regula 1: (99 − 1) / 2 + 1 = 49 + 1 = 50 ✓

Perechile: 1+99=100, 3+97=100, ..., 49+51=100 → 25 de perechi

$$S = 25 \times 100 = \mathbf{2500}$$

Sau mai simplu: suma primelor n numere impare este întotdeauna **n²** → 50² = **2500** ✓

</details>

---

## Întrebarea 21 ⭐
**Cât face suma tuturor numerelor de două cifre?**

<details>
<summary>Răspuns</summary>

Numerele de două cifre sunt de la **10** la **99** — un șir care nu începe de la 1.

Câte sunt: 99 − 10 + 1 = **90**.

$$S = \frac{(10 + 99) \times 90}{2} = 109 \times 45 = \mathbf{4905}$$

Verificare: (1+...+99) − (1+...+9) = 4950 − 45 = **4905** ✓

</details>

---

## Întrebarea 22 ⭐⭐
**Cât face suma numerelor de la 1 la 100 care NU sunt divizibile cu 3?**

<details>
<summary>Răspuns</summary>

Strategia: adun tot, apoi scad ce nu vreau.

**Tot:** 1 + 2 + ... + 100 = (100 × 101)/2 = **5050**

**Multiplii de 3 până la 100:** 3, 6, 9, ..., 99 → câte sunt? (99 − 3)/3 + 1 = 32 + 1 = **33**

$$3+6+...+99 = 3 \times (1+2+...+33) = 3 \times \frac{33 \times 34}{2} = 3 \times 561 = 1683$$

**Răspunsul:**

$$S = 5050 - 1683 = \mathbf{3367}$$

</details>

---

## Întrebarea 23 ⭐⭐
**Un elev calculează suma numerelor de la 8 la 24 și obține 256. Unde a greșit și cât este rezultatul corect?**

<details>
<summary>Răspuns</summary>

El a socotit **16 numere** (24 − 8 = 16) și a făcut, **greșit**:

$$\frac{(8 + 24) \times 16}{2} = 32 \times 8 = 256$$

A uitat **„+1"**! Numărul corect de termeni este 24 − 8 + 1 = **17**, deci rezultatul **corect** este:

$$S = \frac{(8 + 24) \times 17}{2} = 16 \times 17 = \mathbf{272}$$

Diferența dintre cele două rezultate este 272 − 256 = **16**, adică exact valoarea unei „jumătăți de pereche" (32 ÷ 2). Cu alte cuvinte, el a lăsat pe dinafară un număr întreg din șir.

**Verifică ideea pe un șir scurt**, de la 8 la 12:
- greșit (4 termeni): (8 + 12) × 4 / 2 = **40** ✗
- corect (5 termeni): (8 + 12) × 5 / 2 = **50** ✓
- adunat direct, termen cu termen: 8 + 9 + 10 + 11 + 12 = **50** ✓

**Morala:** la șirurile care nu încep de la 1, numără termenii cu grijă — sau testează formula pe un șir scurt pe care îl poți verifica direct.

</details>

---

# 📋 Fișa de formule

Pentru un șir cu pas constant (primul = a, ultimul = u, pasul = p):

| Ce vreau | Formula |
|---|---|
| Câte numere sunt | $n = \dfrac{u - a}{p} + 1$ |
| Suma | $S = \dfrac{(a + u) \times n}{2}$ |
| Suma (altă citire) | $S = \text{media} \times n$, unde media $= \dfrac{a+u}{2}$ |
| Caz special: 1+2+...+n | $S = \dfrac{n \times (n+1)}{2}$ |
| Caz special: 1+3+5+...+ al n-lea impar | $S = n^2$ |

## ⚠️ Greșeli frecvente

1. **Uiți „+1"** la numărul de termeni. De la 7 la 20 sunt 14 numere, nu 13.
2. **Împarți la 2 de două ori.** Ori faci „perechi × valoarea perechii", ori faci „(a+u) × n / 2" — nu amândouă.
3. **La metoda scăderii, scazi prea mult.** Pentru 7+8+...+20 scazi suma până la **6**, nu până la 7.
4. **Dai factor comun când nu poți.** La 11+13+...+99 (numere impare) nu există factor comun 2. Folosește formula generală.
5. **Te blochezi când numărul de termeni este impar.** Nu e nevoie de perechi perfecte: suma = media × numărul de termeni, iar media este numărul din mijloc.
