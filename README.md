# Character Manager FX v0.7 — Kelompok 8

Migrasi Character Manager dari Swing (v0.6) ke JavaFX + FXML (v0.7).
Mata Kuliah Java Visual (SIH-6406) · UNPRI Prodi Sistem Informasi.

## Anggota dan Peran
| Nama | NIM | Peran | Username GitHub | Branch |
|------|-----|-------|-----------------|--------|
| [Veva Br Tarigan] | [253303621280] | Model Manager      | [vevatarigan] | feature/model |
| [Abil Febrian Panggabean] | [253303621266] | View Manager       | [abilgaming01811-oss] | feature/view |
| [Natanael Lata Saro Agassi Zebua] | [253303621260] | Controller Manager | [natanaelzebua] | feature/controller |

## Teknologi
Java 17 · JavaFX 21 · Maven · Scene Builder · VS Code

## Cara Menjalankan
    git clone [url-repo]
    cd [nama-repo]
    mvn javafx:run

## Struktur Project
    src/main/java/com/unpri/charactermanager/
      CharacterManagerApp.java
      model/       (Model Manager)
      view/        (CharacterController — Controller Manager)
    src/main/resources/com/unpri/charactermanager/view/
      CharacterView.fxml   (View Manager)

## Alur MVC (tombol Simpan)
View (klik Simpan) -> Controller.handleSave() -> Model.addCharacter()
-> Controller.refreshList() -> View (kartu dan bar status diperbarui)

## Screenshot
![Aplikasi kosong](docs/01-kosong.png)
![Aplikasi berisi data](docs/02-data.png)
![Pesan error validasi](docs/03-error.png)
![Scene Builder](docs/04-scene-builder.png)

## Bukti Model Bersih
Perintah: grep -rn "javafx\|javax.swing" src/main/java/com/unpri/charactermanager/model
Hasil: (kosong)

## Tabel Uji
| No | Input | Hasil diharapkan | Hasil nyata | Lapisan yang menangkap |
|----|-------|------------------|-------------|------------------------|
| 1  | Nama kosong   | Pesan "Nama wajib diisi" | [isi] | Model / Controller |
| 2  | Level 0       | Pesan level tidak valid  | [isi] | [isi] |
| ...| ...           | ...                      | ...   | ...   |
| 10 | [kasus sendiri] | [isi]                  | [isi] | [isi] |

## Kolaborasi Git
- Merge strategy: [Squash and merge / Merge commit]
- Pull Request yang sudah merged:
  - [PR #1 judul](url)
  - [PR #2 judul](url)
  - [PR #3 judul](url)

## Pembagian Kerja (jika kelompok 2 orang, tulis perangkapan peran)
[uraian singkat]

## Analisis Individu (Google Docs, Bagian E di AP22)
- [Nama 1]: [link]
- [Nama 2]: [link]
- [Nama 3]: [link]