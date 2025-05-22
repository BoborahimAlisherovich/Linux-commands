<p align="center"><img src="https://raw.githubusercontent.com/bobbyiliev/101-linux-commands-ebook/main/ebook/en/assets/cover.jpg" height="450" width="auto"></p>

<div align="center">
    <p>
	    <a name="stars"><img src="https://img.shields.io/github/stars/bobbyiliev/101-linux-commands-ebook?style=for-the-badge"></a>
	    <a name="forks"><img src="https://img.shields.io/github/forks/bobbyiliev/101-linux-commands-ebook?logoColor=green&style=for-the-badge"></a>
	    <a name="contributions"><img src="https://img.shields.io/github/contributors/bobbyiliev/101-linux-commands-ebook?logoColor=green&style-for-the-badge"></a>
      <a name="ebook" href="https://sugatoray.github.io/101-linux-commands-ebook" target="_blank"><img src="https://img.shields.io/static/v1?label=eBook&message=Read%20Online&color=orange&logoColor=green&style=for-the-badge&logo=github"><img src="https://img.shields.io/github/contributors/bobbyiliev/101-linux-commands-ebook?logoColor=yellow&style=for-the-badge"></a>
	    <a name="madeWith"><img src="https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg?style=for-the-badge"></a>
	    <a name="license"><img src="https://img.shields.io/github/license/bobbyiliev/101-linux-commands-ebook?style=for-the-badge"></a>
    </p>
</div>

## 💻 101 Linux buyruqlari – Ochiq manbali eBook

Bu ochiq manbali eBook bo‘lib, unda har bir Linux foydalanuvchisi bilishi kerak bo‘lgan 101 ta buyruq keltirilgan. Siz DevOps/SysOps muhandisi, dasturchi yoki oddiy Linux ishqibozi bo‘lsangiz ham, terminaldan foydalanishga to‘g‘ri keladi. Ushbu kitobda keltirilgan buyruqlar tizimni boshqarish, fayllar bilan ishlash, tarmoq sozlamalari va boshqa ko‘plab vazifalarni bajarishda yordam beradi.

**Eslatma**: Repozitoriyga yulduzcha qo‘yishni unutmang ⭐

