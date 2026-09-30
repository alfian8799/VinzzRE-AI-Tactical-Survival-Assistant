VinzzRE: AI Tactical Survival Assistant

VinzzRE asisten AI interaktif berbasis *Retrieval-Augmented Generation* (RAG) yang dirancang khusus untuk mendampingi pemain gim taktis *survival-horror* seperti *Resident Evil*. Masalah utama yang diselesaikan adalah kesulitan pemain dalam mencari panduan (*walkthrough*), solusi teka-teki (*puzzle*), dan strategi *boss* yang sering kali terpencar, tidak terstruktur, atau memakan waktu lama di internet. Pengguna utama proyek ini adalah para pemain gim, kreator konten, dan penggemar strategi digital yang membutuhkan referensi instan. Solusi bekerja dengan cara mengindeks dokumen panduan resmi ke dalam basis data vektor, sehingga agen AI dapat memproses pertanyaan pengguna dan memberikan jawaban taktis yang akurat secara real-time. Manfaat utamanya adalah meningkatkan efisiensi waktu bermain, melatih kemampuan pemecahan masalah (*problem-solving*), serta mengoptimalkan manajemen sumber daya dalam permainan tanpa risiko halusinasi data.

### **Problem Statement**

Masalah spesifik yang diselesaikan adalah tingginya tingkat frustrasi dan inefisiensi waktu yang dialami pemain saat menghadapi rintangan sulit dalam gim, seperti teka-teki rumit dan pertarungan *boss* berseri. Sebelum adanya solusi ini, pemain harus keluar dari gim (*tab-out*) untuk membaca panduan teks yang panjang atau menonton video yang memakan waktu. *Pain point* utamanya adalah informasi sering kali tidak spesifik dan lambat diakses. Masalah ini penting diselesaikan karena menguji bagaimana teknologi AI generatif dapat dimanfaatkan untuk manajemen literasi dokumen instan dan pelatihan strategi kognitif berbasis teks.

### **Target User**

- Gamers / pemain gim taktis
- Kreator konten / video editor *gaming*
- Komunitas penggemar *survival-horror*
- Pelajar dan individu yang melatih keterampilan logika serta pemecahan masalah berbasis skenario

### **Mengapa Solusi Ini Dibutuhkan?**

Solusi ini jauh lebih baik dibandingkan pencarian web konvensional karena pengguna tidak perlu menyaring informasi dari berbagai tautan iklan atau forum yang tidak akurat. VinzzRE memberikan jawaban langsung secara instan, terstruktur dalam bentuk poin-poin taktis, dan dijamin valid karena bersumber langsung dari dokumen panduan (*survival guide*) terpercaya yang telah diunggah ke dalam sistem.

### **Fitur Utama Project**

- **Document Analysis (RAG Search):** Menganalisis dan mencari informasi spesifik dari dokumen panduan PDF secara semantik menggunakan basis data vektor.
- **AI Tactical Guidance:** Menyediakan strategi *boss*, solusi kode brankas, dan urutan eksplorasi secara akurat.
- **Anti-Hallucination Guardrail:** Sistem diatur dengan instruksi ketat untuk menolak menjawab apabila informasi tidak ditemukan dalam dokumen, guna menjaga integritas data.
- **Structured Output Generation:** Menampilkan jawaban dalam format poin-poin (*bullet points*) yang ringkas dan mudah dibaca saat pengguna sedang bermain.

### **Alur Penggunaan Project**

User Input (Chat) → IBM Bob (Interface) → Langflow (Workflow & Astra DB Retrieval) → AI Processing (LLM + Prompt Template) → Output (Structured Response) → User Action

### **Penggunaan IBM Langflow**

IBM Langflow digunakan sebagai pusat *workflow* visual untuk membangun sistem RAG secara menyeluruh. *Flow* dibagi menjadi dua bagian utama: pengunggahan dokumen (*Read File* ➔ *Split Text* ➔ *Astra DB*) dan pemrosesan kueri (*Chat Input* ➔ *Astra DB Vector Store* ➔ *Parser* ➔ *Prompt Template* ➔ *Language Model* ➔ *Chat Output*). Langflow berfungsi sebagai mesin utama yang mengekstrak teks, melakukan *embedding*, mencocokkan konteks semantik, dan menghasilkan respons terstruktur berdasarkan templat instruksi agen taktis.

### **Penggunaan IBM Bob**

IBM Bob digunakan sebagai lapisan antarmuka pengguna akhir (*user-facing conversation*). Melalui IBM Bob, pengguna dapat menjalankan interaksi obrolan secara langsung, memilih *tools* atau fungsionalitas agen yang tepat, serta membaca penjelasan taktis yang dikirimkan oleh sistem dalam format yang ramah pengguna.

### **Bagaimana IBM Langflow dan IBM Bob Terintegrasi?**

IBM Langflow bertindak sebagai pengendali logika di balik layar (*backend orchestration*) yang memproses kueri, melakukan pencarian vektor ke Astra DB, dan mengeksekusi instruksi LLM, sementara IBM Bob bertindak sebagai jembatan antarmuka interaktif yang menerima masukan ketikan pengguna. Data atau informasi berpindah ketika pengguna mengirimkan pesan di IBM Bob, yang kemudian diteruskan ke *endpoint* alur kerja Langflow untuk diproses oleh agen RAG, dan hasil akhirnya dikembalikan ke layar obrolan IBM Bob sebagai respons teks terstruktur.