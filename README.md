## Jawaban Soal 1
Kode akan menghasilkan error karena terdapat dua extension pada tipe String dengan nama method yang sama (toInt). Dart tidak dapat menentukan method mana yang digunakan karena return type tidak menjadi pembeda. Solusinya adalah mengganti nama method agar berbeda atau memanggil extension secara eksplisit menggunakan nama extension.
Solusi agar tidak konflik 

---
## Solusi Agar Tidak Konflik
### 1. Gunakan nama Method berbeda
   ```dart
   extension StringNumber on String {
  int toIntValue() {
    return int.parse(this);
  }
}

extension StringDouble on String {
  double toDoubleValue() {
    return double.parse(this);
  }
}

void main() {
  String angka = '123';
  print(angka.toIntValue());   // 123
  print(angka.toDoubleValue()); // 123.0
}
```

[Klik di sini untuk menjalankan kode DartPad](https://dartpad.dev/acc0afdd3989695374ed5fe29a8e2902)

### 2. Gunakan nama Extension secara explisit
Kalau tetap mau nama method sama:

   ```dart
extension StringNumber on String {
  int toInt() {
    return int.parse(this);
  }
}

extension StringDouble on String {
  double toInt() {
    return double.parse(this);
  }
}

void main() {
  String angka = '123';

  print(StringNumber(angka).toInt()); // 123
  print(StringDouble(angka).toInt()); // 123.0
}
  ```
[Klik di sini untuk menjalankan kode DartPad](https://dartpad.dev/396c6de94f081944db69a38d9633f1e3)

---











