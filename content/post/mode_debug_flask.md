---
title: "Mode Debug Flask"
date: 2021-09-05T14:41:44+07:00
draft: false
Author: "Surya Efendi"
Description: "`Flask` dapat melakukan aksi lebih banyak sekedar hanya menjalankan development server, dengan mengaktifkan debug mode, `Flask` secara otomatis akan memuat ulang server ketika ada perubahan kode, dan akan menampilkan sebuah debug interaktif pada browser jika ada masalah terjadi saat melakukan permintaan
"
Cover: "https://flask.palletsprojects.com/en/2.0.x/_static/flask-icon.png"
---

## Deskripsi

`Flask` dapat melakukan aksi lebih banyak sekedar hanya menjalankan development server, dengan mengaktifkan debug mode, `Flask` secara otomatis akan memuat ulang server ketika ada perubahan kode, dan akan menampilkan sebuah debug interaktif pada browser jika ada masalah terjadi saat melakukan permintaan

![Flask Debug](https://flask.palletsprojects.com/en/2.0.x/_images/debugger.png)

---

## Peringatan

debugger memperbolehkan menjalankan kode python dari browser, itu terlindungi oleh pin, tetapi tetap merupakan sebuah resiko keamanan utama, jangan jalankan development server atau debugger pada lingkungan production

---

untuk mengaktifkan semua fitur development, set `FLASK_ENV` pada environment variable dengan nilai development sebelum menjalankan `Flask`

{{< code language="bash" id="1" expand="Show" collapse="Hide" isCollapsed="true" >}}
$ export FLASK_ENV=development
$ flask run
{{< /code >}}
{{< code language="CMD" id="2" expand="Show" collapse="Hide" isCollapsed="true" >}}
> set FLASK_ENV=development
> flask run
{{< /code >}}
{{< code language="Powershell" id="3" expand="Show" collapse="Hide" isCollapsed="true" >}}
> $env:FLASK_ENV = "development"
> flask run
{{< /code >}}

Lihat Juga:

- [Development Server](https://flask.palletsprojects.com/en/2.0.x/server/) and [Command Line Interface](https://flask.palletsprojects.com/en/2.0.x/cli/) for information about running in development mode.
- [Debugging Application Errors](https://flask.palletsprojects.com/en/2.0.x/debugging/) for information about using the built-in debugger and other debuggers.
- [Logging](https://flask.palletsprojects.com/en/2.0.x/logging/) and [Handling Application Errors](https://flask.palletsprojects.com/en/2.0.x/errorhandling/) to log errors and display nice error pages.
