# nmap-cheat-sheet
This repository provides a comprehensive cheat sheet for using Nmap, a powerful network scanning tool.

### Dasar Nmap Scanning
1. **Scan cepat untuk semua port yang umum digunakan:**
   ```bash
   nmap -F <target>
   ```

2. **Scan spesifik untuk semua 65535 port:**
   ```bash
   nmap -p- <target>
   ```

3. **Scan spesifik untuk satu atau beberapa port tertentu:**
   ```bash
   nmap -p <port1,port2,...> <target>
   ```

4. **Scan semua port dari 1 hingga 65535:**
   ```bash
   nmap -p 1-65535 <target>
   ```

### Deteksi Versi Layanan dan OS
1. **Deteksi versi layanan yang berjalan di port yang terbuka:**
   ```bash
   nmap -sV <target>
   ```

2. **Deteksi versi layanan di port spesifik:**
   ```bash
   nmap -sV -p <port1,port2,...> <target>
   ```

3. **Deteksi OS yang digunakan target:**
   ```bash
   nmap -O <target>
   ```

### Scan Khusus untuk Port SSH yang Telah Diubah
1. **Scan cepat untuk port yang umumnya digunakan oleh SSH:**
   ```bash
   nmap -p 22,2222,22222 <target>
   ```

2. **Scan untuk menemukan port SSH yang mungkin telah diubah:**
   ```bash
   nmap -p 1-65535 --open -sV --script=ssh-hostkey <target>
   ```

### Scan dengan Pilihan Tambahan
1. **Scan tanpa melakukan ping terlebih dahulu:**
   ```bash
   nmap -Pn <target>
   ```

2. **Scan dengan informasi yang lebih detail:**
   ```bash
   nmap -A <target>
   ```

3. **Scan dengan menampilkan output dalam format grep (untuk parsing lebih lanjut):**
   ```bash
   nmap -oG <outputfile> <target>
   ```

### Contoh Penggunaan
1. **Mencari port SSH yang telah diubah:**
   ```bash
   nmap -p 1-65535 -sV --script=ssh-hostkey <target>
   ```

2. **Scan cepat pada semua port umum:**
   ```bash
   nmap -F <target>
   ```

3. **Scan spesifik pada port 22 dan 2222:**
   ```bash
   nmap -p 22,2222 <target>
   ```

### Tips
- Ganti `<target>` dengan IP atau hostname dari server yang ingin Anda scan.
- Gunakan `-v` (verbose) untuk output yang lebih detail saat scanning:
  ```bash
  nmap -v -p- <target>
  ```
- Simpan hasil scan ke file untuk analisis lebih lanjut:
  ```bash
  nmap -oN output.txt -p 1-65535 <target>
  ```

Dengan cheat sheet ini, Anda dapat melakukan scanning menggunakan Nmap untuk menemukan port spesifik, termasuk port SSH yang telah diubah.
