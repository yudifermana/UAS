# UAS


NAMA : YUDI FERMANA

NIM : 312210321

KELAS : TI 22 A3

PACKAGE & MODULE

Tugas ini berdasarkan praktikum sebelumnya dengan struktur seperti ini:

![uas 1](https://user-images.githubusercontent.com/115516653/211435008-ff09e6d4-8930-4207-9c25-7481da2b8fbd.png)

daftar_nilai.py berisi modul untuk :

tambah_data

```python
    elif c.lower() == 't':
i = open('view/database.txt', 'a')
P(" Tambah Kontak")
while (True):
    nama = input(" Nama : ")
    if nama == '':
        P(' Masukan dengan Nama Dengan Benar')
    else:
        break
while (True):
    try:
        nim = int(input(" NIM  : "))
        if nim == '':
            P(' Masukan Nim dengan Angka')
    except ValueError:
        P(' Masukan Nim dengan Angka')
    else:
        break
while (True):
    try:
        tugas = int(input(" TUGAS  : "))
        if tugas == '':
            P(' Masukan TUGAS dengan Angka')
    except ValueError:
        P(' Masukan TUGAS dengan Angka')
    else:
        break
while (True):
    try:
        uts = int(input(" UTS  : "))
        if uts == '':
            P(' Masukan UTS dengan Angka')
    except ValueError:
        P(' Masukan UTS dengan Angka')
    else:
        break
while (True):
    try:
        uas = int(input(" UAS  : "))
        if uas == '':
            P(' Masukan UAS dengan Angka')
    except ValueError:
        P(' Masukan UAS dengan Angka')
    else:
        break
akhir = round((float(tugas) * 0.3) + (float(uts) * 0.35) + (float(uas) * 0.35), 2)
i.write('\nNama : ' + nama + '|Nim : ' + str(nim) + '|Tugas : ' + str(tugas) + '|UTS : ' + str(uts) + '|UAS : ' + str(
    uas) + "|Akhir : " + str(akhir) + '\n')
i.close()
Oc("clear")
```

Output tambah_data

![kodingan 1 1 uas](https://user-images.githubusercontent.com/115516653/211487069-38be1862-b0a9-4924-9cd7-089eeef8e545.png)
![kodingan 1 2 uas](https://user-images.githubusercontent.com/115516653/211487126-88f69795-a156-46fc-aa88-94b9bd7a8132.png)


Penjelasan

* Def tambahkan : Dibagian ini kita gunakan print untuk penulisan bagian input data mahasiswa nanti agar terlihat rapih

ubah_data

```Python
elif c.lower() == 'u':
u = open('view/database.txt', 'r').read().splitlines()
target = input(' Masukan Nama : ')
nm = []
for l in u:
    if l == '':
        pass
    else:
        l1 = l.replace('Nama : ', '').replace('Nim : ', '').replace('Tugas : ', '').replace('UTS : ', '').replace(
            'UAS : ', '').replace('Akhir : ', '')
        na, ni, tu, uts, uas, akhir = l1.strip().split('|')
        if na == target:
            P(' Mengedit Data %s' % (target))
            while (True):
                nama = input(" Nama : ")
                if nama == '':
                    P(' Masukan dengan Nama Dengan Benar')
                else:
                    break
            while (True):
                try:
                    nim = int(input(" NIM  : "))
                    if nim == '':
                        P(' Masukan Nim dengan Angka')
                except ValueError:
                    P(' Masukan Nim dengan Angka')
                else:
                    break
            while (True):
                try:
                    tugas = int(input(" TUGAS  : "))
                    if tugas == '':
                        P(' Masukan TUGAS dengan Angka')
                except ValueError:
                    P(' Masukan TUGAS dengan Angka')
                else:
                    break
            while (True):
                try:
                    uts = int(input(" UTS  : "))
                    if uts == '':
                        P(' Masukan UTS dengan Angka')
                except ValueError:
                    P(' Masukan UTS dengan Angka')
                else:
                    break
            while (True):
                try:
                    uas = int(input(" UAS  : "))
                    if uas == '':
                        P(' Masukan UAS dengan Angka')
                except ValueError:
                    P(' Masukan UAS dengan Angka')
                else:
                    break
            akhir = round((float(tugas) * 0.3) + (float(uts) * 0.35) + (float(uas) * 0.35), 2)
            edit = ('Nama : ' + nama + '|Nim : ' + str(nim) + '|Tugas : ' + str(tugas) + '|UTS : ' + str(
                uts) + '|UAS : ' + str(uas) + "|Akhir : " + str(akhir) + '\n')
            nm.append(edit + '\n')
        else:
            nm.append(str(l) + '\n')
new = open('view/database.txt', 'w')
new.write(str(nm))
new.close()
new = open('view/database.txt', 'r').read().splitlines()
new1 = open('view/database.txt', 'w')
new1.close()
new2 = open('view/database.txt', 'a')
for i in new:
    i2 = i.replace("['", "").replace("\\n', '", "\n").replace("']", "").replace("\\n", "\n")
    new2.write(i2 + '\n')
new2.close()
```

Output ubah_data

![kodingan 2 uas](https://user-images.githubusercontent.com/115516653/211488306-ab7cd146-7166-4ea2-8d6e-13828d27ebe7.png)

Penjelasan

* Disini kita hampir sama dengan yang hapus, kita gunakan inputan nama untuk mengubah NIM, Nilai Tugas, Ujian Tengah Semester(UTS), ataupun Ujian Akhir Semester(UAS)

* Lalu setelah kita memasukkan nama maka dictionary akan mengeksekusi program menggunakan keys untuk mencari data dari nama mahasiswa tersebut

* (If)Jika nama mahasiswa tersebut ketemu atau ada didalam data maka program akan masuk ke inputan NIM, Nilai Tugas, Nilai UTS, dan Nilai UAS yang baru

* (Else)Jika nama mahasiswa tersebut tidak ada didalam data maka program akan memunculkan tulisan atau perintah bahwa data mahasiswa tidak ada

hapus_data

```python
elif c.lower() == 'h':
u = open('view/database.txt', 'r').read().splitlines()
target = input(' Masukan Nama : ')
nm = []
for l in u:
    if l == '':
        pass
    else:
        l1 = l.replace('Nama : ', '').replace('Nim : ', '').replace('Tugas : ', '').replace('UTS : ', '').replace(
            'UAS : ', '').replace('Akhir : ', '')
        na, ni, tu, uts, uas, akhir = l1.strip().split('|')
        if str(na) == str(target):
            P('BERHASIL MENGHAPUS Data %s' % (target))
            pass
        else:
            nm.append(str(l) + '\n')
new = open('view/database.txt', 'w')
new.write(str(nm))
new.close()
new = open('view/database.txt', 'r').read().splitlines()
new1 = open('view/database.txt', 'w')
new1.close()
new2 = open('view/database.txt', 'a')
for i in new:
    i2 = i.replace("['", "").replace("\\n', '", "\n").replace("']", "").replace("\\n", '')
    new2.write(i2)
new2.close()
```

Output hapus_data

![kodingan 3 uas](https://user-images.githubusercontent.com/115516653/211488741-c29f9503-9687-441c-a3e9-1bfb58940de6.png)


Penjelasan

* Def hapus :

* Disini kita hampir sama dengan yang hapus, kita gunakan inputan nama untuk mengubah NIM, Nilai Tugas, Ujian Tengah Semester(UTS), ataupun Ujian Akhir Semester(UAS)

* Lalu setelah kita memasukkan nama maka dictionary akan mengeksekusi program menggunakan keys untuk mencari data dari nama mahasiswa tersebut

* (If)Jika nama mahasiswa tersebut ketemu atau ada didalam data maka program akan masuk ke inputan NIM, Nilai Tugas, Nilai UTS, dan Nilai UAS yang baru

* (Else)Jika nama mahasiswa tersebut tidak ada didalam data maka program akan memunculkan tulisan atau perintah bahwa data mahasiswa tidak ada

cari_data

```python
elif c.lower() == 'c':
cari = input(' cari : ')
i = open('view/database.txt', 'r').read().splitlines()
P(" ╔═════════════════════════════════════════════════════════════════════╗")
P(" ╠════════════════════════ DAFTAR DATA MAHASISWA ══════════════════════╣")
P(" ╠══════════════════╦══════════════════╦═══════╦═══════╦═══════╦═══════╣")
P(" ║      NAMA        ║       NIM        ║ TUGAS ║  UTS  ║  UAS  ║ AKHIR ║")
P(" ╠══════════════════╬══════════════════╬═══════╬═══════╬═══════╬═══════╣")
for l in i:
    if l == '':
        pass
    elif cari in l:
        l1 = l.replace('Nama : ', '').replace('Nim : ', '').replace('Tugas : ', '').replace('UTS : ', '').replace(
            'UAS : ', '').replace('Akhir : ', '')
        na, ni, tu, uts, uas, akhir = l1.strip().split('|')
        P((' ║ ') + (na).ljust(17) + ('║ ') + (ni).ljust(17) + ('║ ') + (tu).ljust(6) + ('║ ') + (uts).ljust(6) + (
            '║ ') + (uas).ljust(6) + ('║ ') + (akhir).ljust(6) + ('║'))
P(" ╚══════════════════╩══════════════════╩═══════╩═══════╩═══════╩═══════╝")
```

Output cari_data

![kodingan 4 uas](https://user-images.githubusercontent.com/115516653/211489045-1a0a76df-9a7e-4845-a7f8-3fa19c37d246.png)

view_nilai.py berisi modul untuk :

Penjelasan Def cari

Fungsinya sama dengan Def tambahkan

cetak_daftar_nilai

```python
elif c.lower() == 'l':
i = open('view/database.txt', 'r').read().splitlines()
P(" ╔═════════════════════════════════════════════════════════════════════╗")
P(" ╠═══════════════════════ DAFTAR DATA MAHASISWA  ══════════════════════╣")
P(" ╠══════════════════╦══════════════════╦═══════╦═══════╦═══════╦═══════╣")
P(" ║      NAMA        ║       NIM        ║ TUGAS ║  UTS  ║  UAS  ║ AKHIR ║")
P(" ╠══════════════════╬══════════════════╬═══════╬═══════╬═══════╬═══════╣")
for l in i:
    if l == '':
        pass
    else:
        l1 = l.replace('Nama : ', '').replace('Nim : ', '').replace('Tugas : ', '').replace('UTS : ', '').replace(
            'UAS : ', '').replace('Akhir : ', '')
        na, ni, tu, uts, uas, akhir = l1.strip().split('|')
        P((' ║ ') + (na[:15]).ljust(17, '.') + ('║ ') + (ni).ljust(17) + ('║ ') + (tu).ljust(6) + ('║ ') + (uts).ljust(
            6) + ('║ ') + (uas).ljust(6) + ('║ ') + (akhir).ljust(6) + ('║'))
P(" ╚══════════════════╩══════════════════╩═══════╩═══════╩═══════╩═══════╝")
```

Output cetak_daftar_nilai

![kodingan 5 uas](https://user-images.githubusercontent.com/115516653/211489346-f4471bbb-0c90-41e5-9f1d-adbb77f0596a.png)

cetak_hasil_pencarian

```python
elif c.lower() == 'c':
cari = input(' cari : ')
i = open('view/database.txt', 'r').read().splitlines()
P(" ╔═════════════════════════════════════════════════════════════════════╗")
P(" ╠════════════════════════ DAFTAR DATA MAHASISWA ══════════════════════╣")
P(" ╠══════════════════╦══════════════════╦═══════╦═══════╦═══════╦═══════╣")
P(" ║      NAMA        ║       NIM        ║ TUGAS ║  UTS  ║  UAS  ║ AKHIR ║")
P(" ╠══════════════════╬══════════════════╬═══════╬═══════╬═══════╬═══════╣")
for l in i:
    if l == '':
        pass
    elif cari in l:
        l1 = l.replace('Nama : ', '').replace('Nim : ', '').replace('Tugas : ', '').replace('UTS : ', '').replace(
            'UAS : ', '').replace('Akhir : ', '')
        na, ni, tu, uts, uas, akhir = l1.strip().split('|')
        P((' ║ ') + (na).ljust(17) + ('║ ') + (ni).ljust(17) + ('║ ') + (tu).ljust(6) + ('║ ') + (uts).ljust(6) + (
            '║ ') + (uas).ljust(6) + ('║ ') + (akhir).ljust(6) + ('║'))
P(" ╚══════════════════╩══════════════════╩═══════╩═══════╩═══════╩═══════╝")
```

Output cetak_hasil_pencarian

![kodingan 6 uas](https://user-images.githubusercontent.com/115516653/211489612-d2f36ae8-e538-4c6a-8eb6-14f41fecb8b1.png)

input_nilai.py berisi modul untuk :

input_data yang meminta pengguna memasukan data

![kodingan databest](https://user-images.githubusercontent.com/115516653/211490263-1f0dc532-ffe1-4c46-a61b-debddef5ef66.png)

Output input_nilai.py

![kodingan 7](https://user-images.githubusercontent.com/115516653/211489840-64339885-dae2-497d-8a13-a2bb4e27999c.png)

main.py berisi program uatama menu pilihan yang memanggil semua yang ada.

```python
import os,sys
P = print
Oc = os.system
while True:
    P("")
    P("")
    c = input("L)ihat, T)ambah, U)bah, H)apus, C)ari, K)eluar: ")
    if c.lower() == 'k':
        break
    elif c.lower() == 'l':
        i = open('view/database.txt', 'r').read().splitlines()
        P(" ╔═════════════════════════════════════════════════════════════════════╗")
        P(" ╠═══════════════════════ DAFTAR DATA MAHASISWA  ══════════════════════╣")
        P(" ╠══════════════════╦══════════════════╦═══════╦═══════╦═══════╦═══════╣")
        P(" ║      NAMA        ║       NIM        ║ TUGAS ║  UTS  ║  UAS  ║ AKHIR ║")
        P(" ╠══════════════════╬══════════════════╬═══════╬═══════╬═══════╬═══════╣")
        for l in i:
            if l == '':
                pass
            else:
                l1 = l.replace('Nama : ','').replace('Nim : ','').replace('Tugas : ','').replace('UTS : ','').replace('UAS : ','').replace('Akhir : ','')
                na,ni,tu,uts,uas,akhir = l1.strip().split('|')
                P((' ║ ')+(na[:15]).ljust(17,'.')+('║ ')+(ni).ljust(17)+('║ ')+(tu).ljust(6)+('║ ')+(uts).ljust(6)+('║ ')+(uas).ljust(6)+('║ ')+(akhir).ljust(6)+('║'))
        P(" ╚══════════════════╩══════════════════╩═══════╩═══════╩═══════╩═══════╝")
    elif c.lower() == 'c':
        cari = input(' cari : ')
        i = open('view/database.txt', 'r').read().splitlines()
        P(" ╔═════════════════════════════════════════════════════════════════════╗")
        P(" ╠════════════════════════ DAFTAR DATA MAHASISWA ══════════════════════╣")
        P(" ╠══════════════════╦══════════════════╦═══════╦═══════╦═══════╦═══════╣")
        P(" ║      NAMA        ║       NIM        ║ TUGAS ║  UTS  ║  UAS  ║ AKHIR ║")
        P(" ╠══════════════════╬══════════════════╬═══════╬═══════╬═══════╬═══════╣")
        for l in i:
            if l == '':
                pass
            elif cari in l:
                l1 = l.replace('Nama : ','').replace('Nim : ','').replace('Tugas : ','').replace('UTS : ','').replace('UAS : ','').replace('Akhir : ','')
                na,ni,tu,uts,uas,akhir = l1.strip().split('|')
                P((' ║ ')+(na).ljust(17)+('║ ')+(ni).ljust(17)+('║ ')+(tu).ljust(6)+('║ ')+(uts).ljust(6)+('║ ')+(uas).ljust(6)+('║ ')+(akhir).ljust(6)+('║'))
        P(" ╚══════════════════╩══════════════════╩═══════╩═══════╩═══════╩═══════╝")
    elif c.lower() == 'h':
        u = open('view/database.txt', 'r').read().splitlines()
        target = input(' Masukan Nama : ')
        nm = []
        for l in u:
            if l == '':
                pass
            else:
                l1 = l.replace('Nama : ','').replace('Nim : ','').replace('Tugas : ','').replace('UTS : ','').replace('UAS : ','').replace('Akhir : ','')
                na,ni,tu,uts,uas,akhir = l1.strip().split('|')
                if str(na) == str(target):
                    P('BERHASIL MENGHAPUS Data %s'%(target))
                    pass
                else:
                    nm.append(str(l)+'\n')
        new = open('view/database.txt', 'w')
        new.write(str(nm))
        new.close()
        new = open('view/database.txt', 'r').read().splitlines()
        new1 = open('view/database.txt', 'w')
        new1.close()
        new2 = open('view/database.txt', 'a')
        for i in new:
            i2 = i.replace("['","").replace("\\n', '", "\n").replace("']","").replace("\\n",'')
            new2.write(i2)
        new2.close()
    elif c.lower() == 'u':
        u = open('view/database.txt', 'r').read().splitlines()
        target = input(' Masukan Nama : ')
        nm = []
        for l in u:
            if l == '':
                pass
            else:
                l1 = l.replace('Nama : ','').replace('Nim : ','').replace('Tugas : ','').replace('UTS : ','').replace('UAS : ','').replace('Akhir : ','')
                na,ni,tu,uts,uas,akhir = l1.strip().split('|')
                if na == target:
                    P(' Mengedit Data %s'%(target))
                    while (True):
                        nama = input(" Nama : ")
                        if nama == '':
                            P(' Masukan dengan Nama Dengan Benar')
                        else:
                            break
                    while (True):
                        try:
                            nim  = int(input(" NIM  : "))
                            if nim == '':
                                P(' Masukan Nim dengan Angka')
                        except ValueError:
                            P(' Masukan Nim dengan Angka')
                        else:
                            break
                    while (True):
                        try:
                            tugas  = int(input(" TUGAS  : "))
                            if tugas == '':
                                P(' Masukan TUGAS dengan Angka')
                        except ValueError:
                            P(' Masukan TUGAS dengan Angka')
                        else:
                            break
                    while (True):
                        try:
                            uts  = int(input(" UTS  : "))
                            if uts == '':
                                P(' Masukan UTS dengan Angka')
                        except ValueError:
                            P(' Masukan UTS dengan Angka')
                        else:
                            break
                    while (True):
                        try:
                            uas  = int(input(" UAS  : "))
                            if uas == '':
                                P(' Masukan UAS dengan Angka')
                        except ValueError:
                            P(' Masukan UAS dengan Angka')
                        else:
                            break
                    akhir = round((float(tugas) * 0.3)+(float(uts) * 0.35)+(float(uas) * 0.35),2)
                    edit  =('Nama : '+nama+'|Nim : '+str(nim)+'|Tugas : '+str(tugas)+'|UTS : '+str(uts)+'|UAS : '+str(uas)+"|Akhir : "+str(akhir)+'\n')
                    nm.append(edit+'\n')
                else:
                    nm.append(str(l)+'\n')
        new = open('view/database.txt', 'w')
        new.write(str(nm))
        new.close()
        new = open('view/database.txt', 'r').read().splitlines()
        new1 = open('view/database.txt', 'w')
        new1.close()
        new2 = open('view/database.txt', 'a')
        for i in new:
            i2 = i.replace("['","").replace("\\n', '", "\n").replace("']","").replace("\\n","\n")
            new2.write(i2+'\n')
        new2.close()
    elif c.lower() == 't':
        i = open('view/database.txt', 'a')
        P(" Tambah Kontak")
        while (True):
            nama = input(" Nama : ")
            if nama == '':
                P(' Masukan dengan Nama Dengan Benar')
            else:
                break
        while (True):
            try:
                nim  = int(input(" NIM  : "))
                if nim == '':
                    P(' Masukan Nim dengan Angka')
            except ValueError:
                P(' Masukan Nim dengan Angka')
            else:
                break
        while (True):
            try:
                tugas  = int(input(" TUGAS  : "))
                if tugas == '':
                    P(' Masukan TUGAS dengan Angka')
            except ValueError:
                P(' Masukan TUGAS dengan Angka')
            else:
                break
        while (True):
            try:
                uts  = int(input(" UTS  : "))
                if uts == '':
                    P(' Masukan UTS dengan Angka')
            except ValueError:
                P(' Masukan UTS dengan Angka')
            else:
                break
        while (True):
            try:
                uas  = int(input(" UAS  : "))
                if uas == '':
                    P(' Masukan UAS dengan Angka')
            except ValueError:
                P(' Masukan UAS dengan Angka')
            else:
                break
        akhir = round((float(tugas) * 0.3)+(float(uts) * 0.35)+(float(uas) * 0.35),2)
        i.write('\nNama : '+nama+'|Nim : '+str(nim)+'|Tugas : '+str(tugas)+'|UTS : '+str(uts)+'|UAS : '+str(uas)+"|Akhir : "+str(akhir)+'\n')
        i.close()
        Oc("clear")
    else:
        P("Pilih menu yang tersedia")
```

Output main.py

![uas penutup](https://user-images.githubusercontent.com/115516653/211483457-2c40c5c3-76f7-41a2-966e-d72ede768dda.png)
