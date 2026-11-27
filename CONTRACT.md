# CONTRACT — Character Manager v0.7

## 1. Model (milik: Veva Br Tarigan)
Package: com.unpri.charactermanager.model

| Class            | Anggota yang dipakai Controller                          |
|------------------|----------------------------------------------------------|
| Character        | new Character(name, type, level) -> IllegalArgumentException |
|                  | jika nama kosong / type null / level di luar 1-99        |
|                  | getName(), getType(), getLevel(), getHitPoints(),        |
|                  | getAttackPower()                                         |
| CharacterType    | enum (sama persis dengan v0.6)                           |
| CharacterManager | boolean addCharacter(Character)  (false jika duplikat)   |
|                  | ArrayList getAllCharacters()  (salinan)       |
|                  | int getTotalCharacters()                                 |
|                  | boolean isNameTaken(String)                              |
|                  | double getAverageLevel()  (0 bila kosong)                |

Kebutuhan Controller -> method Model (hanya ini yang dipakai):
| Kebutuhan                    | Method                              |
|------------------------------|-------------------------------------|
| Tolak nama dobel             | isNameTaken(name)                   |
| Buat karakter dari input     | new Character(name, type, level)    |
| Simpan                       | addCharacter(c)                     |
| Gambar kartu                 | getAllCharacters() + getter Character |
| Bar status: jumlah           | getTotalCharacters()                |
| Bar status: rata-rata level  | getAverageLevel()                   |

Aturan: model TIDAK mengimpor javafx.* maupun javax.swing.*.
Model v0.6 tidak diubah, kecuali menambah getAverageLevel() bila belum ada.

## 2. View / FXML (milik: Abil Febrian Panggabean)
Berkas: src/main/resources/com/unpri/charactermanager/view/CharacterView.fxml
fx:controller = com.unpri.charactermanager.view.CharacterController

| fx:id          | Tipe node  | Fungsi                                  |
|----------------|------------|-----------------------------------------|
| nameField      | TextField  | Input nama (onAction = #handleSave)     |
| typeCombo      | ComboBox   | Pilihan CharacterType                   |
| levelSpinner   | Spinner    | Input level                             |
| messageLabel   | Label      | Pesan error / sukses                    |
| cardsBox       | VBox       | Wadah kartu karakter                    |
| countLabel     | Label      | Jumlah karakter                         |
| avgLevelLabel  | Label      | Rata-rata level                         |
| statusLabel    | Label      | Ringkasan status di bar bawah           |

| Tombol | onAction       |
|--------|----------------|
| Simpan | #handleSave    |
| Reset  | #handleReset   |

## 3. Controller (milik: Natanael Lata Saro Agassi Zebua)
Class: com.unpri.charactermanager.view.CharacterController

| Method                           | Keterangan                                   |
|----------------------------------|----------------------------------------------|
| initialize()                     | Isi typeCombo, atur Spinner                  |
| setManager(CharacterManager)     | Dipanggil oleh CharacterManagerApp           |
| handleSave()                     | Baca input -> Model -> refreshList()         |
| handleReset()                    | Kosongkan input dan pesan                    |
| refreshList()                    | Bangun ulang kartu + countLabel + avgLevelLabel |

## 4. Aturan Perubahan
- Mengubah nama fx:id / method WAJIB lewat PR yang di-approve ketiga anggota.
- PR yang mengubah kontrak diberi label "contract".