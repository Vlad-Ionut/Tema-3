# **Quick Time**

## **Descriere**
Aceasta este tema 3 a laboratorului de Microcontrolere, care presupune realizarea unui joc de reflexe pentru doi jucători. Proiectul este gândit pentru a testa viteza de reacție a participanților într-un mod competitiv, iar rezultatele sunt afișate în timp real pe un ecran LCD.

Fiecare jucător interacționează cu jocul printr-un set de butoane și LED-uri, iar la final este declarat câștigător cel care acumulează cel mai mare punctaj.

---

## **Cerințe și funcționalitate**

### **1. Componente utilizate:**
- **6 LED-uri** (câte 3 pentru fiecare jucător, fiecare de o culoare diferită)
- **2 LED-uri RGB** (unul pentru fiecare jucător)
- **6 butoane** (câte 3 pentru fiecare jucător)
- **1 LCD** (pentru afișarea scorurilor și mesajelor)
- **1 servomotor** (pentru a indica progresul jocului)
- **2 breadboard-uri**
- Fire de legătură
- **2 Arduino Uno**

### **2. Funcționalitatea jocului:**

1. **Pornirea jocului:**
   - Jocul începe cu afișarea unui mesaj de bun venit pe LCD.
   - Pornirea jocului se poate face prin:
     - Apăsarea oricărui buton.
     - Apăsarea unui buton dedicat.
     - Utilizarea unui buton separat pentru start.

2. **Runde de joc:**
   - La fiecare rundă, LED-ul RGB al jucătorului activ se aprinde într-o culoare.
   - Jucătorul trebuie să apese butonul corespunzător culorii afișate pentru a obține puncte.
   - Punctajele sunt afișate și actualizate în timp real pe LCD.

3. **Finalizarea jocului:**
   - Servomotorul indică progresul jocului prin rotație. Când ajunge la o rotație completă, jocul se termină.
   - La final, LCD-ul afișează scorul final și câștigătorul.

---

## **Detalii tehnice**

### **1. Comunicare SPI:**
Pentru a putea conecta toate componentele, am utilizat două plăci Arduino care comunică prin SPI:
- **Arduino Master:** Controlează LCD-ul, servomotorul și stochează starea jocului.
- **Arduino Slave:** Controlează LED-urile și butoanele, trimițând informații către Master.

### **2. Butoane:**
- Multiplexarea este utilizată pentru a economisi pini.
- Fiecare jucător folosește doar butoanele sale în timpul rundei active.

### **3. LED-uri:**
- Fiecare LED individual este asociat cu un buton de aceeași culoare.
- LED-ul RGB afișează o culoare specifică în funcție de rundă.

### **4. LCD:**
- LCD-ul afișează scorurile ambilor jucători și mesaje pe tot parcursul jocului.
- Controlul LCD-ului este realizat cu biblioteca **LiquidCrystal**.

### **5. Servomotor:**
- Servomotorul se rotește progresiv pentru a indica timpul rămas din joc.
