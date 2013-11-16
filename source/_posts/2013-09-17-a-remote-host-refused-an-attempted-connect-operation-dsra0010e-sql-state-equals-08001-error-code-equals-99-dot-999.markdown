---
layout: post
title: "A remote host refused an attempted connect operation. DSRA0010E: SQL State = 08001-Error Code = -99.999"
date: 2013-09-17 11:58
comments: true
categories: ["websphere"]
---

Bulan kemaren (Agustus - 2013), gw dapat laporan dari client, bahwa server aplikasi tidak dapat connect ke core banking, ketika di lakukan test connection dari ibm console (websphere) muncul error seperti di bawah ini

{% blockquote %}
The application requester cannot establish the connection. (A remote host refused an attempted connect operation.) DSRA0010E: SQL State = 08001, Error Code = -99.999
{% endblockquote %}

Setelah google, di dapatkan 2 link berikut

1. [link 1][1], dia mengalami hal serupa, karena dia lupa memilih "Component-managed authentication alias"
2. [link 2][2], langsung dari support websphere, menyarankan untuk me-restart websphere.

Solusi 1, jelas tidak mungkin, karena aplikasi sebelumnya dapat berjalan dengan lancar. Solusi 2, masih boleh di coba, dan ternyata setelah di lakukan restart websphere, tetap tidak dapat lakukan test connection, dengan message error masih sama seperti di atas.

hmmm, akhirnya gw curiga sama firewall, gw minta ijin sama client, untuk dapat melakukan koneksi melalui laptop saya, dimana, jaringan yang saya gunakan tidak di block oleh firewall. Saya develop aplikasi java mini (mendadak :( )), untuk melakukan test connection ke core banking (AS/400). Source code untuk aplikasi java tersebut dapat di lihat [di sini][3]. Dan alhamdullilah, ternyata saya dapat melakukan koneksi ke core banking.

Setelah vendor firewall di panggil, akhirnya di ketahui, untuk dapat melakukan koneksi ke AS/400, kita mesti membuka 3 port berikut, yaitu (449, 8476, 8471)


[1]: http://madhutomy.blogspot.com/2013/03/javasqlsqlexception-invalid-arguments.html
[2]: http://www-01.ibm.com/support/docview.wss?uid=swg21235300
[3]: https://github.com/hendrysuwanda/test-connection-as-400