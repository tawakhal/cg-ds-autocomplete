
# Autocomplete (CodeGeeX + DeepSeek R1)

Proyek ini adalah experiment antara **CodeGeeX** dan **DeepSeek R1** untuk mencoba membangum autocomplete, yg tujuannya itu untuk :
1. Menyediakan autocomplete. (pake codegeex)
2. Memberikan rekomendasi snippet atau fungsi berdasarkan konteks kode. (pake deepseek)

---

## 📂 Struktur Folder
```
cg-ds-autocomplete/
├── CodeGeeX/              # Folder hasil clone CodeGeeX
├── DeepSeek-R1/           # Folder hasil clone DeepSeek R1
├── api_gateway.py         # File API Gateway untuk menghubungkan kedua AI
├── venv/                  # Virtual environment (opsional)
├── requirements.txt       # Dependencies (opsional)
└── README.md              # Dokumentasi proyek ini
```

---

## 🚀 Cara Install dan Jalankan
### 1. Clone Repo CodeGeeX dan DeepSeek R1
```bash
git clone https://github.com/THUDM/CodeGeeX.git
git clone https://github.com/deepseek-ai/DeepSeek-R1.git
```

### 2. Install Dependency
```bash
pip install -r CodeGeeX/requirements.txt
pip install -r DeepSeek-R1/requirements.txt
pip install flask requests  # Untuk API Gateway
```

### 3. Jalankan CodeGeeX dan DeepSeek R1
```bash
# Jalankan CodeGeeX
cd CodeGeeX
python run.py --model_path ./model

# Jalankan DeepSeek R1
cd ../DeepSeek-R1
python server.py
```

### 4. Jalankan API Gateway
```bash
cd ../
python api_gateway.py
```

API Gateway akan berjalan di: **http://localhost:8080**

---

## 🔄 Cara Menggunakan
### Contoh Request
**Endpoint:** `http://localhost:8080/autocomplete`  
**Method:** `POST`  
**Payload:**
```json
{
  "code": "def find_max("
}
```

### Contoh Response
```json
{
  "codegeex": "def find_max(nums):",
  "deepseek": [
    "def find_max(numbers):",
    "def find_maximum(arr):"
  ]
}
```

---

## 🛠️ Customisasi dan Rebranding
1. Ubah nama API di `api_gateway.py` agar terlihat seperti buatan sendiri.
2. Ganti nama dan deskripsi di `package.json` untuk VS Code extension.

---

## 📋 To-Do
- [ ] Fine-tuning CodeGeeX dengan dataset spesifik.
- [ ] Optimasi performa di Mac OS.
- [ ] Integrasi tambahan untuk code search.

---

## 📞 Kontak
Jika ada pertanyaan, silakan hubungi [email@example.com](mailto:email@example.com).

Happy Coding! 🚀