Agar ushbu buyruqlarni sinab ko‘rish uchun Linux virtual mashinasiga ehtiyoj sezsangiz, quyidagi havoladan foydalanib [DigitalOcean’da $200 bepul kredit](https://m.do.co/c/2a9bba940f39) olishingiz mumkin!

## Linuxga kirish eBook

Agar yangi boshlovchilar uchun keng qamrovli qo‘llanma izlayotgan bo‘lsangiz, ushbu eBookni ko‘rib chiqing: [Introduction to Linux eBook](https://leanpub.com/introduction-to-linux)

## 📙 Onlayn eBook

Kitobning onlayn nusxasi :zap:🌐 quyidagi havolada mavjud [**bu yerda** 📙](https://sugatoray.github.io/101-linux-commands-ebook).

## 🔽 Yuklab olish havolalari

- [Qorong‘i rejim](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/export/101-linux-commands-ebook-dark.pdf)
- [Yorug‘ rejim](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/export/101-linux-commands-ebook-light.pdf)

---

# Mundarija <!-- omit in toc -->

- [Asoslar](#asoslar)
  - [Fayl Tizimi Ierarxiyasi Standarti (FHS)](#fayl-tizimi-ierarxiyasi-standarti-fhs)
  - [Buyruqlar](#buyruqlar)
- [Disk va Fayl Tizimini Boshqarish](#disk-va-fayl-tizimini-boshqarish)
  - [Umumiy Disk Manipulyatsiyasi (LVMsiz)](#umumiy-disk-manipulyatsiyasi-lvmsiz)
  - [Globallar (Joker Belgilar)](#globallar-joker-belgilar)
  - [Regex](#regex)
  - [Oqim yo‘naltirish](#oqim-yo‘naltirish)
- [Matn O‘quvchilar va Muharrirlar](#matn-o‘quvchilar-va-muharrirlar)
  - [Less](#less)
  - [VI](#vi)
- [Foydalanuvchi va Guruh Boshqaruvi](#foydalanuvchi-va-guruh-boshqaruvi)
- [Fayl Tizimi Ruxsatnomalari](#fayl-tizimi-ruxsatnomalari)
- [SSH](#ssh)
- [Cronjobs](#cronjobs)
- [Paket Boshqaruvi](#paket-boshqaruvi)
  - [RPM](#rpm)
  - [YUM](#yum)
- [📃 Kategoriyalar bo‘yicha buyruqlar ro‘yxati:](#kategoriyalar-bo‘yicha-buyruqlar-ro‘yxati)
    - [Papkalar bo‘yicha navigatsiya](#papkalar-bo‘yicha-navigatsiya)
    - [Fayl buyruqlari](#fayl-buyruqlari)
    - [Fayl va Papka Manipulyatsiyasi](#fayl-va-papka-manipulyatsiyasi)
    - [Paket arxivlash va siqish vositalari](#paket-arxivlash-va-siqish-vositalari)
    - [Tizim buyruqlari](#tizim-buyruqlari)
    - [Tarmoq buyruqlari](#tarmoq-buyruqlari)
    - [Paket boshqaruvi](#paket-boshqaruvi-1)
    - [Foydalanuvchi ma’lumotlari buyruqlari](#foydalanuvchi-ma‘lumotlari-buyruqlari)
    - [Sessiya buyruqlari](#sessiya-buyruqlari)
    - [Yordam olish](#yordam-olish)
    - [Ilovalar](#ilovalar)
- [📃 Boblar bo‘yicha buyruqlar ro‘yxati:](#boblar-bo‘yicha-buyruqlar-ro‘yxati)
- [🔗Havolalar](#havolalar)
- [📖Boshqa eBooklar](#boshqa-ebooklar)
- [🤲Hissa qo‘shish](#hissa-qo‘shish)

---

# Asoslar

## Fayl Tizimi Ierarxiyasi Standarti (FHS)

| Yo‘l      | Tarkib                              |
|-----------|-------------------------------------|
| `/bin`    | Foydalanuvchi uchun binary fayllar  |
| `/boot`   | Yuklash fayllari                   |
| `/etc`    | Tizim sozlamalari                  |
| `/lib`    | Umumiy kutubxonalar va yadro modullari |
| `/sbin`   | Tizim administratori uchun buyruqlar |
| `/var`    | O‘zgaruvchan fayllar (masalan, loglar) |
| `/usr`    | Uchinchi tomon dasturlari          |
| `/proc`   | Virtual fayl tizimi                |
| `/sys`    | Virtual fayl tizimi                |
| `/mnt`    | Ichki disklar uchun ulash nuqtasi  |
| `/media`  | Tashqi disklar uchun ulash nuqtasi |
| `/home`   | Foydalanuvchilarning shaxsiy papkalari |
| `/run`    | Ishlayotgan jarayonlarning PID fayllari |

---

## Buyruqlar

**Fayl Tizimi Buyruqlari**

| Buyruq  | Opsiyalar          | Tavsif                                  |
|---------|--------------------|-----------------------------------------|
| [`cd`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/002-the-cd-command.md)     | `-`                | Oxirgi papkaga o‘tish                   |
|         | `~`                | Foydalanuvchi uy papkasiga o‘tish      |
|         | `~username`        | Belgilangan foydalanuvchi uy papkasiga o‘tish |
| [`pwd`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/006-the-pwd-command.md)    |                    | Joriy papkani ko‘rsatish                |
| [`ls`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/001-the-ls-command.md)     |                    | Papka tarkibini ko‘rsatish              |
|         | `-l`               | Ro‘yxatni batafsil ko‘rsatish           |
|         | `-a`               | Yashirin fayllarni ko‘rsatish (`-A` `.` va `..`siz) |
|         | `-r`               | Teskari tartibda ko‘rsatish             |
|         | `-R`               | Rekursiv ko‘rsatish                    |
|         | `-S`               | Hajm bo‘yicha saralash                 |
|         | `-t`               | O‘zgartirilgan sana bo‘yicha saralash  |
| [`mkdir`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/014-the-mkdir-command.md) | `-p`             | Ota-onalar bilan papka yaratish         |
| [`cp`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/031-the-cp-command.md)     | `-r`               | Papkani nusxalash                      |
| [`rmdir`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/103-the-rmdir-command.md) | `-p`             | Bo‘sh papkani va uning ota-onalarini o‘chirish |
| [`rm`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/040-the-rm-command.md)     | `-rf`              | Papkani rekursiv ravishda o‘chirish, `-f` tasdiqlamasdan |
| [`mv`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/032-the-mv-command.md)     |                    | Fayl yoki papkani ko‘chirish           |
| [`find`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/102-the-find-command.md)   | `-iname pattern`   | Fayl/papkani katta-kichik harflarga e’tiborsiz qidirish |
|         | `-mmin n`          | Oxirgi n daqiqada o‘zgartirilgan fayllar |
|         | `-mtime n`         | Oxirgi n kunda o‘zgartirilgan fayllar  |
|         | `-regex pattern`   | Naqshga mos keladigan yo‘l             |
|         | `-size n[kMG]`     | Fayl hajmi bo‘yicha qidirish (`-n` kichik; `+n` katta) |
|         | `! searchparams`   | Qidiruvni teskari qilish               |

---

**Fayl Manipulyatsiyasi**

| Buyruq  | Opsiyalar                                    | Tavsif                                    |
|---------|----------------------------------------------|-------------------------------------------|
| [`cat`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/003-the-cat-tac-command.md)    | `fayl`                                     | Fayl mazmunini ko‘rsatish                 |
| [`tac`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/003-the-cat-tac-command.md)    | `fayl`                                     | Fayl mazmunini teskari tartibda ko‘rsatish |
| [`sort`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/059-the-sort-command.md)   | `fayl`                                     | Faylni saralab ko‘rsatish                 |
|         | `fayl -r -u`                               | Teskari tartibda, takrorlanmasdan saralash |
| [`head`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/004-the-head-command.md)   | `-n10 fayl`                                | Faylning dastlabki 10 qatorini ko‘rsatish |
| [`tail`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/005-the-tail-command.md)   | `-f fayl`                                  | Yangi qatorlarni avtomatik kuzatish       |
| [`cut`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/098-the-cut-command.md)    | `-f -4,7-10,12,15- fayl`                   | Tab bilan ajratilgan maydonlarni tanlash   |
|         | `-c -4,7-10,12,15- fayl`                   | Belgilangan belgilarni tanlash            |
|         | `-f 2,4 -d, --output-delimiter=$'\t' fayl` | Ajratuvchini o‘zgartirish (chiqishda tab) |
| [`uniq`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/074-the-uniq-command.md)   | `fayl`                                     | Ketma-ket bir xil qatorlarni yashirish    |
|         | `fayl -c`                                  | Ketma-ket bir xil qatorlar sonini ko‘rsatish |
|         | `fayl -u`                                  | Faqat takrorlanmagan qatorlarni ko‘rsatish |
| `file`  | `fayl`                                     | Fayl turini aniqlash                      |
| `wc`    | `fayl`                                     | Qatorlar, so‘zlar va belgilarni sanash    |

---

**Arxivlash**

| Buyruq          | Opsiyalar                          | Tavsif                                              |
|-----------------|------------------------------------|-----------------------------------------------------|
| [`tar`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/063-the-tar-command.md)            | `cfv archiv.tar fayl1 fayl2`       | Arxiv yaratish yoki yangilash                       |
|                 | `tfv archiv.tar`                   | Arxiv mazmunini ko‘rsatish                          |
|                 | `xf archiv.tar [-C ~/extracted]`   | Arxivni ochish (siqilgan bo‘lsa, dekompressiya qilish) |
|                 | `cfvj archiv.tar.bz2 fayl`         | Bzip2 bilan siqilgan arxiv yaratish                 |
|                 | `cfvz archiv.tar.gz fayl`          | Gzip bilan siqilgan arxiv yaratish                  |
|                 | `cfa archiv.tar.[komp] fayl`       | Siqilgan arxiv yaratish (nomi bo‘yicha avto-tur)   |
| [`bzip2`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/069-the-bzip2-command.md) | `fayl1 fayl2`                      | Fayllarni alohida siqish                            |
|                 | `-d fayl1 fayl2`                   | Fayllarni dekompressiya qilish                      |
| [`gzip`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/015-the-gzip-command.md)  | `fayl1 fayl2`                      | Fayllarni alohida siqish                            |
|                 | `-d fayl1 fayl2`                   | Fayllarni dekompressiya qilish                      |

---

# Disk va Fayl Tizimini Boshqarish

## Umumiy Disk Manipulyatsiyasi (LVMsiz)

Jismoniy bo‘limlarni yaratish **talab qilinmaydi**! Siz to‘g‘ridan-to‘g‘ri PVlar yaratishingiz mumkin!

| Buyruq       | Opsiyalar                     | Tavsif                                      |
|--------------|-------------------------------|---------------------------------------------|
| `fdisk`      | `-l`                          | Jismoniy disklar va bo‘limlarni ro‘yxatlash |
|              | `/dev/sdb`<br>`n`             | Yangi bo‘lim yaratish                       |
|              | `/dev/sdb`<br>`t`<br>`8e`     | Bo‘lim turini *Linux LVM* ga o‘zgartirish   |
| `mkfs.xfs`   | `/dev/myVG/myVol`             | LVni XFS formatida formatlash               |
| `mkfs.ext4`  | `-f /dev/myVG/myVol`          | LVni EXT4 formatida formatlash (qayta yozish) |
| `blkid`      | `/dev/myVG/myVol`             | UUID va formatlash ma’lumotlarini ko‘rsatish |
| `mount`      |                               | Joriy ulangan fayl tizimlarini ko‘rsatish   |
|              | `-t ext4 /dev/myVG/myVol /mountpoint` | LVni /mountpoint ga ulash            |
|              | `-a`                          | /etc/fstab da sozlanganidek ulash           |
| `umount`     |                               | Fayl tizimini ajratish                      |
|              | `/dev/myVG/myVol`             | LVni /mountpoint dan ajratish               |
|              | `/mountpoint`                 | LVni /mountpoint dan ajratish               |
| [`df`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/010-the-df-command.md) |                -              | Disk foydalanishini ko‘rsatish              |
| `xfs_growfs` | `/dev/myVG/myVol`             | XFS fayl tizimi hajmini o‘zgartirish        |
| `resize2fs`  | `/dev/myVG/myVol`             | EXT3/4 fayl tizimi hajmini o‘zgartirish     |

---

**Boshqalar**

| Buyruq     | Opsiyalar         | Tavsif                                    |
|------------|-------------------|-------------------------------------------|
| `<buyruq>` | `--help`          | Joriy buyruq uchun yordam (standartlashtirilmagan) |
|            | `-h`              |                                           |
|            | `-?`              |                                           |
| [`man`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/024-the-man-command.md)       | `<buyruq>`       | Buyruqning qo‘llanma sahifasi             |
|            | `-k kalit so‘z`   | Kalit so‘z bo‘yicha buyruq qidirish (yoki `apropos`) |
| `alias`    |                   | Taxalluslarni ko‘rsatish                  |
|            | `name='buyruq'`   | Taxallus yaratish                         |

---

## Globallar (Joker Belgilar)

Yashirin elementlar oldidagi nuqta `.` globallar naqshlarida e’tiborga olinmaydi!

| Belgi     | Tavsif                          |
|-----------|---------------------------------|
| `?`       | Har qanday yagona belgi         |
| `*`       | Har qanday belgilar             |
| `[ac-e]`  | Ro‘yxatdagi 1 ta belgi          |
| `[!ac-e]` | Ro‘yxatda bo‘lmagan 1 ta belgi  |

## Regex

Bash o‘zi regexni bilmaydi. `grep`, `sed`, `awk` kabi dasturlardan foydalaning.

**Boshqaruv belgilari**

| Belgi          | Tavsif                          |
|----------------|---------------------------------|
| `.`            | Har qanday yagona belgi         |
| `[ac-e]`       | Ro‘yxatdagi 1 ta belgi          |
| `[^ac-e]`      | Ro‘yxatda bo‘lmagan 1 ta belgi  |
| `^`            | Satr boshlanishi                |
| `$`            | Satr tugashi                    |
| `\d`           | Raqam                           |
| `\D`           | Raqam emas                      |
| `\s`           | Bo‘shliq                        |
| `\S`           | Bo‘shliq emas                   |
| `\<`           | So‘z boshlanishi                |
| `\>`           | So‘z tugashi                    |
| `naqsh?`       | 0 yoki 1 marta takrorlanadi     |
| `naqsh*`       | 0 yoki undan ko‘p marta         |
| `naqsh+`       | 1 yoki undan ko‘p marta         |
| `naqsh{x}`     | Aynan x marta                   |
| `naqsh{x,}`    | x dan ko‘p marta                |
| `naqsh{x,y}`   | x dan y gacha                   |
| `naqsh{,y}`    | 0 dan y gacha                   |

**Grep**

| Buyruq | Opsiyalar           | Tavsif                  |
|--------|---------------------|-------------------------|
| [`grep`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/107-the-grep-command.md)  | `naqsh fayl`        | Kengaytirilgan Regex    |
|        | `-E naqsh fayl`     | Kengaytirilgan Regex    |
|        | `-v naqsh fayl`     | Teskari moslik          |
|        | `-w naqsh fayl`     | So‘z bo‘yicha moslik    |
|        | `-i naqsh fayl`     | Katta-kichik harflarga e’tiborsiz |

## Oqim yo‘naltirish

- `>` qayta yozish
- `>>` qo‘shish

| Belgi                | Tavsif                          |
|----------------------|---------------------------------|
| `> fayl` yoki `1> fayl` | STDOUT ni faylga yozish         |
| `< fayl`             | Faylni STDIN ga yo‘naltirish    |
| `2> fayl`            | STDERR ni faylga yozish         |
| `2>&1`               | STDERR ni STDOUT bilan bir joyga |
| `> fayl 2>&1`        | STDOUT va STDERR ni faylga      |

# Matn O‘quvchilar va Muharrirlar

## Less

| Buyruq             | Tavsif                          |
|--------------------|---------------------------------|
| `q`                | Chiqish                         |
| `R`                | Mazmunni yangilash              |
| `F`                | Avtomatik aylantirish           |
| `g raqam`          | Qatorga o‘tish                  |
| `m kichikHarf`     | Qatorni belgilash               |
| `' kichikHarf`     | Belgilangan qatorga o‘tish      |
| `/naqsh`           | Oldinga qidirish                |
| `?naqsh`           | Orqaga qidirish                 |
| `n`                | Keyingi qidiruv natijasi        |
| `N`                | Oldingi qidiruv natijasi        |
| `ESC u`            | Qidiruv belgilanishini olib tashlash |

## VI

[`VI/VIM`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/100-the-vim-command.md)
**Tahrirlash**

Tahrirlash rejimidan chiqish uchun `ESC` ni bosing.

| Buyruq   | Tavsif                          |
|----------|---------------------------------|
| `i`      | Kursor oldidan yozish           |
| `a`      | Kursor orqasidan yozish         |
| `A`      | Qator oxiridan yozish           |
| `o`      | Quyida yangi qator              |
| `O`      | Yuqorida yangi qator            |
| `u`      | Bekor qilish                    |
| `.`      | Oxirgi buyruqni takrorlash      |
| `yy`     | Qatorni nusxalash               |
| `5yy`    | 5 qatorni nusxalash             |
| `p`      | Quyida joylashtirish            |
| `P`      | Yuqorida joylashtirish          |
| `x`      | Belgini o‘chirish               |
| `5x`     | 5 belgini o‘chirish             |
| `dd`     | Qatorni o‘chirish               |
| `5dd`    | 5 qatorni o‘chirish             |
| `:10,20d`| 10-20 qatorlarni o‘chirish      |
| `d0`     | Qator boshigacha o‘chirish      |
| `d$`     | Qator oxirigacha o‘chirish      |

**Navigatsiya**

Odatdagidek `strelka tugmalari`, `home`, `end`, `pg up`, `pg dn` bilan harakatlaning.

| Buyruq | Tavsif                          |
|--------|---------------------------------|
| `5G`   | 5-qatorga o‘tish                |
| `H`    | Ekranning yuqorisiga            |
| `M`    | Ekranning o‘rtasiga             |
| `L`    | Ekranning pastiga               |
| `5w`   | 5 so‘z oldinga                  |
| `5b`   | 5 so‘z orqaga                   |

**Boshqalar**

| Buyruq     | Tavsif                          |
|------------|---------------------------------|
| `/foo`     | Oldinga qidirish                |
| `?foo`     | Orqaga qidirish                 |
| `n`        | Qidiruvni takrorlash            |
| `:w`       | Saqlash                         |
| `:q`       | Yopish                          |
| `:wq`      | Saqlash va yopish               |
| `:q!`      | Saqlamasdan yopish              |
| `:!buyruq` | Bash buyruqlarini ishga tushirish |
| `:r foo`   | Foo faylini joriy faylga o‘qish |

# Foydalanuvchi va Guruh Boshqaruvi

**UID**

| UID   | Tur             |
|-------|-----------------|
| <1000 | Tizim hisobi    |
| >1000 | Foydalanuvchi hisobi |

**Foydalanuvchi ma’lumotlar bazasi**

Foydalanuvchi ma’lumotlari parolsiz `/etc/passwd` da saqlanadi.

| foydalanuvchi | PW  | UID  | GID  | GECOS     | HOME        | SHELL     |
|---------------|-----|------|------|-----------|-------------|-----------|
| hfict         | x   | 1000 | 1000 |           | /home/hfict | /bin/bash |

**Guruh ma’lumotlar bazasi**

Ikkinchi darajali guruh a’zolari `/etc/group` da saqlanadi. Asosiy guruh a’zolari foydalanuvchi bazasidagi GID orqali aniqlanadi.

| guruhnomi | PW  | GID | Foydalanuvchilar |
|-----------|-----|-----|------------------|
| wheel     | x   | 10  | hfict,user2      |

**Parol ma’lumotlar bazasi**

Hashlangan foydalanuvchi parollari `/etc/shadow` da saqlanadi. Parol shifrlash `/etc/login.defs` da sozlanadi.

| foydalanuvchi | PW     | Oxirgi parol o‘zgartirish | Minimum | Maximum | Ogohlantirish | Faol emas | Tugash |
|---------------|--------|---------------------------|---------|---------|---------------|-----------|--------|
| hfict         | [hash] | 17803                     | 0       | 99999   | 7             |           |        |

Parol:

- `[hash]` Shifrlangan test paroli
- `! [hash]` Hisob qulflangan
- `!!` yoki `*` Hisob qulflangan, parol o‘rnatilmagan

**Buyruqlar**

| Buyruq    | Parametrlar                                    | Tavsif                                    |
|-----------|-----------------------------------------------|-------------------------------------------|
| `id`      | `foydalanuvchi`                               | Foydalanuvchi ID va guruhlarini ko‘rsatish |
| [`who`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/017-the-who-command.md)      |                                               | Tizimga kirgan foydalanuvchilarni ko‘rsatish |
| [`last`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/048-the-last-command.md)     |                                               | Oxirgi kirishlarni ko‘rsatish             |
| `lastb`   |                                               | Oxirgi muvaffaqiyatsiz kirishlarni ko‘rsatish |
| [`sudo`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/051-the-sudo-command.md)     | `-u foydalanuvchi buyruq`                     | Buyruqni foydalanuvchi huquqlari bilan bajarish (standart root) |
|           | `-i` yoki `su -`                              | Root huquqlari bilan shell                |
| [`su`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/044-the-su-command.md)       |                                               | Root sifatida shell (kirish shellsiz)     |
|           | `-`                                           | Root sifatida shell (kirish shell)        |
|           | `- foydalanuvchi`                             | Foydalanuvchi sifatida shell              |
| [`useradd`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/080-the-useradd-command.md)  | `-u 2101 -g asosiyguruh -c izoh foydalanuvchi` | Foydalanuvchi yaratish ( `-g` siz yangi guruh yaratiladi) |
| [`usermod`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/082-the-usermod-command.md)  | `-G guruh1,guruh2`                            | Ikkinchi darajali guruhlarni belgilash (qayta yozish) |
|           | `-ag guruh,guruh2`                            | Ikkinchi darajali guruhlarni qo‘shish     |
|           | `-l foydalanuvchi`                            | Foydalanuvchi nomini o‘zgartirish         |
|           | `-L`                                          | Hisobni qulflash                          |
|           | `-U`                                          | Hisobni qulfdan chiqarish                 |
|           | `-s shell_yo‘li`                              | Shellni o‘zgartirish                      |
| [`userdel`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/081-the-userdel-command.md)  | `-r foydalanuvchi`                            | Foydalanuvchini uy va pochta fayllari bilan o‘chirish |
| [`passwd`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/025-the-passwd-command.md)   | `foydalanuvchi`                               | Parolni o‘zgartirish (interaktiv)         |
| `groupadd` | `guruhnomi`                                  | Guruh yaratish (`-g` bilan GID o‘rnatish mumkin) |
| `groupdel` | `guruhnomi`                                  | Guruhni o‘chirish                         |

# Fayl Tizimi Ruxsatnomalari

Ruxsatnomalar quyidagilarga o‘rnatiladi:

- Foydalanuvchi (egasi)
- Guruh (egasi)
- Boshqalar

Faqat root *Foydalanuvchi* ni o‘zgartira oladi. *Foydalanuvchi* *Guruh* ni o‘zgartira oladi.

Asosiy ruxsatnomalar (birlashtirish uchun ikkilik bayroqlarni qo‘shing):

| Belgi | Ikkilik Bayroq | Ruxsatnoma |
|-------|----------------|------------|
| r     | 4              | o‘qish     |
| w     | 2              | yozish     |
| x     | 1              | bajarish   |

Kengaytirilgan ruxsatnomalar (asosiy ruxsatnomalar oldiga qo‘yiladi: `chmod 1777 shared`):

| Belgi | Ikkilik Bayroq | Nomi       | Tavsif                                                                |
|-------|----------------|------------|-----------------------------------------------------------------------|
| t / T | 1              | Sticky Bit | *Boshqalar* tarkibni o‘chira olmaydi (faqat papkalar uchun)           |
| s / S | 2              | SGID-Bit   | Fayl: *Guruh* huquqlari bilan ishlaydi<br>Papka: Yangi elementlar *Guruh* ni meros qilib oladi |
| s / S | 4              | SUID-Bit   | Fayl *Foydalanuvchi* huquqlari bilan ishlaydi (faqat fayllar uchun)   |

Kengaytirilgan ruxsatnomalar `ls -l` da **x** ni almashtiradi. Agar **x** o‘rnatilgan bo‘lsa kichik harf, aks holda katta harf.

*O‘qish* ruxsatnomasi papkani ko‘rishga imkon beradi, lekin tarkibini emas. Tarkibni ko‘rish uchun *bajarish* ruxsatnomasi kerak.

**Buyruqlar**

| Buyruq   | Opsiyalar                    | Tavsif                                      |
|----------|-----------------------------|---------------------------------------------|
| [`chmod`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/106-the-chmod-command.md)   | `-R [uog] papkanomi`       | Ruxsatnomalarni rekursiv ravishda o‘rnatish |
|          | `+[suog] faylnomi`         | Ikkilik bayroqlar yordamida ruxsat qo‘shish |
|          | `-[suog] faylnomi`         | Ikkilik bayroqlar yordamida ruxsatni olib tashlash |
|          | `u+x faylnomi`             | *Foydalanuvchi* uchun *bajarish* ruxsatini qo‘shish |
|          | `g+wx faylnomi`            | *Guruh* uchun *yozish* va *bajarish* ruxsatlarini qo‘shish |
|          | `o-r faylnomi`             | *Boshqalar* uchun *o‘qish* ruxsatini olib tashlash |
| [`chown`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/101-the-chown-command.md)   | `-R foydalanuvchi:guruh faylnomi` | Egani (*Foydalanuvchi* va *Guruh*) rekursiv ravishda o‘zgartirish |
|          | `foydalanuvchi faylnomi`   | Egani (*Foydalanuvchi*) o‘zgartirish        |
|          | `:guruh faylnomi`          | Egani (*Guruh*) o‘zgartirish                |
| `chgroup`| `guruh faylnomi`           | Egani (*Guruh*) o‘zgartirish                |

# SSH

[`SSH`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/089-the-ssh-command.md)
Sozlamalar `/etc/ssh/sshd_config` da amalga oshiriladi.

O‘zgarishlarni qo‘llash uchun SSH xizmatini qayta yuklang: `systemctl reload sshd`!

DenyUsers, AllowUsers, DenyGroups, AllowGroups bir-birini qayta yozadi va yuqoridagi tartibda qo‘llaniladi.

| Sozlama           | Opsiya             | Tavsif                                   |
|-------------------|--------------------|------------------------------------------|
| `PermitRootLogin` | `no`               | Root uchun SSH orqali kirishni taqiqlash |
|                   | `yes`              | Root uchun SSH orqali kirishga ruxsat    |
|                   | `without-password` | Faqat shaxsiy/ommaviy kalit autentifikatsiyasi bilan ruxsat |
| `AllowUsers`      | `foydalanuvchi1 foydalanuvchi2` | Faqat foydalanuvchi1 va foydalanuvchi2 ga ruxsat |
| `DenyUsers`       | `foydalanuvchi1 foydalanuvchi2` | Hammaga ruxsat, faqat foydalanuvchi1 va foydalanuvchi2 dan tashqari |
| `AllowGroups`     | `guruh1 guruh2`    | Faqat belgilangan guruhlardagi foydalanuvchilarga ruxsat |
| `DenyGroups`      | `guruh1 guruh2`    | Hammaga ruxsat, faqat belgilangan guruhlardagi foydalanuvchilardan tashqari |

# Cronjobs

**[`Crontab`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/091-the-crontab-command.md)**

Cronjoblar crontab fayllarida sozlanadi. Ushbu fayllarni to‘g‘ridan-to‘g‘ri tahrirlamang. Buning o‘rniga `crontab -e` dan foydalaning. Bu saqlangandan so‘ng cronjobni faollashtirish uchun barcha kerakli amallarni bajaradi. Joylashuvlar quyidagicha:

- `/var/spool/cron/foydalanuvchi` foydalanuvchiga xos
- `/etc/crontab` tizim bo‘yicha crontab

Fayllar formati (foydalanuvchiga xos crontablarda *foydalanuvchi-nomi* ustuni bo‘lmaydi):



| Buyruq                          | Tavsif                          |
|---------------------------------|---------------------------------|
| `rpm -q cronie`                 | Paket o‘rnatilganligini tekshirish |
| `systemctl status crond.service` | Xizmat ishlayotganligini tekshirish |
| `crontab -l`                    | Joriy foydalanuvchi crontabini ro‘yxatlash |
| `crontab -e`                    | Joriy foydalanuvchi crontabini tahrirlash |
| `crontab -e -u foydalanuvchi`   | Belgilangan foydalanuvchi crontabini tahrirlash |
| `crontab -r`                    | Joriy foydalanuvchi crontabini o‘chirish |

**Skript papkalari**

Quyidagi papkalardagi skriptlar papka nomida ko‘rsatilgan vaqt oralig‘ida ishga tushiriladi:

- `/etc/cron.hourly`
- `/etc/cron.daily`
- `/etc/cron.weekly`
- `/etc/cron.monthly`

**Ruxsat berish / Taqiqlash**

Foydalanuvchi nomlarini quyidagi fayllarga bir qatordan qo‘shing:

- `/etc/cron.allow` Oq ro‘yxat
- `/etc/cron.deny` Qora ro‘yxat

Agar hech qanday fayl mavjud bo‘lmasa, barcha foydalanuvchilarga ruxsat beriladi.

**Loglar va Natijalar**

Cronjoblarning bajarilishi `/var/log/cron` da qayd etiladi.
Natijalar foydalanuvchi pochtasiga `/var/spool/mail/foydalanuvchi` ga yuboriladi.

# Paket Boshqaruvi

## RPM

[`RPM`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/075-the-rpm-command.md)

| Buyruq                  | Tavsif                               |
|------------------------|--------------------------------------|
| `rpm -i rpmfayl\|rpmurl` | Paketni o‘rnatish                   |
| `rpm -e paketnomi`     | Paketni o‘chirish                   |
| `rpm -q paketnomi`     | Paket o‘rnatilganligini tekshirish  |
| `rpm -ql paketnomi`    | Paketdagi fayllarni ro‘yxatlash     |
| `rpm -qa`              | Barcha o‘rnatilgan paketlarni ro‘yxatlash |
| `rpm -qf /fayl_yo‘li`  | Faylni o‘rnatgan paketni aniqlash   |
| `rpm -qf $(which <exe>)` | Ijro faylini o‘rnatgan paketni aniqlash |
| `rpm -V paketnomi`     | O‘rnatilgan paketni tekshirish      |

## YUM

[`YUM`](https://github.com/bobbyiliev/101-linux-commands-ebook/blob/main/ebook/en/content/053-the-yum-command.md) `/etc/yum.conf` da sozlanadi

Repolar `/etc/yum.repos.d/` da sozlanadi

Log `/var/log/yum.log` da

| Buyruq                               | Tavsif                               |
|-------------------------------------|--------------------------------------|
| `yum install paketnomi [-y]`        | Paketni o‘rnatish (`-y` tasdiqlamasdan) |
| `yum remove paketnomi`              | Paketni o‘chirish                   |
| `yum update`                        | Barcha o‘rnatilgan paketlarni yangilash |
| `yum update paketnomi`              | Maxsus paketni yangilash            |
| `yum update naqsh*`                 | Joker belgi yordamida paketlarni yangilash |
| `yum info paketnomi`                | Paket haqida batafsil ma’lumot      |
| `yum list paketnomi`                | O‘rnatilgan va mavjud paketlarni ro‘yxatlash |
| `yum search qidiruv_so‘zi`          | Paketni qidirish (nomi va xulosa bo‘yicha) |
| `yum search all qidiruv_so‘zi`      | Paketni qidirish (barcha ma’lumotlar bo‘yicha) |
| `yum deplist paketnomi`             | Paket qaramliklarini ro‘yxatlash    |
| `yum reinstall paketnomi`           | Paketni qayta o‘rnatish (buzilgan bo‘lsa) |
| `yumdownloader --resolve paketnomi` | RPM paketini qaramliklari bilan yuklab olish |

---

# 📃 Kategoriyalar bo‘yicha buyruqlar ro‘yxati:

Agar hissa qo‘shmoqchi bo‘lsangiz, `TODO` deb belgilangan mavzuni tanlab, pull request yuboring 🙌

Agar ro‘yxatda yoqtirgan mavzungiz bo‘lmasa, yangi mavzu qo‘shishingiz mumkin.

---

### Papkalar bo‘yicha navigatsiya

- [cd](ebook/en/content/002-the-cd-command.md) - joriy papkani o‘zgartirish
- [ls](ebook/en/content/001-the-ls-command.md) - papka tarkibini ro‘yxatlash
- [dir](ebook/en/content/057-the-dir-command.md) - papka ro‘yxatini ustunli formatda ko‘rsatish
- [pwd](ebook/en/content/006-the-pwd-command.md) - joriy papka nomini ko‘rsatish
- [tree](ebook/en/content/095-the-tree-command.md) - pastki papkalarni daraxt shaklida ro‘yxatlash

### Fayl buyruqlari

- [cat/tac](ebook/en/content/003-the-cat-tac-command.md) - fayllarni birlashtirish va chop etish
- [diff/sdiff](ebook/en/content/062-the-diff-sdiff-command.md) - fayllarni qator bo‘yicha taqqoslash
- [find](ebook/en/content/102-the-find-command.md) - fayllarni qidirish
- [grep](ebook/en/content/107-the-grep-command.md) - fayl naqshlarini qidiruvchi
- [head](ebook/en/content/004-the-head-command.md) - faylning dastlabki qatorlarini ko‘rsatish
- [locate](ebook/en/content/049-the-locate-command.md) - fayl va papkalarni topish
- [stat](ebook/en/content/079-the-stat-command.md) - fayl holatini ko‘rsatish
- [tail](ebook/en/content/005-the-tail-command.md) - faylning oxirgi qatorlarini ko‘rsatish
- [uniq](ebook/en/content/074-the-uniq-command.md) - takrorlanadigan qatorlarni filtrlash yoki hisobot qilish

### Fayl va Papka Manipulyatsiyasi

- [awk](ebook/en/content/090-the-awk-command.md) - naqshga yo‘naltirilgan skanlash va qayta ishlash tili
- [chmod](ebook/en/content/106-the-chmod-command.md) - ruxsatnomalarni o‘zgartirish
- [chown](ebook/en/content/101-the-chown-command.md) - fayl egasi va guruhini o‘zgartirish
- [cp](ebook/en/content/031-the-cp-command.md) - fayl va papkalarni nusxalash
- [cut](ebook/en/content/098-the-cut-command.md) - fayllardan qismlarni olib tashlash
- [mkdir](ebook/en/content/014-the-mkdir-command.md) - yangi papka yaratish
- [mv](ebook/en/content/032-the-mv-command.md) - fayl va papkalarni ko‘chirish
- [nano](ebook/en/content/039-the-nano-command.md) - matn muharriri
- [rm](ebook/en/content/040-the-rm-command.md) - fayl va papkalarni o‘chirish
- [rmdir](ebook/en/content/103-the-rmdir-command.md) - papkani o‘chirish
- [paste](ebook/en/content/060-the-paste-command.md) - fayl qatorlarini birlashtirish
- [rsync](ebook/en/content/086-the-rsync-command.md) - masofadan nusxalash
- [scp](ebook/en/content/076-the-scp-command.md) - xavfsiz nusxalash
- [basename](ebook/en/content/111-the-basename-command.md) - fayl yo‘lidan papka ma’lumotlari va qo‘shimchalarni olib tashlash
- [sed](ebook/en/content/099-the-sed-command.md) - matn o‘zgartirish vositasi
- [sort](ebook/en/content/059-the-sort-command.md) - fayl qatorlarini tartiblash yoki birlashtirish
- [split](ebook/en/content/078-the-split-command.md) - faylni bo‘laklarga bo‘lish
- [touch](ebook/en/content/007-the-touch-command.md) - faylga kirish va o‘zgartirish vaqtlarini o‘zgartirish
- [vim](ebook/en/content/100-the-vim-command.md) - matn muharriri

### Paket arxivlash va siqish vositalari

- [bzip2](ebook/en/content/069-the-bzip2-command.md) - blok saralash fayl siqish vositasi
- [gzip](ebook/en/content/015-the-gzip-command.md) - siqish vositasi
- [gunzip](ebook/en/content/064-the-gunzip-command.md) - dekompressiya vositasi
- [tar](ebook/en/content/063-the-tar-command.md) - arxivlarni yaratish, ochish va manipulyatsiya qilish
- [zip](ebook/en/content/054-the-zip-command.md) - fayllarni paketlash va siqish
- [unzip](ebook/en/content/055-the-unzip-command.md) - ZIP fayllarni ro‘yxatlash, sinash, ochish

### Tizim buyruqlari

- [crontab](ebook/en/content/091-the-crontab-command.md) - cron daemonini boshqarish uchun individual jadvallarni saqlash
- [df](ebook/en/content/010-the-df-command.md) - bo‘sh disk joyini ko‘rsatish
- [du](ebook/en/content/084-the-du-command.md) - disk foydalanish statistikasini ko‘rsatish
- [free](ebook/en/content/018-the-free-command.md) - xotira foydalanish ma’lumotlarini ko‘rsatish
- [hostname](ebook/en/content/038-the-hostname-command.md) - joriy xost tizim nomini o‘rnatish yoki ko‘rsatish
- [hostnamectl](ebook/en/content/065-the-hostnamectl-command.md) - xostnomi sozlamalarini o‘zgartirish
- [ionice](ebook/en/content/083-the-ionice-command.md) - I/O jarayon ustuvorligini olish/o‘rnatish
- [iostat](ebook/en/content/050-the-iostat-command.md) - I/O statistikasi
- [kill](ebook/en/content/034-the-kill-command.md) - jarayonni ID bo‘yicha to‘xtatish yoki signal yuborish
- [killall](ebook/en/content/035-the-killall-command.md) - jarayonlarni nomi bo‘yicha to‘xtatish
- [lsblk](ebook/en/content/104-the-lsblk-command.md) - blok va tsikl qurilmalarini ko‘rsatish
- [lsof](ebook/en/content/068-the-lsof-command.md) - ochiq fayllarni ro‘yxatlash
- [mpstat](ebook/en/content/072-the-mpstat-command.md) - CPU statistikasi
- [ncdu](ebook/en/content/073-the-ncdu-command.md) - curses asosidagi disk foydalanish
- [ps](ebook/en/content/033-the-ps-command.md) - jarayon holatini ko‘rsatish
- [pstree](ebook/en/content/094-the-pstree-command.md) - jarayonlarni daraxt formatida ko‘rsatish
- [reboot](ebook/en/content/058-the-reboot-command.md) - tizimni qayta yuklash
- [service](ebook/en/content/070-the-service-command.md) - boshlang‘ich skriptni ishga tushirish
- [shutdown](ebook/en/content/056-the-shutdown-command.md) - tizimni belgilangan vaqtda yopish
- [top/htop](ebook/en/content/019-the-top-htop-command.md) - jarayon ma’lumotlarini ko‘rsatish
- [uname](ebook/en/content/013-the-uname-command.md) - operatsion tizim tafsilotlarini chop etish
- [useradd](ebook/en/content/080-the-useradd-command.md) - foydalanuvchi hisoblarini qo‘shish/yangilash
- [userdel](ebook/en/content/081-the-userdel-command.md) - foydalanuvchi hisobini o‘chirish
- [usermod](ebook/en/content/082-the-usermod-command.md) - foydalanuvchi xususiyatlarini o‘zgartirish
- [vmstat](ebook/en/content/071-the-vmstat-command.md) - virtual xotira statistikasi
- [whereis](ebook/en/content/096-the-whereis-command.md) - dasturlarni topish

### Tarmoq buyruqlari

- [dig](ebook/en/content/087-the-dig-command.md) - DNS qidiruv vositasi
- [ifconfig](ebook/en/content/041-the-ifconfig-command.md) - tarmoq interfeysi parametrlarini sozlash
- [ip](ebook/en/content/042-the-ip-command.md) - tarmoq boshqaruv vazifalarini bajarish
- [iptable](ebook/en/content/066-the-iptable-command.md) - IPv4 tarmoq devorini sozlash
- [lscpu](ebook/en/content/030-the-lscpu-command.md) - CPU arxitekturasi ma’lumotlarini ko‘rsatish
- [netstat](ebook/en/content/067-the-netstat-command.md) - tarmoq holatini ko‘rsatish
- [ping](ebook/en/content/085-the-ping-command.md) - tarmoq ulanishini tekshirish
- [whois](ebook/en/content/088-the-whois-command.md) - internet domen nomlari va tarmoq raqamlari haqida ma’lumot

### Paket boshqaruvi

- [apt](ebook/en/content/052-the-apt-command.md) - Debian paket boshqaruvi
- [rpm](ebook/en/content/075-the-rpm-command.md) - RPM paket boshqaruvchisi (RedHat)
- [yum](ebook/en/content/053-the-yum-command.md) - RedHat Linux uchun paket boshqaruvchisi

### Foydalanuvchi ma’lumotlari buyruqlari
Foydalanuvchi o‘zgartirish uchun tizim buyruqlari ostidagi useradd, userdel, usermod ga qarang

- [groups](ebook/en/content/023-the-groups-command.md) - guruh a’zoliklarini ko‘rsatish
- [finger](ebook/en/content/022-the-finger-command.md) - foydalanuvchilar haqida ma’lumot ko‘rsatish
- [last](ebook/en/content/048-the-last-command.md) - eng so‘nggi foydalanuvchi kirishlarini ko‘rsatish
- [passwd](ebook/en/content/025-the-passwd-command.md) - foydalanuvchi parolini o‘zgartirish
- [w](ebook/en/content/026-the-w-command.md) - kim tizimga kirgan va nima qilayotganini ko‘rsatish
- [who](ebook/en/content/017-the-who-command.md) - tizimga kirganlarni ko‘rsatish
- [whoami](ebook/en/content/027-the-whoami-command.md) - joriy foydalanuvchi ID sini ko‘rsatish

### Sessiya buyruqlari

- [clear](ebook/en/content/043-the-clear-command.md) - terminal ekranini tozalash
- [env](ebook/en/content/036-the-env-command.md) - muhit o‘zgaruvchilarini ko‘rsatish yoki buyruq uchun o‘zgaruvchilarni o‘rnatish
- [exit](ebook/en/content/061-the-exit-command.md) - faol sessiya/shellni yopish
- [printenv](ebook/en/content/037-the-printenv-command.md) - belgilangan muhit o‘zgaruvchilarini chop etish
- [history](ebook/en/content/028-the-history-command.md) - buyruqlar tarixini ko‘rsatish
- [login](ebook/en/content/029-the-login-command.md) - kirish va foydalanuvchi sessiyasini boshlash
- [nohup](ebook/en/content/093-the-nohup-command.md) - uzilishlarga chidamli vositani ishga tushirish
- [sleep](ebook/en/content/077-the-sleep-command.md) - bajarishni vaqt oralig‘ida to‘xtatish
- [ssh](ebook/en/content/089-the-ssh-command.md) - xavfsiz shell kirish
- [su](ebook/en/content/044-the-su-command.md) - foydalanuvchi identifikatorini almashtirish
- [sudo](ebook/en/content/051-the-sudo-command.md) - buyruqni boshqa foydalanuvchi sifatida bajarish
- [screen](ebook/en/content/108-the-screen-command.md) - ekran sessiyasini boshlash

### Yordam olish

- [man](ebook/en/content/024-the-man-command.md) - onlayn qo‘llanma sahifalarini formatlash va ko‘rsatish
- [help](ebook/en/content/011-the-help-command.md) - ‘man’ qamrab olmaydigan asosiy buyruqlar haqida yordam ko‘rsatish
- [whatis](ebook/en/content/016-the-whatis-command.md) - buyruqlarning bir qatorli tavsiflarini ko‘rsatish

### Ilovalar

- [bc](ebook/en/content/009-the-bc-command.md) - asosiy kalkulyator
- [cal](ebook/en/content/008-the-cal-command.md) - kalendarni ko‘rsatish
- [cmatrix](ebook/en/content/105-the-cmatrix-command.md) - Matrixga kirish
- [curl](ebook/en/content/046-the-curl-command.md) - serverga yoki serverdan ma’lumot uzatish
- [echo](ebook/en/content/021-the-echo-command.md) - talqin qilingan argumentlarni ko‘rsatish
- [factor](ebook/en/content/012-the-factor-command.md) - raqamlarning tub omillarini chop etish
- [printf](ebook/en/content/097-the-printf-command.md) - chiqishni formatlash
- [sl](ebook/en/content/020-the-sl-command.md) - terminalda bug‘ lokomotivini ishga tushirish
- [wget](ebook/en/content/045-the-wget-command.md) - interaktiv bo‘lmagan veb fayl yuklab olish
- [xargs](ebook/en/content/092-the-xargs-command.md) - argumentlar ro‘yxatini yaratish va vositani ishga tushirish
- [yes](ebook/en/content/047-the-yes-command.md) - doimiy chiqish oqimini chop etish
- [banner](ebook/en/content/112-the-banner-command.md) - ASCII belgi satrlarini katta harflarda chop etish
- [aplay](ebook/en/content/125-the-aplay-command.md) - audio fayllarni buyruq satridan ijro etish
- [spd-say](ebook/en/content/126-the-spd-say-command.md) - berilgan matnni tovush sifatida ijro etish

---

# 📃 Boblar bo‘yicha buyruqlar ro‘yxati:

Agar hissa qo‘shmoqchi bo‘lsangiz, mavzuni tanlab, `Yangi Misollar | [Opsiyalar]` bilan yangilab, pull request yuboring 🙌

Agar ro‘yxatda yoqtirgan mavzungiz bo‘lmasa, yangi mavzu qo‘shishingiz mumkin.

- [001-the-ls-command.md](ebook/en/content/001-the-ls-command.md)
- [002-the-cd-command.md](ebook/en/content/002-the-cd-command.md)
- [003-the-cat-tac-command.md](ebook/en/content/003-the-cat-tac-command.md)
- [004-the-head-command.md](ebook/en/content/004-the-head-command.md)
- [005-the-tail-command.md](ebook/en/content/005-the-tail-command.md)
- [006-the-pwd-command.md](ebook/en/content/006-the-pwd-command.md)
- [007-the-touch-command.md](ebook/en/content/007-the-touch-command.md)
- [008-the-cal-command.md](ebook/en/content/008-the-cal-command.md)
- [009-the-bc-command.md](ebook/en/content/009-the-bc-command.md)
- [010-the-df-command.md](ebook/en/content/010-the-df-command.md)
- [011-the-help-command.md](ebook/en/content/011-the-help-command.md)
- [012-the-factor-command.md](ebook/en/content/012-the-factor-command.md)
- [013-the-uname-command.md](ebook/en/content/013-the-uname-command.md)
- [014-the-mkdir-command.md](ebook/en/content/014-the-mkdir-command.md)
- [015-the-gzip-command.md](ebook/en/content/015-the-gzip-command.md)
- [016-the-whatis-command.md](ebook/en/content/016-the-whatis-command.md)
- [017-the-who-command.md](ebook/en/content/017-the-who-command.md)
- [018-the-free-command.md](ebook/en/content/018-the-free-command.md)
- [019-the-top-htop-command.md](ebook/en/content/019-the-top-htop-command.md)
- [020-the-sl-command.md](ebook/en/content/020-the-sl-command.md)
- [021-the-echo-command.md](ebook/en/content/021-the-echo-command.md)
- [022-the-finger-command.md](ebook/en/content/022-the-finger-command.md)
- [023-the-groups-command.md](ebook/en/content/023-the-groups-command.md)
- [024-the-man-command.md](ebook/en/content/024-the-man-command.md)
- [025-the-passwd-command.md](ebook/en/content/025-the-passwd-command.md)
- [026-the-w-command.md](ebook/en/content/026-the-w-command.md)
- [027-the-whoami-command.md](ebook/en/content/027-the-whoami-command.md)
- [028-the-history-command.md](ebook/en/content/028-the-history-command.md)
- [029-the-login-command.md](ebook/en/content/029-the-login-command.md)
- [030-the-lscpu-command.md](ebook/en/content/030-the-lscpu-command.md)
- [031-the-cp-command.md](ebook/en/content/031-the-cp-command.md)
- [032-the-mv-command.md](ebook/en/content/032-the-mv-command.md)
- [033-the-ps-command.md](ebook/en/content/033-the-ps-command.md)
- [034-the-kill-command.md](ebook/en/content/034-the-kill-command.md)
- [035-the-killall-command.md](ebook/en/content/035-the-killall-command.md)
- [036-the-env-command.md](ebook/en/content/036-the-env-command.md)
- [037-the-printenv-command.md](ebook/en/content/037-the-printenv-command.md)
- [038-the-hostname-command.md](ebook/en/content/038-the-hostname-command.md)
- [039-the-nano-command.md](ebook/en/content/039-the-nano-command.md)
- [040-the-rm-command.md](ebook/en/content/040-the-rm-command.md)
- [041-the-ifconfig-command.md](ebook/en/content/041-the-ifconfig-command.md)
- [042-the-ip-command.md](ebook/en/content/042-the-ip-command.md)
- [043-the-clear-command.md](ebook/en/content/043-the-clear-command.md)
- [044-the-su-command.md](ebook/en/content/044-the-su-command.md)
- [045-the-wget-command.md](ebook/en/content/045-the-wget-command.md)
- [046-the-curl-command.md](ebook/en/content/046-the-curl-command.md)
- [047-the-yes-command.md](ebook/en/content/047-the-yes-command.md)
- [048-the-last-command.md](ebook/en/content/048-the-last-command.md)
- [049-the-locate-command.md](ebook/en/content/049-the-locate-command.md)
- [050-the-iostat-command.md](ebook/en/content/050-the-iostat-command.md)
- [051-the-sudo-command.md](ebook/en/content/051-the-sudo-command.md)
- [052-the-apt-command.md](ebook/en/content/052-the-apt-command.md)
- [053-the-yum-command.md](ebook/en/content/053-the-yum-command.md)
- [054-the-zip-command.md](ebook/en/content/054-the-zip-command.md)
- [055-the-unzip-command.md](ebook/en/content/055-the-unzip-command.md)
- [056-the-shutdown-command.md](ebook/en/content/056-the-shutdown-command.md)
- [057-the-dir-command.md](ebook/en/content/057-the-dir-command.md)
- [058-the-reboot-command.md](ebook/en/content/058-the-reboot-command.md)
- [059-the-sort-command.md](ebook/en/content/059-the-sort-command.md)
- [060-the-paste-command.md](ebook/en/content/060-the-paste-command.md)
- [061-the-exit-command.md](ebook/en/content/061-the-exit-command.md)
- [062-the-diff-sdiff-command.md](ebook/en/content/062-the-diff-sdiff-command.md)
- [063-the-tar-command.md](ebook/en/content/063-the-tar-command.md)
- [064-the-gunzip-command.md](ebook/en/content/064-the-gunzip-command.md)
- [065-the-hostnamectl-command.md](ebook/en/content/065-the-hostnamectl-command.md)
- [066-the-iptable-command.md](ebook/en/content/066-the-iptable-command.md)
- [067-the-netstat-command.md](ebook/en/content/067-the-netstat-command.md)
- [068-the-lsof-command.md](ebook/en/content/068-the-lsof-command.md)
- [069-the-bzip2-command.md](ebook/en/content/069-the-bzip2-command.md)
- [070-the-service-command.md](ebook/en/content/070-the-service-command.md)
- [071-the-vmstat-command.md](ebook/en/content/071-the-vmstat-command.md)
- [072-the-mpstat-command.md](ebook/en/content/072-the-mpstat-command.md)
- [073-the-ncdu-command.md](ebook/en/content/073-the-ncdu-command.md)
- [074-the-uniq-command.md](ebook/en/content/074-the-uniq-command.md)
- [075-the-rpm-command.md](ebook/en/content/075-the-rpm-command.md)
- [076-the-scp-command.md](ebook/en/content/076-the-scp-command.md)
- [077-the-sleep-command.md](ebook/en/content/077-the-sleep-command.md)
- [078-the-split-command.md](ebook/en/content/078-the-split-command.md)
- [079-the-stat-command.md](ebook/en/content/079-the-stat-command.md)
- [080-the-useradd-command.md](ebook/en/content/080-the-useradd-command.md)
- [081-the-userdel-command.md](ebook/en/content/081-the-userdel-command.md)
- [082-the-usermod-command.md](ebook/en/content/082-the-usermod-command.md)
- [083-the-ionice-command.md](ebook/en/content/083-the-ionice-command.md)
- [084-the-du-command.md](ebook/en/content/084-the-du-command.md)
- [085-the-ping-command.md](ebook/en/content/085-the-ping-command.md)
- [086-the-rsync-command.md](ebook/en/content/086-the-rsync-command.md)
- [087-the-dig-command.md](ebook/en/content/087-the-dig-command.md)
- [088-the-whois-command.md](ebook/en/content/088-the-whois-command.md)
- [089-the-ssh-command.md](ebook/en/content/089-the-ssh-command.md)
- [090-the-awk-command.md](ebook/en/content/090-the-awk-command.md)
- [091-the-crontab-command.md](ebook/en/content/091-the-crontab-command.md)
- [092-the-xargs-command.md](ebook/en/content/092-the-xargs-command.md)
- [093-the-nohup-command.md](ebook/en/content/093-the-nohup-command.md)
- [094-the-pstree-command.md](ebook/en/content/094-the-pstree-command.md)
- [095-the-tree-command.md](ebook/en/content/095-the-tree-command.md)
- [096-the-whereis-command.md](ebook/en/content/096-the-whereis-command.md)
- [097-the-printf-command.md](ebook/en/content/097-the-printf-command.md)
- [098-the-cut-command.md](ebook/en/content/098-the-cut-command.md)
- [099-the-sed-command.md](ebook/en/content/099-the-sed-command.md)
- [100-the-vim-command.md](ebook/en/content/100-the-vim-command.md)
- [101-the-chown-command.md](ebook/en/content/101-the-chown-command.md)
- [102-the-find-command.md](ebook/en/content/102-the-find-command.md)
- [103-the-rmdir-command.md](ebook/en/content/103-the-rmdir-command.md)
- [104-the-lsblk-command.md](ebook/en/content/104-the-lsblk-command.md)
- [105-the-cmatrix-command.md](ebook/en/content/105-the-cmatrix-command.md)
- [106-the-chmod-command.md](ebook/en/content/106-the-chmod-command.md)
- [107-the-grep-command.md](ebook/en/content/107-the-grep-command.md)
- [108-the-screen-command.md](ebook/en/content/108-the-screen-command.md)
- [109-the-nc-command.md](ebook/en/content/109-the-nc-command.md)
- [110-the-make-command.md](ebook/en/content/110-the-make-command.md)
- [111-the-basename-command.md](ebook/en/content/111-the-basename-command.md)
- [112-the-banner-command.md](ebook/en/content/112-the-banner-command.md)
- [113-the-alias-command.md](