# 🎨 FlowCode Studio

**FlowCode Studio** adalah pembuat *flowchart* otomatis berbasis web (*single-file HTML*) yang mengubah kode teks ringkas (**Domain-Specific Language / DSL**) menjadi diagram alir presisi secara *real-time* dengan antarmuka bergaya Whimsical dan ekspor gambar beresolusi tinggi (**Zero-Margin HD**)[cite: 2].

---

## ✨ Fitur Utama

* **⚡ Text-to-Flowchart Real-Time:** Ketik sintaks DSL sederhana dan diagram otomatis tersusun rapi menggunakan algoritma *auto-layout*[cite: 2].
* **🖱️ Direct Canvas Editing (Two-Way Sync):**
  * **Klik Kiri:** Pilih *shape*, geser posisi dengan *smart alignment guides*, ubah ukuran lewat 8 *resize handles* (*auto text-wrap*), atau tarik kotak seleksi (*marquee multi-select*)[cite: 2].
  * **Klik Kanan:** *Free-hand panning* untuk menggeser kanvas ke segala arah dengan leluasa[cite: 2].
  * **Scroll / Pinch:** *Zoom In–Out* kanvas (25% – 300%)[cite: 2].
  * **Klik Ganda & Geser Label:** Edit teks simbol langsung di kanvas atau geser lencana `Ya` / `Tidak` mengikuti jalur panah[cite: 2].
* **📸 Zero-Margin Copy HD & Export:** Salin langsung ke *clipboard* (JPG/PNG 3x & 4x Ultra HD) tanpa ruang kosong berlebih, siap tempel ke Word, Docs, atau PPT[cite: 2].

---

## 📖 Referensi Sintaks DSL FlowCode Studio

Setiap baris kode merepresentasikan alur hubungan antar-simbol menggunakan konektor `->` atau `--Label-->`[cite: 1, 2]:

| Awalan / Sintaks | Bentuk Simbol | Fungsi Standar Flowchart | Contoh Penggunaan |
| :--- | :--- | :--- | :--- |
| `[Teks]` | **Oval / Kapsul** (*Terminator*) | Titik mulai atau selesai program | `[Mulai]`, `[Selesai]` |
| `I:` / `O:` | **Jajargenjang** (*Input/Output*) | Memasukkan data atau menampilkan hasil | `I: Input nilai`, `O: Output hasil` |
| `P:` | **Persegi Panjang** (*Process*) | Perhitungan, operasi, atau pemberian nilai | `P: total = a + b` |
| `D:` | **Belah Ketupat** (*Decision*) | Percabangan logika / kondisi (`Ya`/`Tidak`) | `D: nilai >= 75?` |
| `S:` | **Kotak Garis Ganda** (*Subprocess*) | Pemanggilan fungsi atau subprogram | `S: HitungRataRata()` |
| `M:` | **Trapesium** (*Manual Input*) | Input manual dari pengguna/keyboard | `M: Masukkan PIN` |
| `DOC:` | **Dokumen** (*Document*) | Pencetakan laporan atau berkas | `DOC: Cetak Struk` |
| `DB:` | **Silinder** (*Database*) | Penyimpanan atau pembacaan basis data | `DB: Simpan ke tabel_user` |
| `C:` | **Lingkaran Kecil** (*Connector*) | Titik penghubung alur di halaman yang sama | `C: A` |
| `->` / `--Label-->` | **Panah** (*Arrows*) | Arah aliran proses & label cabang | `A --Ya--> B`, `A --Tidak--> C` |

> **💡 Konsep ID Referensi:** Untuk membuat perulangan (*loop*) atau menyambungkan beberapa cabang ke satu simbol yang sama, beri nama ID di depan definisi simbol (contoh: `cek_loop: D: i <= N?`), lalu panggil kembali ID tersebut di baris berikutnya (`inc -> cek_loop`)[cite: 1, 2].

---

## 🤖 Cara Menerapkan DSL FlowCode ke Berbagai AI (ChatGPT, Gemini, Claude, DeepSeek)

Anda dapat menyuruh AI mana pun untuk mengubah soal algoritma, kode program (C, Python, Java, dll.), atau alur bisnis menjadi kode DSL **FlowCode Studio** secara instan.

### 1. Metode Copy-Paste Prompt (Untuk Semua AI)
Salin blok **Master Prompt** di bawah ini, tempelkan ke chat AI pilihan Anda, lalu tambahkan soal atau kode program Anda di bagian paling bawah:

```text
Bertindaklah sebagai generator kode DSL untuk aplikasi "FlowCode Studio". 
Ubah soal algoritma / kode program / alur kerja yang saya berikan menjadi sintaks DSL FlowCode Studio dengan aturan ketat berikut:

1. FORMAT SIMBOL:
   - Terminator (Mulai/Selesai): [Mulai] dan [Selesai]
   - Input / Output: awali dengan "I: " atau "O: " (contoh: I: Input N, O: Output total)
   - Proses / Perhitungan: awali dengan "P: " (contoh: P: i = 1, total = 0)
   - Keputusan / Percabangan: awali dengan "D: " dan akhiri tanda tanya (contoh: D: i <= N?)
   - Subproses / Fungsi: awali dengan "S: "
   - Manual Input: awali dengan "M: "
   - Dokumen: awali dengan "DOC: "
   - Database: awali dengan "DB: "
   - Konektor: awali dengan "C: "

2. KONEKTOR & PERCABANGAN:
   - Alur lurus gunakan: SimbolA -> SimbolB
   - Percabangan Decision gunakan: id_decision --Ya--> SimbolJikaYa dan id_decision --Tidak--> SimbolJikaTidak

3. ATURAN ID & PERULANGAN (LOOP):
   - Berikan ID unik (huruf kecil tanpa spasi) sebelum titik dua untuk simbol yang akan dituju ulang, contoh:
     cek_loop: D: i <= N?
   - Saat memanggil kembali ID tersebut untuk loop atau penggabungan cabang, tulis ID-nya saja tanpa mengulang prefiks/teksnya (contoh: inc -> cek_loop).
   - Jangan gunakan ID yang sama untuk dua simbol berbeda.

4. OUTPUT:
   - Berikan HANYA kode DSL di dalam satu blok kode teks (```text ... ```) tanpa penjelasan panjang agar langsung bisa di-copy ke FlowCode Studio.

Berikut soal/kode yang harus dibuatkan DSL-nya:
[TEMPEL SOAL ATAU KODE PROGRAM ANDA DI SINI]
