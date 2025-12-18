# LAPORAN-MINGGUAN-JOB-6
Nama: Muhammad Aqil Alkausar

NPM: 2410017514012

Prodi: TRKJ 

Mata kuliah: Basic Analog Electronic

1. Tujuan Pratikum
   
   Tujuan dari pratikum ini adalah untuk:
   
•	Untuk mengetahui cara kerja seven Segment

•	Untuk mengetahui cara kerja arduino dengan seven segment

•	Untuk menguji keterkiriman source code pada board arduino dan seven segment.

3. Teori

Seven Segment Display (7 Segment Display) dalam bahasa Indonesia disebut dengan Layar Tujuh Segmen adalah komponen Elektronika yang dapat menampilkan angka desimal melalui kombinasi-kombinasi segmennya. Seven Segment Display pada umumnya dipakai pada Jam Digital, Kalkulator, Penghitung atau Counter Digital, Multimeter Digital dan juga Panel Display Digital seperti pada Microwave Oven ataupun Pengatur Suhu Digital . Seven Segment Display pertama diperkenalkan dan dipatenkan pada tahun 1908 oleh Frank. W. Wood dan mulai dikenal luas pada tahun 1970-an setelah aplikasinya pada LED (Light Emitting Diode).

Terdapat 2 Jenis LED 7 Segmen, diantaranya adalah “LED 7 Segmen common Cathode” dan “LED 7 Segmen common Anode”.
1.	LED 7 Segmen Tipe Common Cathode (Katoda)
Pada LED 7 Segmen jenis Common Cathode (Katoda), Kaki Katoda pada semua segmen LED adalah terhubung menjadi 1 Pin, sedangkan Kaki Anoda akan menjadi Input untuk masing-masing Segmen LED.  Kaki Katoda yang terhubung menjadi 1 Pin ini merupakan Terminal Negatif (-) atau Ground sedangkan Signal Kendali (Control Signal) akan diberikan kepada masing-masing Kaki Anoda Segmen LED.

 2. Pada LED 7 Segmen jenis Common Anode (Anoda), Kaki Anoda pada semua segmen LED adalah terhubung menjadi 1 Pin, sedangkan kaki Katoda akan menjadi Input untuk masing-masing Segmen LED. Kaki Anoda yang terhubung menjadi 1 Pin ini akan diberikan Tegangan Positif (+) dan Signal Kendali (control signal) akan diberikan kepada masing-masing Kaki Katoda Segmen LED.
3.	Peralatan
   1.	Laptop
   2.	Board Arduino
   3.	Konektor USB
   4.	Breadboard
   5.	Seven Segment
   6.	Jumper wires
4.	Rangkaian Praktikum 
Praktikum dilaksanakan dengan  rangkaian sebagai berikut :
<img width="585" height="435" alt="image" src="https://github.com/user-attachments/assets/3845c88f-494d-48ab-b1fe-76e1c2022013" />
 
6.	Prosedur Praktikum 
•	Mempersiapkan peralatan praktikum
•	Membuka arduino IDE, lalu menulis listing program.
•	Mengecek listing program yang telah dibuat.
•	Merangkai komponen sesuai dengan rangkaian pelaksanaan dan memasang kabel USB pada Arduino dengan port USB yang terdapat pada Laptop.
•	Mengecek rangkaian yang telah dirangkai.
•	Mengcompile dan mengupload program kedalam Arduino board.
•	Mengamati hasil percobaan.
7.	Screnshoot prosedur pratikum
   ![WhatsApp Image 2025-12-18 at 21 56 35](https://github.com/user-attachments/assets/05aa0148-4459-4008-afe6-b1fbb64fcbbc)

9.	Source Code Arduino
    // Definisi pin segmen (a sampai g, dp)
const int pinA = 2;
const int pinB = 3;
const int pinC = 4;
const int pinD = 5;
const int pinE = 6;
const int pinF = 7;
const int pinG = 8;
const int pinDP = 9;

// Fungsi untuk mematikan semua segmen
void clearDisplay() {
  digitalWrite(pinA, LOW);
  digitalWrite(pinB, LOW);
  digitalWrite(pinC, LOW);
  digitalWrite(pinD, LOW);
  digitalWrite(pinE, LOW);
  digitalWrite(pinF, LOW);
  digitalWrite(pinG, LOW);
  digitalWrite(pinDP, LOW);
}

// Fungsi menampilkan angka 0-9
void showNumber(int num) {
  clearDisplay();
  switch (num) {
    case 0:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinB, HIGH);
      digitalWrite(pinC, HIGH);
      digitalWrite(pinD, HIGH);
      digitalWrite(pinE, HIGH);
      digitalWrite(pinF, HIGH);
      break;
    case 1:
      digitalWrite(pinB, HIGH);
      digitalWrite(pinC, HIGH);
      break;
    case 2:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinB, HIGH);
      digitalWrite(pinD, HIGH);
      digitalWrite(pinE, HIGH);
      digitalWrite(pinG, HIGH);
      break;
    case 3:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinB, HIGH);
      digitalWrite(pinC, HIGH);
      digitalWrite(pinD, HIGH);
      digitalWrite(pinG, HIGH);
      break;
    case 4:
      digitalWrite(pinB, HIGH);
      digitalWrite(pinC, HIGH);
      digitalWrite(pinF, HIGH);
      digitalWrite(pinG, HIGH);
      break;
    case 5:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinC, HIGH);
      digitalWrite(pinD, HIGH);
      digitalWrite(pinF, HIGH);
      digitalWrite(pinG, HIGH);
      break;
    case 6:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinC, HIGH);
      digitalWrite(pinD, HIGH);
      digitalWrite(pinE, HIGH);
      digitalWrite(pinF, HIGH);
      digitalWrite(pinG, HIGH);
      break;
    case 7:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinB, HIGH);
      digitalWrite(pinC, HIGH);
      break;
    case 8:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinB, HIGH);
      digitalWrite(pinC, HIGH);
      digitalWrite(pinD, HIGH);
      digitalWrite(pinE, HIGH);
      digitalWrite(pinF, HIGH);
      digitalWrite(pinG, HIGH);
      break;
    case 9:
      digitalWrite(pinA, HIGH);
      digitalWrite(pinB, HIGH);
      digitalWrite(pinC, HIGH);
      digitalWrite(pinD, HIGH);
      digitalWrite(pinF, HIGH);
      digitalWrite(pinG, HIGH);
      break;
  }
}

void setup() {
  // Set semua pin sebagai OUTPUT
  pinMode(pinA, OUTPUT);
  pinMode(pinB, OUTPUT);
  pinMode(pinC, OUTPUT);
  pinMode(pinD, OUTPUT);
  pinMode(pinE, OUTPUT);
  pinMode(pinF, OUTPUT);
  pinMode(pinG, OUTPUT);
  pinMode(pinDP, OUTPUT);

  clearDisplay(); // Pastikan awal mati semua
}

void loop() {
  // Tampilkan angka 0 sampai 9, bergantian tiap 1 detik
  for (int i = 0; i <= 9; i++) {
    showNumber(i);
    delay(1000);
  }
}


