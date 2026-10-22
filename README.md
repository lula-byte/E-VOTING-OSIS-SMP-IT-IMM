# E-Voting OSIS IM Maos 2026-2027

## Pemasangan
1. script.google.com > Proyek baru. Salin `Code.gs` dan buat file HTML bernama `Index` (isi dari `Index.html`).
2. Pengaturan Proyek > centang "Tampilkan file manifes appsscript.json", lalu samakan isinya.
3. Jalankan fungsi `setupDatabase` sekali (setujui izin Sheets dan Drive). Spreadsheet dan folder Drive otomatis dibuat.
4. Pengaturan Proyek > Properti Skrip: ubah `ADMIN_PASSWORD` (min. 8 karakter). Jangan ubah `PEPPER` setelah token dibuat.
5. Deploy > Aplikasi web > Jalankan sebagai: Saya; Akses: Siapa saja. Bagikan URL /exec.
6. Admin: login, tambah 2-3 kandidat, buat token & cetak kupon, lalu Mulai Pemilihan.
7. GitHub: push folder ini (opsional pakai `clasp`). Jangan commit password, pepper, atau data suara.

## Catatan keamanan
- Jangan bagikan spreadsheet database. Ubah kode (Code.gs) memerlukan deploy versi baru.
- `usedAt` di Tokens dan urutan baris di Ballots dapat menimbulkan risiko korelasi. Ballots sengaja tanpa timestamp.
- Randomness token memakai SHA-256 dari beberapa UUID, bukan CSPRNG resmi. Ini baik untuk sekolah, bukan untuk pemilihan berisiko tinggi.
- Lakukan uji TEST-001 s.d. TEST-012 pada pemilihan percobaan sebelum hari H.
