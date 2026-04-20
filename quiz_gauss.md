# Quiz: Seriile lui Gauss

---

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

## Întrebarea 9
**Poți folosi formula lui Gauss și pentru numere pare? Cât face 2+4+6+...+20?**

<details>
<summary>Răspuns</summary>

Da! Observăm că fiecare număr este dublul unui număr din șirul 1,2,...,10:

$$S = 2 \times (1+2+3+...+10) = 2 \times \frac{10 \times 11}{2} = 2 \times 55 = \mathbf{110}$$

</details>

---

## Întrebarea 10 ⭐ (Provocare)
**Cât face suma numerelor impare de la 1 la 99? (1+3+5+...+99)**

<details>
<summary>Răspuns</summary>

Sunt **50 de numere impare** de la 1 la 99.

> **De ce sunt 50?** Fiecare număr impar are un „prieten" par chiar după el: 1→2, 3→4, 5→6, ..., 99→100. Numerele de la 1 la 100 se împart perfect în 50 de perechi (impar + par), deci sunt exact **50 de numere impare**.

Perechile: 1+99=100, 3+97=100, ..., 49+51=100 → 25 de perechi

$$S = 25 \times 100 = \mathbf{2500}$$

Sau mai simplu: suma primelor n numere impare este întotdeauna **n²** → 50² = **2500** ✓

</details>

---

*Formula lui Gauss: **S = n × (n+1) / 2***
