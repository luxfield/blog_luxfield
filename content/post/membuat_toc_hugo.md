---
title: "Cara Membuat TOC di Hugo"
date: 2021-09-06T18:18:35+07:00
draft: false
author: "Surya Efendi"
description: "Kalian pasti sering lihat di sebuah blog ada sebuah TOC (Table of Content) atau daftar isi, sebenarnya daftar isi itu buat apa sih ? dan gunanya TOC di blog itu apa sih ?"
cover: "https://d33wubrfki0l68.cloudfront.net/c38c7334cc3f23585738e40334284fddcaf03d5e/2e17c/images/hugo-logo-wide.svg"
Toc: true
TocTitle: "Daftar Isi"
tags: ["Hugo"]
---

**Cara Membuat TOC di Hugo** - Kalian pasti sering lihat di sebuah blog ada sebuah TOC (Table of Content) atau daftar isi, didalam daftar isi banyak judul-judul/bagian-bagian didalam sebuah blog, sebenarnya daftar isi itu buat apa sih ? dan gunanya TOC di Hugo itu apa ?.

## Pengertian TOC (Table Of Content)

TOC (Table of Content) adalah pembuatan daftar isi secara otomatis dan dinamis, pada halaman website biasanya TOC akan terbuat secara otomatis mengikuti heading yang kita buat pada tulisan di halaman tersebut.

Contohnya seperti ini:

![toc](/img/membuat_toc_hugo/toc.jpg)

Jika salah satu poin pada daftar isinya di klik maka langsung mengarah ke pembahasan tersebut misal kita klik "On-Target (T.O.C)" maka tampilan halaman pada website akan langsung menampilkan pembahasan tentang "On-Target (T.O.C)" pada halaman website yang sama.

## Apa Fungsinya TOC?

Sebagai pemilik website Anda harus memahami karakter pembaca website Anda, tidak semua user suka membaca artikel yang cukup panjang. Mereka biasanya lebih suka membaca hal penting yang mereka cari saja.

Misal pada konten jualan, mungkin user tipe ini hanya fokus mencari harga produk Anda saja. atau hanya fokus mencari penjelasan spesifikasi produk yang Anda tawarkan tanpa mau membaca pembahasan lainnya.

Untuk user seperti ini TOC sangat penting adanya, sehingga mereka hanya perlu melihat daftar isinya saja kemudian meng-klik judul informasi yang mereka cari untuk langsung menuju ke pembahasan judul tersebut.

Tanpa adanya TOC, user seperti ini akan langsung keluar dari website Anda karena malas scrol dan membaca artikel secara keseluruhan untuk menemukan informasi yang mereka cari. Hal ini mengakibatkan bounce rate di website menjadi tinggi dan menyebabkan user experience website menjadi buruk di mata Google

## Bagaimana Cara Membuat TOC di Hugo?

di hugo ada 2 cara untuk membuat TOC

### 1. TOC di single page template

untuk membuat TOC di single page template ini mudah sekali, buka file `single.html` di `layout/_default/single.html` jika tidak ada maka buat saja dengan nama `single.html` kemudian ikutin contoh dibawah ini

```html
{{ define "main" }}
<main>
    <article>
    <header>
        <h1>{{ .Title }}</h1>
    </header>
        {{ .Content }}
    </article>
    <aside>
        {{ .TableOfContents }}
    </aside>
</main>
{{ end }}
```

### 2. TOC di partial page template

sama saja dengan single page template untuk membuat TOC di partial page template ini mudah sekali, buka file `toc.html` di `layout/partials/toc.html` jika tidak ada maka buat saja dengan nama `toc.html` atau bebas kemudian ikutin contoh dibawah ini

```html
{{ if and (gt .WordCount 400 ) (.Params.toc) }}
<aside>
    <header>
    <h2>{{.Title}}</h2>
    </header>
    {{.TableOfContents}}
</aside>
{{ end }}

```

Penjelasan kode diatas:

- `.WordCount` : fungsi ini akan menghitung kata dalam halaman webite kita
- `.Params.toc` : fungsi ini akan menampilkan toc jika nilai `true` maka toc akan tampil

Karena partial page template ini terpisah dari layout maka untuk memasukan `toc.html` kedalam halaman website kita dapat menggunakan

```go
{{ partial "partials/toc.html" . }}
```

## Konfigurasi TOC

pada tag `{{ .TableOfContents }}` berisi TOC pada sebuah halaman website kita, kemudian kita konfigurasi `{{ .TableOfContents }}` di `config.toml`

```md
[markup]
  [markup.tableOfContents]
    endLevel = 3
    ordered = false
    startLevel = 2
```

penjelasan `[markup.tableOfContents]` :

- `endLevel` : batas akhir sub judul yang akan di tampilkan di TOC, nilainya berdasarkan tag html, misal `3` maka tag html `</h3></h3>` akan ditampilkan di TOC, tag `<h4></h4>` keatas tidak akan ditampilkan
- `ordered` : pada bagian ini judul-judul pada TOC akan diurutkan apabila di set nilai `true`
- `startLevel` : batas awal judul yang akan di tampilkan di TOC, nilainya berdasarkan tag html, misal `2` maka tag html `</h2></h2>` akan ditampilkan di TOC, tag `<h1></h1>` keatas tidak akan ditampilkan

## Kesimpulan

Kita bisa tau apa itu TOC dan fungsi TOC untuk website kita, memudahkan pembaca untuk melihat apa yang mereka ingin lihat, kemudian kita dapat membuat TOC di hugo dan mengkonfigurasikannya, sekian dari saya semoga tulisan ini bermanfaat

**Referensi**

<ul>
    <li>
        <a href="https://gohugo.io/content-management/toc/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">https://gohugo.io/content-management/toc/</a>
    </li>
    <li>
        <a href="https://gohugo.io/templates/partials/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">https://gohugo.io/templates/partials/</a>
    </li>
    <li>
        <a href="https://gohugo.io/getting-started/configuration-markup/#table-of-contents" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">https://gohugo.io/getting-started/configuration-markup/#table-of-contents</a>
    </li>
    <li>
        <a href="https://defriansyah.net/table-of-content/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">https://defriansyah.net/table-of-content/</a>
    </li>
</ul>

---
