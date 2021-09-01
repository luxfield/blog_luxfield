---
title: "Fungsi callable() python"
date: 2021-09-01T08:46:04+07:00
draft: false
Author: "Surya Efendi"
Description: "Fungsi callable pada python akan mengembalikan nilai `True` jika objek yang menjadi argumennya dapat dipanggil, jika tidak maka akan mengembalikan nilai `False`"
---

## Deskripsi

Fungsi callable pada python akan mengembalikan nilai `True` jika objek yang menjadi argumennya dapat dipanggil, jika tidak maka akan mengembalikan nilai `False`

---

## Syntax

Fungsi callable() memiliki sintaks sebagai berikut:

```python
callable(object)
```

---

## Parameter

- object – objek yang akan diuji apakah bisa dipanggil atau tidak

---

## Nilai Kembalian

Fungsi callable() akan mengembalikan:

- `True` -- jika objek bisa dipanggil
- `False` -- jika objek tidak bisa dipanggil

> Perlu dicatat bahwa meskipun kembalian dari callable() adalah True, bisa saja pemanggilan terhadap objek masih gagal.
>
> Tapi, saat kembaliannya False, maka sudah pasti pemanggilan terhadap objek tersebut akan gagal.
>
> Perhatikan bahwa `Class` dapat dipanggil (memanggil `Class` akan mengembalikan sebuah fungsi) fungsi adalah callable jika `Class`-nya memiliki fungsi `__call__()`

---

## Contoh

```python
a:int = 10
print(callable(x))

def hello()->None:
    print("Hello World")

b = hello
print(callable(b))

class kelas:
    def fungsi()->None:
        print("Hello World")

print(callable(kelas))
```

---

Output

Output dari program di atas adalah seperti berikut:

```python
False
True
True
```
