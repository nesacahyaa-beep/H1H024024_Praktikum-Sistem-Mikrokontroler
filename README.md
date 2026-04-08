# Percobaan 2 – Running LED

Percobaan ini bertujuan untuk mempelajari pengendalian LED menggunakan Arduino Uno. Percobaan mencakup:  
1. Gambaran rangkaian schematic LED.  
2. LED berjalan dari kiri ke kanan.  
3. LED berjalan dari kanan ke kiri (*bounce effect*).  
4. LED tiga kiri dan tiga kanan menyala bergantian.

---

## 1. Rangkaian Schematic LED

Rangkaian menggunakan 5 LED yang disusun paralel dengan resistor 220 Ω untuk membatasi arus.  
- Anoda LED dihubungkan ke pin digital Arduino (2–6).  
- Katoda LED dihubungkan ke resistor, kemudian ke GND.  

![Percobaan 2 – Running LED](images/percobaan2.jpeg)

---

## 2. Program LED Berjalan dari Kiri ke Kanan dan Kanan ke Kiri

### Kiri ke Kanan
LED dinyalakan satu per satu dari pin kecil ke besar untuk membuat efek bergerak dari kiri ke kanan.

```cpp
for (int ledPin = 2; ledPin <= 6; ledPin++) {
    digitalWrite(ledPin, HIGH); // Nyalakan LED
    delay(200);                  // Tunggu 200 ms
    digitalWrite(ledPin, LOW);   // Matikan LED sebelum pindah LED berikutnya
}
## 3. Jelaskan bagaimana program membuat LED kembali dari kanan ke kiri

Setelah LED berjalan dari kiri ke kanan, efek *running LED* dapat dibalik agar LED menyala dari kanan ke kiri (*bounce effect*).  

### Kode Program

```cpp
for (int ledPin = 6; ledPin >= 2; ledPin--) {
    digitalWrite(ledPin, HIGH); // Nyalakan LED
    delay(200);                  // Tunggu 200 ms agar LED terlihat menyala
    digitalWrite(ledPin, LOW);   // Matikan LED sebelum pindah ke LED berikutnya
}
## 4. Program agar LED menyala tiga LED kanan dan tiga LED kiri secara bergantian

Program ini membuat LED menyala secara bergantian antara tiga LED kiri dan tiga LED kanan menggunakan array dan perulangan `for`.

### Kode Program

```cpp
// Deklarasi pin LED kiri dan kanan
int ledKiri[] = {2, 3, 4};   // Pin LED kiri
int ledKanan[] = {5, 6, 7};  // Pin LED kanan

void setup() {
  // Mengatur semua pin LED sebagai OUTPUT
  for (int i = 0; i < 3; i++) {
    pinMode(ledKiri[i], OUTPUT);  // Set pin LED kiri sebagai OUTPUT
    pinMode(ledKanan[i], OUTPUT); // Set pin LED kanan sebagai OUTPUT
  }
}

void loop() {
  // Nyalakan LED kiri
  for (int i = 0; i < 3; i++) {
    digitalWrite(ledKiri[i], HIGH); // Nyalakan LED kiri satu per satu
  }
  delay(500); // Tunggu agar LED menyala terlihat
  for (int i = 0; i < 3; i++) {
    digitalWrite(ledKiri[i], LOW);  // Matikan LED kiri
  }

  // Nyalakan LED kanan
  for (int i = 0; i < 3; i++) {
    digitalWrite(ledKanan[i], HIGH); // Nyalakan LED kanan satu per satu
  }
  delay(500); // Tunggu agar LED menyala terlihat
  for (int i = 0; i < 3; i++) {
    digitalWrite(ledKanan[i], LOW);  // Matikan LED kanan
  }
}
