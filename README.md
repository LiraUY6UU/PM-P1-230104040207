# Praktikum 1: Environment Setup & Hello World

**Mata Kuliah:** Mobile Programming  
**Dosen:** Muhayat, M.IT  
**Institusi:** UIN Antasari Banjarmasin  

---

## 👤 Profil Mahasiswa
| Item | Detail |
| :--- | :--- |
| **Nama** | Lira Anggraini |
| **NIM** | [230104040207] |
| **Kelas** | [TI23A] |

---

## 📝 Deskripsi Tugas
Repositori ini berisi hasil pengerjaan **Tugas Kecil 1.1** dan **Tugas Kecil 1.2** dari Modul Praktikum 1. Tujuan utama dari praktikum ini adalah memahami struktur dasar proyek Android, penggunaan XML untuk tampilan, dan logika dasar menggunakan Kotlin.

---

## 📂 Tugas Kecil 1.1: Modifikasi Hello World
**Tujuan:** Mengubah teks default "Hello World" menjadi "Halo [Nama Anda]".

### Metode Pengerjaan
Terdapat dua opsi yang dikerjakan dalam tugas ini:
1.  **Opsi A (Static XML):** Mengubah atribut `android:text` secara langsung pada file `activity_main.xml`. Metode ini cocok untuk teks yang tidak perlu berubah-ubah.
2.  **Opsi B (Dynamic Kotlin):** Membiarkan XML kosong atau default, lalu mengubah teks menggunakan kode Kotlin di `MainActivity.kt`. Ini memberikan fleksibilitas untuk mengubah konten secara dinamis.

**Hasil:**
Aplikasi menampilkan teks sapaan sesuai nama mahasiswa saat dijalankan di Emulator/HP.

---

## 📂 Tugas Kecil 1.2: Aplikasi Interaktif (Toggle Button)
**Tujuan:** Membuat aplikasi sederhana yang dapat merespons interaksi tombol (Click Event).

### Skenario Aplikasi:
1.  **Tampilan Awal:** Menampilkan TextView dengan tulisan **"Halo [Nama]"**.
2.  **Interaksi:** User menekan tombol **"Klik Saya"**.
3.  **Respon 1:** Teks berubah menjadi **"Selamat Datang di Perkuliahan Mobile Programming"**.
4.  **Respon 2:** Jika tombol ditekan kembali, teks kembali menjadi **"Halo [Nama]"**.
5.  **Loop:** Teks akan terus berganti setiap kali tombol ditekan.

### 💻 Implementasi Kode

#### 1. Layout XML (`activity_main.xml`)
Menggunakan `LinearLayout` dengan orientasi vertikal, berisi satu `TextView` (id: `tvMessage`) dan satu `Button` (id: `btnToggle`).

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="[http://schemas.android.com/apk/res/android](http://schemas.android.com/apk/res/android)"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="16dp">

    <TextView
        android:id="@+id/tvMessage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Halo Lira Anggraini"
        android:textSize="24sp"
        android:textStyle="bold"
        android:gravity="center"
        android:layout_marginBottom="20dp"/>

    <Button
        android:id="@+id/btnToggle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Klik Saya"/>
</LinearLayout>
```

#### 2. Logika Kotlin (MainActivity.kt)
Menggunakan variabel flag isHalo untuk mengecek status teks saat ini dan mengubahnya menggunakan setOnClickListener .

```Kotlin
package com.example.helloworldapp

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.TextView

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Inisialisasi komponen UI
        val tvMessage = findViewById<TextView>(R.id.tvMessage)
        val btnToggle = findViewById<Button>(R.id.btnToggle)

        // Variabel penanda status (Flag)
        var isHalo = true

        // Event Klik Tombol
        btnToggle.setOnClickListener {
            if (isHalo) {
                // Ubah ke pesan selamat datang
                tvMessage.text = "Selamat Datang di Perkuliahan Mobile Programming"
                isHalo = false
            } else {
                // Kembalikan ke sapaan nama
                tvMessage.text = "Halo Lira Anggraini"
                isHalo = true
            }
        }
    }
}
```
---
## 📸 Screenshot Hasil
### Tugas kecil 1.1
<img width="1080" height="2400" alt="Screenshot_20260105_053943" src="https://github.com/user-attachments/assets/980eb7ab-4de3-43ee-8859-7b06313bde19" />
### Tugas kecil 1.2
<img width="1080" height="2400" alt="Screenshot_20260105_054257" src="https://github.com/user-attachments/assets/b141e46d-e490-4e0b-95db-309af78a4ab6" />
<img width="1080" height="2400" alt="Screenshot_20260105_054306" src="https://github.com/user-attachments/assets/ac3ed24c-dd7e-480c-b586-f337d2ab8848" />

---
*Dibuat untuk memenuhi tugas Praktikum Mobile Programming.*
