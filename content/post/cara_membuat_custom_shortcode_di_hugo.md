---
title: "Cara membuat custom shortcode di Hugo"
date: 2021-09-13T19:16:27+07:00
draft: false
Author: "Surya Efendi"
Description: "di Hugo untuk membuat postingan pasti menggunakan markdown style, karena file-nya ditulis dengan format markdown, lalu kalian apabila ingin menambahkan syntax html di markdown tidak bisa di render menjadi html, karena bukan markdown style,"
Cover: "/img/hugo-shortcode.png"
Toc: true
TocTitle: "Daftar Isi"
tags: ["Hugo","GoLang","web","SSG"]
---

***Cara membuat custom shortcode di Hugo*** - di Hugo untuk membuat postingan pasti menggunakan markdown style, karena file-nya ditulis dengan format markdown, lalu kalian apabila ingin menambahkan syntax html di markdown tidak bisa di render menjadi html, karena bukan markdown style,

## Shortcode Hugo

untuk itu hugo menawarkan fitur `shortcode` untuk menambahkan syntax html didalam markdown, namun `shortcode` bawaan Hugo ini terbatas, hanya syntax tertentu yang ada di `shortcode` bawaan Hugo, untuk itu kita coba buat custom `shortcode` sendiri

## Lokasi File Shortcode

### Root folder

untuk membuat sebuah shortcode, buat file html dengan nama bebas di `layouts/shortcodes/namafile.html` kemudian untuk memanggil file shortcode cukup mudah dengan mengetik :

```go
{{- <namafile> }}
```

### Subfolder shortcode

kamu bisa mengelompokkan shortcode kamu menggunakan subfolder contohnya `layouts/shortcodes/namafolder/namafile.html`

kemudian untuk memanggil file shortcode cukup mudah dengan mengetik :

```go
{{- < namafolder/namafile > }}
```

## Susunan Tepmlate Shortcode Hugo

Susunan Template Shortcode di Hugo yaitu :

1. `/layouts/shortcodes/<SHORTCODE>.html`
2. `/themes/<THEME>/layouts/shortcodes/<SHORTCODE>.html`

Jadi shortcode akan dijalankan sesuai urutan diatas, apabila shortcode dipanggil maka Hugo akan mencari shortcode di folder projek kita terlebih dahulu kemudian, jika nggak ada maka akan mencari ke tema yang terinstal di projek kita

## Posisional Argument dan Named Parameter

kamu bisa membuat Shortcode dengan mengikuti tipe Parameter :

- Positional parameters
- Named parameters
- Positional or named parameters

### Posisional argumen

pada shortcode untuk memberi sebuah argumen bisa tanpa menggunakan named Parameter, contohnya seperti ini :

```go
{{- < gambar 'link/to/path/image.jpg' > }}
```

### Named Parameter

pada shortcode untuk memberi sebuah argumen menggunakan named Parameter, contohnya seperti ini :

```go
{{- < gambar src='link/to/path/image.jpg' > }}
```

### Positional or named parameters

pada shortcode untuk memberi sebuah argumen menggunakan named Parameter dan juga tanpa parameter secara bersamaan, contohnya seperti ini :

```go
{{- < gambar src='link/to/path/image.jpg' 'gambar' > }}
```

## Mengambil Parameter

Semua parameter pada Shortcode bisa diakses lewat method `.Get` , meskipun tanpa paramater atau dengan parameter 

### Mengambil Parameter dengan named Parameter

Untuk mengambil parameter dengan nama, gunakan method `.Get` kemudian diikuti dengan nama parameter yang diapit 2 kutip

```go
{{- .Get "src" }}
```

### Mengambil Parameter dengan posisional Parameter

Untuk mengambil parameter tanpa nama, gunakan method `.Get` kemudian diikuti dengan nomor (nomor dimulai dari 0)

```go
{{- .Get 0 }}
```

## Kesimpulan

Begitulah cara membuat shortcode di Hugo, kurang lebihnya mohon maaf, sampai jumpa dia artikel berikutnya~~

**Referensi**

- {{< a href="https://gohugo.io/content-management/shortcodes/" teks="https://gohugo.io/content-management/shortcodes/" >}}
- {{< a href="https://gohugo.io/templates/shortcode-templates/" teks="https://gohugo.io/templates/shortcode-templates/" >}}