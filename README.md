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
<img src="Img/1.png" width="300"><br>
<b>Biner Class</b><br>
Distribusi data training <i>Others</i> dan <i>Non-Others</i>. 
Eksperimen ini bertujuan untuk memisahkan data relevan dan tidak relevan terhadap topik <i>Slow Life</i>.
</td>

<td align="center">
<img src="Img/2.png" width="300"><br>
<b>Multi Class</b><br>
Distribusi data training <i>Positif</i>, <i>Negatif</i>, dan <i>Netral</i> 
dengan memisahkan kategori kelas other.
</td>

<td align="center">
<img src="Img/3.png" width="300"><br>
<b>Multi Class (Data Original)</b><br>
Distribusi kelas <i>Positif</i>, <i>Negatif</i>, <i>Netral</i>, dan <i>Others</i> 
Menggunakan data Original (Imbalance).
</td>

<td align="center">
<img src="Img/4.png" width="300"><br>
<b>Multi Class (Data Augmentation)</b><br>
Distribusi kelas <i>Positif</i>, <i>Negatif</i>, <i>Netral</i>, dan <i>Others</i> 
Setelah dilakukan penyeimbangan data (Balance) menggunakan teknik augmentasi (Synonym Replacement dengan memanfaatkan model bahasa XLM-RoBERTa).
</td>
</tr>
</table>

</div>

---
