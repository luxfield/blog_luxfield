---
title: "Mode Debug Flask"
date: 2021-09-05T14:41:44+07:00
draft: false
Author: "Surya Efendi"
Description: "`Flask` dapat melakukan aksi lebih banyak sekedar hanya menjalankan development server, dengan mengaktifkan debug mode, `Flask` secara otomatis akan memuat ulang server ketika ada perubahan kode, dan akan menampilkan sebuah debug interaktif pada browser jika ada masalah terjadi saat melakukan permintaan
"
Cover: "https://flask.palletsprojects.com/en/2.0.x/_static/flask-icon.png"
toc: true
tags: ["python"]
TocTitle: "Daftar Isi"
---

## Deskripsi

`Flask` dapat melakukan aksi lebih banyak sekedar hanya menjalankan development server, dengan mengaktifkan debug mode, `Flask` secara otomatis akan memuat ulang server ketika ada perubahan kode, dan akan menampilkan sebuah debug interaktif pada browser jika ada masalah terjadi saat melakukan permintaan

![Flask Debug](https://flask.palletsprojects.com/en/2.0.x/_images/debugger.png)

---

## Peringatan

debugger memperbolehkan menjalankan kode python dari browser, itu terlindungi oleh pin, tetapi tetap merupakan sebuah resiko keamanan utama, jangan jalankan development server atau debugger pada lingkungan production

---

untuk mengaktifkan semua fitur development, set `FLASK_ENV` pada environment variable dengan nilai development sebelum menjalankan `Flask`

{{< code language="bash" id="1" expand="Tampilkan" collapse="Hide" isCollapsed="true" >}}
$ export FLASK_ENV=development
$ flask run
{{< /code >}}
{{< code language="CMD" id="2" expand="Tampilkan" collapse="Hide" isCollapsed="true" >}}
> set FLASK_ENV=development
> flask run
{{< /code >}}
{{< code language="Powershell" id="3" expand="Tampilkan" collapse="Hide" isCollapsed="true" >}}
> $env:FLASK_ENV = "development"
> flask run
{{< /code >}}

Lihat Juga:

<ul>
    <li>
        <a href="https://flask.palletsprojects.com/en/2.0.x/server/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">Development Server</a> dan <a href="https://flask.palletsprojects.com/en/2.0.x/cli/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">Command Line Interface</a> untuk informasi tentang menjalankan web pada mode development
    </li>
    <li>
        <a href="https://flask.palletsprojects.com/en/2.0.x/debugging/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">Debugging Application Errors</a> for information about using the built-in debugger and other debuggers.
    </li>
    <li>
        <a href="https://flask.palletsprojects.com/en/2.0.x/logging/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">Logging</a> dan <a href="https://flask.palletsprojects.com/en/2.0.x/errorhandling/" onclick="window.open('https://www.effectivecpmgate.com/s3in6ahg?key=d097cf9f5c481b2e272dff32038a169b','_blank');" target="_blank">Handling Application Errors</a> to log errors and display nice error pages.
    </li>
</ul>
