<div align="center">
    <img src="Img/slowlife.jpg" width="350">
    
</div>

# <div align="center">**Analisis Sentimen Gaya Hidup *Slow Live* pada Media Sosial Twitter (X)**</div>

<p align="center">
Gambar di atas merupakan kerangka konsep gaya hidup <i>Slow Life</i> yang menjadi dasar analisis dalam penelitian ini.
</p>

---

## 📌 Latar Belakang

Perkembangan media sosial, khususnya Twitter (X), menjadi ruang diskusi publik mengenai berbagai fenomena sosial, termasuk tren gaya hidup <i>Slow Life</i>. Konsep ini menekankan pada kehidupan yang lebih sadar, tenang, dan bermakna di tengah budaya serba cepat.

Penelitian ini bertujuan untuk menganalisis bagaimana sentimen masyarakat terhadap gaya hidup <i>Slow Life</i> yang diekspresikan melalui tweet.

---

## 🎯 Tujuan Penelitian

1. Mengidentifikasi sentimen masyarakat terhadap gaya hidup <i>Slow Life</i>.
2. Mengklasifikasikan tweet ke dalam kategori Positif, Negatif, Netral, dan Others.
3. Membandingkan performa beberapa metode ekstraksi fitur dan model machine learning.

---

## 🧠 Metodologi Singkat

- **Sumber Data**: Twitter (X)
- **Tahapan**:
  - Data Crawling (01 Jan 2020 s.d 01 Jan 2025)
  - Pelabelan Manual (Positif, Negatif, Netral, Others)
  - Preprocessing
  - Feature Extraction (BoW, N-gram, TF-IDF, IndoBERTweet)
  - Modeling & Evaluasi
- **Eksperimen**:
  - Biner Class (others dan non others)
  - Multi Class (Positif, Negatif, Netral)
  - Multi Class Data Ori/Data Aug (Positif, Negatif, Netral, Others)

---

## 📊 Distribusi Data Eksperimen

<div align="center">

<table>
<tr>
<td align="center">
<img src="Img/1.png" width="150"><br>
<b>Biner Class</b><br>
Distribusi data training <i>Others</i> dan <i>Non-Others</i>. 
Eksperimen ini bertujuan untuk memisahkan data relevan dan tidak relevan terhadap topik <i>Slow Life</i>.
</td>

<td align="center">
<img src="Img/2.png" width="150"><br>
<b>Multi Class</b><br>
Distribusi data training <i>Positif</i>, <i>Negatif</i>, dan <i>Netral</i> 
dengan memisahkan kategori kelas Other.
</td>

<td align="center">
<img src="Img/3.png" width="150"><br>
<b>Multi Class (Data Original)</b><br>
Distribusi kelas <i>Positif</i>, <i>Negatif</i>, <i>Netral</i>, dan <i>Others</i> 
Menggunakan data Original <i>Imbalance</i>.
</td>

<td align="center">
<img src="Img/4.png" width="150"><br>
<b>Multi Class (Data Augmentation)</b><br>
Distribusi kelas <i>Positif</i>, <i>Negatif</i>, <i>Netral</i>, dan <i>Others</i> 
Menggunakan teknik augmentasi <i>Synonym Replacement</i> dengan memanfaatkan model bahasa <i>XLM-RoBERTa</i>.
</td>
</tr>
</table>

</div>

---

## 🔎 Analisis Kesalahan Prediksi Model

Berikut merupakan analisis pola kesalahan spesifik yang dilakukan model, pada berbagai skenario klasifikasi:

| No | Skenario Klasifikasi | Sampel + True Label | Predict Label | Hasil Analisis |
|----|----------------------|---------------------|---------------|----------------|
| 1 | **Biner Klasifikasi** (Other vs Non-Other) | **Tweet:** @kennyivan wkwkwkwk coba diriset... efek lebaran haji ken slow life dulu… <br> **True Label:** Non-Other (Positif) | Other | Sampel ini mengandung kata kunci *“slow life”*. Model belum mampu memahami sentimen implisit yang tidak diucapkan secara langsung. Meskipun model mengenali istilah tersebut, model gagal memahami konteks perayaan pasca lebaran yang bermakna positif. |
| 2 | **Multi-kelas** (Netral, Positif, Negatif) | **Tweet:** Yo.opo se slow living iku <br> **True Label:** Netral | Negatif | Kalimat ini merupakan pertanyaan mengenai *slow living*. Model gagal mengenali bahwa frasa "yo opo se iku" menunjukkan bentuk pertanyaan, bukan keluhan atau sarkasme. |
| 3 | **Multi-kelas** (Netral, Positif, Negatif, Other) | **Tweet:** slow living tidak berlaku untuk yang hidup dalam tekanan dan tuntutan warga sekitar. <br> **True Label:** Negatif | Netral | Kalimat mengandung kata “tidak berlaku”, “tekanan”, dan “tuntutan” yang menunjukkan sentimen negatif. Namun model menganggapnya sebagai deskripsi sosial yang netral. |
| 4 | **Multi-kelas** (Netral, Positif, Negatif, Other) | **Tweet:** memang slow living di klaten tidak tergantikan <br> **True Label:** Positif | Negatif | Model salah menginterpretasikan frasa "tidak tergantikan" sebagai sentimen negatif karena terlalu fokus pada kata "tidak". Ini menunjukkan model masih kesulitan memahami makna positif yang tersirat melalui negasi. |

---
