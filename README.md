# Laporan Mingguan Job 5

**Nama**: Alip Farhandana Lubis  
**NPM**: 2410017514004  
**Prodi**: TRKJ  
**Mata Kuliah**: LAB IV Basic Analog Electronic

### 1. Tujuan Praktikum

Tujuan dari praktikum ini adalah untuk:
- Mengetahui cara kerja sensor suhu LM35.
- Mengetahui cara kerja Arduino dengan sensor suhu LM35.
- Menguji keterkaitan dan komunikasi antara Arduino dan sensor LM35 melalui pengujian source code.

### 2. Teori

Sensor suhu IC LM35 adalah komponen elektronik yang berfungsi mengubah suhu menjadi sinyal tegangan yang proporsional. LM35 memiliki sensitivitas 10 mV/°C, artinya untuk setiap perubahan suhu sebesar 1°C, output tegangan sensor akan berubah sebesar 10 mV. Sensor ini memerlukan tegangan operasi DC 5V dan dapat bekerja pada rentang suhu -55°C hingga +150°C. Output sensor berupa tegangan yang langsung dapat dibaca oleh Arduino.

- **Kelebihan LM35**:
  - Rentang suhu yang lebar (-55°C hingga +150°C).
  - Akurasi tinggi dengan ketepatan ±0.5°C pada 25°C.
  - Tegangan output linier dengan perubahan suhu.
  - Tidak memerlukan kalibrasi atau pengkondisian sinyal tambahan.

Formula output sensor:
\[ V_{out} = (Temperature) \times 10 \, \text{mV} \]

### 3. Peralatan

- Laptop
- Board Arduino (Arduino Uno)
- Konektor USB
- Breadboard
- Kabel jumper
- Sensor suhu LM35
- LDR (Light Dependent Resistor) (jika diperlukan)

### 4. Rangkaian Praktikum

Pada praktikum ini, kita akan merakit sensor suhu LM35 dengan Arduino. Berikut adalah gambaran sederhana dari rangkaian yang digunakan:

**Pin Sensor LM35**:
- **VCC**: Pin 1 (diberikan tegangan 5V dari Arduino)
- **Vout**: Pin 2 (terhubung ke pin analog Arduino, A0)
- **GND**: Pin 3 (ground Arduino)

### 5. Prosedur Praktikum

Langkah-langkah yang dilakukan dalam praktikum ini adalah sebagai berikut:
1. Persiapkan peralatan praktikum, yaitu Arduino Uno, kabel USB, sensor suhu LM35, breadboard, dan kabel jumper.
2. Buka Arduino IDE pada laptop dan buat source code untuk membaca nilai dari sensor suhu LM35.
3. Sambungkan rangkaian sensor suhu LM35 ke board Arduino sesuai dengan gambar rangkaian.
4. Upload program ke Arduino board menggunakan kabel USB.
5. Amati hasil pembacaan suhu yang ditampilkan di serial monitor Arduino.

### 6. Screenshot Prosedur Praktikum

![prosedur1](https://github.com/user-attachments/assets/e4ca3bc8-efbc-4cdd-9e9e-6653c79d3ed7)
![prosedur 2](https://github.com/user-attachments/assets/dab6f77e-e6d1-4b55-80e8-e13ba76c2469)



### 7. Source Code Arduino

Berikut adalah contoh source code untuk membaca nilai suhu dari sensor LM35 dan menampilkannya pada Serial Monitor:

```cpp
// Mendeklarasikan pin untuk sensor LM35
const int LM35Pin = A0;

void setup() {
  // Mulai komunikasi serial dengan baud rate 9600
  Serial.begin(9600);
}

void loop() {
  // Membaca nilai analog dari pin A0
  int sensorValue = analogRead(LM35Pin);
  
  // Menghitung suhu dalam derajat Celsius
  float voltage = sensorValue * (5.0 / 1023.0);  // Konversi nilai sensor ke tegangan
  float temperature = voltage * 100;  // LM35 output 10 mV/°C, jadi kalikan dengan 100
  
  // Menampilkan hasil suhu pada Serial Monitor
  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");
  
  // Delay 1 detik sebelum pembacaan berikutnya
  delay(1000);
}

