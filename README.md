# 🌍 Global Power Plant Data Analysis using Data Warehouse

Proyek akhir mata kuliah **Data Warehouse** ini berfokus pada analisis data pembangkit listrik dunia menggunakan pendekatan **data warehouse**, **OLAP cube**, dan **komputasi terdistribusi**. Proyek ini bertujuan untuk mengeksplorasi pola konsumsi energi, efisiensi pembangkit, dan potensi kebijakan transisi energi berdasarkan data Global Power Plant.


## Tujuan Proyek

- Menganalisis distribusi pembangkit listrik berdasarkan lokasi dan jenis energi.
- Mengevaluasi efisiensi pembangkit melalui rasio kapasitas terhadap energi.
- Mengidentifikasi tren dan kontribusi jenis bahan bakar dari tahun ke tahun.
- Mendukung pengambilan keputusan energi yang lebih ramah lingkungan.

## Dataset

**Sumber:** [Global Power Plant Database - WRI](https://datasets.wri.org/dataset/globalpowerplantdatabase)

- Jumlah baris: ±34.936  
- Jumlah kolom: 36  
- Rentang waktu: 2013–2017  
- Kolom utama: `country`, `capacity_mw`, `primary_fuel`, `generation_gwh_20xx`, `estimated_generation_gwh`, dll.

## Teknologi yang Digunakan

- Python (Pandas, Atoti, Pika, SQLAlchemy)
- Atoti (OLAP Cube)
- RabbitMQ (Message Broker)
- PostgreSQL (Relational Database)
- Jupyter Notebook (Analisis dan Visualisasi)

## Alur Proyek

### 1. Preprocessing
- Pembersihan nilai kosong dan kolom tidak relevan.
- Konsolidasi energi aktual dan estimasi.
- Transformasi data dari format wide ke long.

### 2. Processing
- Pembuatan data cube multidimensi menggunakan Atoti.
- Definisi dimensi: Lokasi, Tahun, Jenis Energi.
- Pembuatan measures: Total Kapasitas, Total Energi, Jumlah Pembangkit, dll.

### 3. Post Processing
- Menjawab query analitik dengan `cube.query()`.
- Visualisasi dengan widget Atoti (scatter plot & bar chart).
- Komputasi Distribusi hasil ke RabbitMQ dan simpan ke PostgreSQL.

## Contoh Analisis

- Negara dengan total produksi energi terbesar: **USA**
- Jenis pembangkit energi dengan kapasitas rata-rata tertinggi: **Nuclear**
- Tahun dengan total energi terbesar: **2017**
- Jenis energi dominan: **Hydro** (kapasitas) dan **Biomass** (produksi)
