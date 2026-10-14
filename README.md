# 🧮 Aplikasi Kalkulator Desktop (Java NetBeans)

Aplikasi **Kalkulator Sederhana** berbasis desktop yang dibangun menggunakan **Apache NetBeans IDE** dengan memanfaatkan **Java Swing (JFrame Form)**. Proyek ini dirancang untuk memenuhi tugas praktikum Pemrograman Berorientasi Objek (PBO) / Java Dasar.

---

## 🚀 Fitur Utama

Aplikasi ini mendukung operasi aritmatika dasar dan kontrol input standar:
* **Penjumlahan (`+`)** - Menambahkan dua bilangan.
* **Pengurangan (`-`)** - Mengurangi bilangan pertama dengan bilangan kedua.
* **Perkalian (`×`)** - Mengalikan dua bilangan.
* **Pembagian (`÷`)** - Membagi bilangan dengan penanganan *error* pembagian nol (`0`).
* **Clear (`C`)** - Menghapus seluruh tampilan layar kembali ke nol.

---

## 🛠️ Spesifikasi & Teknologi

* **Bahasa Pemrograman:** Java (JDK 8 / 11 / 17 atau versi terbaru)
* **IDE:** Apache NetBeans IDE
* **Framework GUI:** Java Swing / AWT (`javax.swing.*`)
* **Sistem Build:** Apache Ant / Maven / Gradle *(sesuaikan dengan proyek Anda)*

---

## 📂 Struktur Proyek

Berikut adalah gambaran folder proyek di dalam NetBeans:

```text
KalkulatorApp/
│
├── nbproject/                  # Konfigurasi internal proyek NetBeans
├── src/                        # Source code utama aplikasi
│   └── kalkulator/
│       ├── MainCalculator.java # File kode program utama (JFrame Form)
│       └── MainCalculator.form # Layout visual GUI dari NetBeans Designer
├── build.xml                   # Script build otomatis (Apache Ant)
└── README.md                   # Dokumentasi proyek (File ini)
```

---

## 💻 Cara Menjalankan Proyek

Ikuti langkah-langkah berikut untuk membuka dan menjalankan aplikasi di komputer Anda:

### 1. Prasyarat
* Pastikan Anda sudah menginstal **Java Development Kit (JDK)**.
* Pastikan Anda sudah menginstal **Apache NetBeans IDE**.

### 2. Impor Proyek ke NetBeans
1. Buka **Apache NetBeans IDE**.
2. Pilih menu **File > Open Project...** di pojok kiri atas.
3. Cari dan pilih direktori folder `KalkulatorApp` ini, lalu klik tombol **Open Project**.

### 3. Menjalankan Aplikasi
1. Pada panel **Projects** di sebelah kiri, buka folder `Source Packages` -> package `kalkulator`.
2. Klik kanan pada file `MainCalculator.java`.
3. Pilih opsi **Run File** (atau gunakan pintasan keyboard **Shift + F6**).

---

## 📝 Contoh Implementasi Logika

Potongan kode di bawah ini menunjukkan logika penanganan tombol operasi matematika pada aplikasi:

```java
private void btnHitungActionPerformed(java.awt.event.ActionEvent evt) {                                         
    try {
        double angka1 = Double.parseDouble(txtAngka1.getText());
        double angka2 = Double.parseDouble(txtAngka2.getText());
        double hasil = 0;

        switch (operasi) {
            case "+": hasil = angka1 + angka2; break;
            case "-": hasil = angka1 - angka2; break;
            case "*": hasil = angka1 * angka2; break;
            case "/": 
                if (angka2 == 0) {
                    throw new ArithmeticException("Tidak bisa dibagi 0");
                }
                hasil = angka1 / angka2; 
                break;
        }
        txtHasil.setText(String.valueOf(hasil));
    } catch (NumberFormatException e) {
        JOptionPane.showMessageDialog(this, "Input harus berupa angka!", "Error", JOptionPane.ERROR_MESSAGE);
    } catch (ArithmeticException e) {
        JOptionPane.showMessageDialog(this, e.getMessage(), "Error", JOptionPane.ERROR_MESSAGE);
    }
}
```

---

## 🤝 Kontribusi

Kontribusi, laporan masalah (*issues*), dan usulan fitur baru sangat terbuka untuk proyek ini:
1. *Fork* repository ini.
2. Buat *branch* fitur baru Anda (`git checkout -b fitur-keren`).
3. Lakukan *commit* perubahan Anda (`git commit -m 'Menambahkan fitur keren'`).
4. *Push* ke *branch* tersebut (`git push origin fitur-keren`).
5. Buat *Pull Request* baru.

---

## 👤 Identitas Pengembang

* **Nama:** [Nama Lengkap Anda]
* **NIM:** [Nomor Induk Mahasiswa Anda]
* **Kelas:** [Kelas / Program Studi Anda]
* **Kontak:** [Email atau Media Sosial Anda]
