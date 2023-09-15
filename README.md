# API Spec

## Carusol

Request :
- Method : GET
- Endpoint : `/mobile/v1/carusol`
- Header : null


Response :

```json 
{
    "data" : [
        {
          "nama_file":
              "https://1.bp.blogspot.com/-lTJvQzNtTRw/XMTxH9UGFCI/AAAAAAAAPFQ/iVfu94tODOQ_AVuG1m-zN1Hl4NcipaCIACLcBGAs/s1600/event.png", //String
          "keterangan": "Gambar Carousel 1", //String
          "link": "https://www.example.com/carousel1", //String
          "status": "aktif", //String
          "tanggal": "2023-08-30" //String || date y-m-d
        },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Auth

### Registrasi

#### Registrasi Akun

Request :
- Method : POST
- Endpoint : `/mobile/v1/register`
- Header : null
- Body :

```json 
{
    "nohp": "number",
    "noregistrasi" : "String",
    "role" : "string",
    "imei": "String"
}
```

Response :

```json 
{
    "data" : {
            "noRegistrasi": "981123000001", //String
            "namaLengkap": "RAHMAD FARIZAN",//String
            "idSekolahKelas": "14",//String
            "namaSekolahKelas": "12 SMA IPA",//String
            "siapa": "SISWA",//String
            "idKelas": "265287",//String
            "namaKelas": "12-IPA-R-N-T-1",//String
            "jenisKelas": null,//String
            "idGedung": "675",//String
            "namaGedung": "KOMBES H. UMAR 75",//String
            "idKota": "214",//String
            "namaKota": "PAGARALAM",//String
            "idSekolah": "117724",//String
            "namaSekolah": "MAN Sidoarjo",//String
            "tahunAjaran": "2023/2024",//String
            "c_Statusbayar": "LUNAS",//String
            "email": "rahmad.farizan.rf@gmail.com", //String
            "emailOrtu": "0@gmail.com",//String
            "nomorHp": "082286968275",//String
            "nomorHpOrtu": "082286968274"//String
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Login

#### Login Siswa

Request :
- Method : POST
- Endpoint : `/mobile/v1/login-siswa`
- Header : null
- Body :

```json 
{
    "noHp" : "number",
    "imei"  : "String"
}
```

Response :

```json 
{
    "data": {
            "noRegistrasi": "040916026101",//String
            "namaLengkap": "YAZID FAUZAN HARTONO",//String
            "idSekolahKelas": "15",//String
            "namaSekolahKelas": "12 SMA IPS",//String
            "siapa": "SISWA",//String
            "idKelas": "254562,266691",//String
            "namaKelas": "12-IPS-R-N-2202,12-IPA-R-N-B01",//String
            "jenisKelas": "REGULER NON SD",//String
            "idGedung": "261",//String
            "namaGedung": "CIPUTAT No. 75 A",//String
            "idKota": "287",//String
            "namaKota": "JAKARTA 4",//String
            "idSekolah": "391007",//String
            "namaSekolah": "SMA ISLAM TERPADU AL-MULTAZAM 2 LINGGAJATI",//String
            "tahunAjaran": "2022/2023",//String
            "c_Statusbayar": "LUNAS",//String
            "email": "fauznn16@gmail.com",//String
            "emailOrtu": "tugas.ibutini@gmail.com",//String
            "nomorHp": "083166563212",//String
            "nomorHpOrtu": "081384965686"//String
        },
        "statusBayar": "",//String
        "pilihanPTN": "{\"pilihan1\":3212146,\"pilihan2\":3632027,\"historyPilihan\":[{\"pilihan\":1,\"tanggal\":\"2023-04-05 18:42:23\",\"idJurusan\":3212146},{\"pilihan\":2,\"tanggal\":\"2023-04-05 18:42:50\",\"idJurusan\":3632027}]}",//object
        "jobOrtu": "",//String
        "daftarAnak": [],//array
        "tokenJWT": "String",//String
        "daftarProduk": [
            {
                "c_IdKomponentProduk": "30659",//String
                "c_IdBundling": "718868",//String
                "c_NamaBundling": "TWT 12 IPA Super Intensif Unit Ciputat : 12 KBM",//String
                "c_NamaProduk": "Ebook Teori Superintensif 12 IPA",//String
                "c_IdJenisProduk": "98",//String
                "c_NamaJenisProduk": "e- Teori Ringkas",//String
                "c_TanggalAwal": "2023-04-03",//String
                "c_TanggalAkhir": "2023-09-30",//String
                "c_IdSekolahKelas": "14"//String
            },
          
        ],//array
        "waktu": "180",//String
        "kirimOTP": false,//bool

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
### Get Imei

Request :
- Method : POST
- Endpoint : `/mobile/v1/auth/imei`
- Header : null

Response :

```json 
{
    "data" : {
           "imei":"d62b5b264fdc7baa" //String
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## SEND Verfikasi dan Validasi

### Send OTP Via WhatsApp

Request :
- Method : POST
- Endpoint : `/mobile/v1/auth/otp-wa`
- Header : null
- Body :

```json 
{
    "nohp" : "string",
    "id_device" : "string, unique",
}
```

Response :

```json 
{
    "data" : {
         "kodeotp" : 065321,//number
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Send OTP Via SMS

Request :
- Method : POST
- Endpoint : `/mobile/v1/auth/otp-sms`
- Header : null
- Body :

```json 
{
    "nohp" : "number",
    "id_device" : "string, unique",
}
```

Response :

```json 
{
    "data" : {
         "data" : {
         "kodeotp" : 065321,//number
    },
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Send Email Verification Mobile App

Request :
- Method : POST
- Endpoint : `/mobile/v1/auth/otp-email`
- Header : null
- Body :

```json 
{
    "email" : "string",
    "id_device" : "string, unique",
}
```

Response :

```json 
{
     "data" : {
         "kodeotp" : 065321,//number
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Laporan

### Laporan TOBK UTBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/tobk-utbk/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
       {
                "kodeTOB": "6789",//String
                "namaTOB": "TOBK SUPER INTENSIF KE-1",//String
                "penilaian": "IRT",//String
                "tanggalAkhir": "2023-04-10 23:59:00",//String
                "tampilSolusi": "1",//String
                "info": [
                    {
                        "kelompok": "0301",//String
                        "namakelompok": "SAINTEK",//String
                        "ptn": "INSTITUT TEKNOLOGI BANDUNG",//String
                        "jurusan": "SEKOLAH TEK. ELEKTRO & INFORMATIKA (STEI)",//String
                        "pg": 689.24000000000001,//doubel
                        "nilai": 452 //int
                    },
                ],//array
                "listNilai": {
                    "TPS - PENGETAHUAN DAN PEMAHAMAN UMUM": "472",//String
                    "Kemampuan Memahami Bacaan dan Menulis": "585",//String
                    "PENALARAN MATEMATIKA": "296",//String
                    "LITERASI DALAM BAHASA INDONESIA": "567",//String
                    "LITERASI DALAM BAHASA INGGRIS": "313",//String
                    "PENGETAHUAN KUANTITATIF": "975",//String
                    "KEMAMPUAN PENALARAN UMUM": "0"//String
                },//object
                "link": "http://epb.ganeshaoperation.com/epb/?v=VG1wak5FOVRPREpPZW1jMVRHcEJNVTFFUlhoTlZFVjRUa1JqZDAxVE5YZGFSMWs5",//String
                "isexists": false //boolean
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan TOBK UTBK Detail

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/tobk-utbk/detail/{kode_tob}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
            "pilihan": [
                {
                    "kelompok": "0301", //String
                    "namakelompok": "SAINTEK", //String
                    "ptn": "INSTITUT TEKNOLOGI BANDUNG", //String
                    "jurusan": "SEKOLAH TEK. ELEKTRO & INFORMATIKA (STEI)", //String
                    "pg": 689.24, //doubel
                    "nilai": 721.95 //doubel
                },
            ],
            "nilai": [
                {
                    "namaKelompokUjian": "KEMAMPUAN PENALARAN UMUM", //String
                    "initial":"KPU", //String
                    "benar": 12, //int
                    "salah": 3, //int
                    "kosong": 0, //int
                    "kodeSoal": "TO-001087", //String
                    "jumlahSoal": 0, //int
                    "nilai": 544, //int
                    "nilaiMax": 0 //int
                }
            ]
        },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan TOBK ANBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/tobk-anbk/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
      "data" : [
       {
                "kodeTOB": "6789",//String
                "namaTOB": "TOBK SUPER INTENSIF KE-1",//String
                "penilaian": "IRT",//String || enum
                "tanggalAkhir": "2023-04-10 23:59:00",//String
                "tampilSolusi": "1",//String
                "info": [
                    {
                        "kelompok": "0301",//String
                        "namakelompok": "SAINTEK",//String
                        "ptn": "INSTITUT TEKNOLOGI BANDUNG",//String
                        "jurusan": "SEKOLAH TEK. ELEKTRO & INFORMATIKA (STEI)",//String
                        "pg": 689.24000000000001,//doubel
                        "nilai": 452 //int
                    },
                ],//array
                "listNilai": {
                    "TPS - PENGETAHUAN DAN PEMAHAMAN UMUM": "472",//String
                    "Kemampuan Memahami Bacaan dan Menulis": "585",//String
                    "PENALARAN MATEMATIKA": "296",//String
                    "LITERASI DALAM BAHASA INDONESIA": "567",//String
                    "LITERASI DALAM BAHASA INGGRIS": "313",//String
                    "PENGETAHUAN KUANTITATIF": "975",//String
                    "KEMAMPUAN PENALARAN UMUM": "0"//String
                },//object
                "link": "http://epb.ganeshaoperation.com/epb/?v=VG1wak5FOVRPREpPZW1jMVRHcEJNVTFFUlhoTlZFVjRUa1JqZDAxVE5YZGFSMWs5",//String
                "isexists": false //boolean
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan TOBK STAN

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/tobk-stan/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
     "data" : [
       {
                "kodeTOB": "6789",//String
                "namaTOB": "TOBK SUPER INTENSIF KE-1",//String
                "penilaian": "IRT",//String || enum
                "tanggalAkhir": "2023-04-10 23:59:00",//String
                "tampilSolusi": "1",//String
                "info": [
                    {
                        "kelompok": "0301",//String
                        "namakelompok": "SAINTEK",//String
                        "ptn": "INSTITUT TEKNOLOGI BANDUNG",//String
                        "jurusan": "SEKOLAH TEK. ELEKTRO & INFORMATIKA (STEI)",//String
                        "pg": 689.24000000000001,//doubel
                        "nilai": 452 //int
                    },
                ],//array
                "listNilai": {
                    "TPS - PENGETAHUAN DAN PEMAHAMAN UMUM": "472",//String
                    "Kemampuan Memahami Bacaan dan Menulis": "585",//String
                    "PENALARAN MATEMATIKA": "296",//String
                    "LITERASI DALAM BAHASA INDONESIA": "567",//String
                    "LITERASI DALAM BAHASA INGGRIS": "313",//String
                    "PENGETAHUAN KUANTITATIF": "975",//String
                    "KEMAMPUAN PENALARAN UMUM": "0"//String
                },//object
                "link": "http://epb.ganeshaoperation.com/epb/?v=VG1wak5FOVRPREpPZW1jMVRHcEJNVTFFUlhoTlZFVjRUa1JqZDAxVE5YZGFSMWs5",//String
                "isexists": false //boolean
            },
    ],
    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan TOBK UjianSekolah

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/tobk-ujian-sekolah/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
      "data" : [
       {
                "kodeTOB": "6789",//String
                "namaTOB": "TOBK SUPER INTENSIF KE-1",//String
                "penilaian": "IRT",//String || enum
                "tanggalAkhir": "2023-04-10 23:59:00",//String
                "tampilSolusi": "1",//String
                "info": [
                    {
                        "kelompok": "0301",//String
                        "namakelompok": "SAINTEK",//String
                        "ptn": "INSTITUT TEKNOLOGI BANDUNG",//String
                        "jurusan": "SEKOLAH TEK. ELEKTRO & INFORMATIKA (STEI)",//String
                        "pg": 689.24000000000001,//doubel
                        "nilai": 452 //int
                    },
                ],//array
                "listNilai": {
                    "TPS - PENGETAHUAN DAN PEMAHAMAN UMUM": "472",//String
                    "Kemampuan Memahami Bacaan dan Menulis": "585",//String
                    "PENALARAN MATEMATIKA": "296",//String
                    "LITERASI DALAM BAHASA INDONESIA": "567",//String
                    "LITERASI DALAM BAHASA INGGRIS": "313",//String
                    "PENGETAHUAN KUANTITATIF": "975",//String
                    "KEMAMPUAN PENALARAN UMUM": "0"//String
                },//object
                "link": "http://epb.ganeshaoperation.com/epb/?v=VG1wak5FOVRPREpPZW1jMVRHcEJNVTFFUlhoTlZFVjRUa1JqZDAxVE5YZGFSMWs5",//String
                "isexists": false //boolean
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan Tes VAK

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/vak/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
        "data": {
            "nis": "050111114701", //String
            "visual": "15", //String
            "auditory": "13", //String
            "kinestetis": "17", //String
            "kecenderungan": "K", //String
            "dominan": "Kinestetik", //String
            "judul1": "KINESTETIK :", //String
            "isi1": "Praktek langsung akan sangat baik untuk memperkuat daya ingat. Gunakan gerakan/sentuhan yang memperkuat daya ingat. Salah satu cara menciptakan gerakan,  tulis ulang pelajaran yang tidak bisa dipraktekkan atau disentuh. Menuliskan ulang  diharapkan dapat sebagai pelengkap gerakan. Lengkapi ruang belajar dengan aksesoris berupa poster/gambar yang menunjukkan adanya gerakan.", //String
            "judul2": null, //String || null
            "isi2": null, //String || null
            "judul3": null, //String || null
            "isi3": null //String || null
        }
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan Hasil GOA

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/goa/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" :{
            "jumRemedial": 1,//int
            "hasil": [
                {
                    "benar": 4,//int
                    "salah": 0,//int
                    "kosong": 0,//int
                    "isLulus": 1,//int
                    "targetLulus": null, //int || null
                    "idKelompokUjian": 21, //int
                    "namaKelompokUjian": "GOA - BAGIAN A" //String
                },
            ],
        },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### list Laporan kuis

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/list/kuis`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
            {
                "cnamamapel": "BAHASA INDONESIA",//String
                "info": [
                    {
                        "cKodeSoal": "KUIS-636"//String
                    },
                    {
                        "cKodeSoal": "KUIS-238" //String
                    },
                    {
                        "cKodeSoal": "KUIS-001163" //String
                    }
                ]
            },
        ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan Hasil Kuis

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/hasil/kuis/{kodekuis}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
            {
                "jenisProduk": "e-Kuis", //String
                "kodePaket": "KUIS-230", //String
                "idBundel": "17487",//String
                "kodeBab": null, //String 
                "idSoal": "342905", //String
                "nomorSoalDatabase": 5, //int
                "nomorSoalSiswa": 5, //int
                "idKelompokUjian": "111", //String
                "namaKelompokUjian": "MATEMATIKA UMUM", //String
                "tipeSoal": "PGB", //String || enum
                "tingkatKesulitan": 1, //int
                "kesempatanMenjawab": null, //int
                "jawabanSiswa": "A", //String
                "kunciJawaban": "B", //String
                "translatorEPB": null, 
                "kunciJawabanEPB": "B", //String
                "jawabanSiswaEPB": "A", //String
                "infoNilai": {"fullcredit": 1, "halfcredit": -1, "zerocredit": 0},
                "nilai": 1.0,//Doubel
                "isRagu": false, //bool
                "sudahDikumpulkan": true, //bool
                "lastUpdate": "2023-08-01 20:23:11" //String
              },
        ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan Presensi Kegiatan Belajar Mengajar (KBM)

Request :
- Method : GET
- Endpoint : "/mobile/v1/laporan/presensi-kbm/{id_user}"
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" :[
        {
                "date": "2023-08-28",
                "listPresences": [
                    {
                        "planId": "10440504", // String
                        "classId": "272153", // String
                        "studentClassId": "272153", // String
                        "className": "11-UMUM-R-N-12", // String
                        "flag": "Sama", // String
                        "date": "2023-08-28", // String
                        "presenceTime": "2023-08-28 18:56:12", // String
                        "teacherId": "2022164089", // String
                        "teacherName": "Noviana Adelita Rahmawan", // String
                        "scheduleStart": "2023-08-28 18:45:00", // String || date
                        "scheduleFinish": "2023-08-28 20:15:00", // String || date
                        "buildingName": "SARIKAYA 148", // String
                        "session": "1", // String
                        "lesson": "MATEMATIKA", // String
                        "activity": "KBM JPMP", // String
                        "isFeedback": false, //bool
                        "feedbackPermission": false //bool
                    },
                ]
            },
        ],
    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
### getPresensi
Request :
- Method : GET
- Endpoint : "/mobile/v1/presensi-kbm/{id_user}"
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" :{
            "jumhadir": "2",
            "jumharus": "3"
        },
    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
## Laporan Aktivitas Belajar Siswa (ABS)
### Laporan Aktivitas daily Belajar Siswa (ABS)

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/abs/daily/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
            {
                "id": "050111114701", // String
                "menu": "Buku Teori", // String
                "detail": "BAHASA INDONESIA, Teks Cerita Sejarah/ Rekon", // String
                "masuk": "2023-09-05 14:04:28",// String || date
                "keluar": null // String || date
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan Aktivitas weekly Belajar Siswa (ABS)

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/abs/weekly/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
            {
                "id": "050111114701", // String
                "menu": "Buku Teori", // String
                "detail": "BAHASA INDONESIA, Teks Cerita Sejarah/ Rekon", // String
                "masuk": "2023-09-05 14:04:28",// String || date
                "keluar": null // String || date
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan Buku Sakti

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/buku-sakti/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
            "detail": {
                "benarlevel1": 42, //int
                "benarlevel2": 33, //int
                "benarlevel3": 94, //int
                "benarlevel4": 40, //int
                "benarlevel5": 5, //int
                "salahlevel1": 22, //int
                "salahlevel2": 12, //int
                "salahlevel3": 30, //int
                "salahlevel4": 12, //int
                "salahlevel5": 0   //int
            },
            "totalScore": 572, //int
            "targetJumlahSoal": 10000, //int
            "totalSoal": 290, //int
            "totalSoalBenar": 214, //int
            "totalSoalSalah": 76, //int
            "rankGedung": 5, //int
            "rankKota": 50, //int
            "rankNasional": 1948 //int
        },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Laporan Progress Hasil Latihan Buku Sakti

Request :
- Method : GET
- Endpoint : `/mobile/v1/laporan/buku-sakti/progress/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
   "data": [
            {
                "cidmapel": "6", //string || int
                "targetharian": "3", //string || int
                "pengerjaanharian": "0", //string || int
                "benarharian": "2", //string || int
                "salahharian": "1", //string || int
                "targetmingguan": "21", //string || int
                "pengerjaanmingguan": "0", //string || int
                "benarmingguan": "0", //string || int
                "salahmingguan": "0", //string || int
                "targetbulanan": "90", //string || int
                "pengerjaanbulanan": "0", //string || int
                "benarbulanan": "0", //string || int
                "salahbulanan": "0", //string || int
                "nama": "Matematika",  //string
                "initial": "MAT" //string
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Leaderboard

### Leaderboard

Request :
- Method : GET
- Endpoint : `/mobile/v1/leaderboard`
- Header : null
Response :

```json 
{
    "data" : [
        {   "pesan": "*Rangking dan skor diupdate pada 12 July 2023 10:00 WIB", //String
             "national": {
                "topfive": [
                   {
                        "id": "050307011501", //String
                        "fullName": "MIRELLA HAYU NOVITASARI", //String
                        "level": "14", //String
                        "sort": "1", //String
                        "rank": "1", //String
                        "total": "114292" //String
                    }, // 5 data teratas
                ],
                "myrank": [
                    {
                        "id": "050906018901",
                        "fullName": "TIRZA KRISTIANITA",
                        "level": "14",
                        "sort": "36162",
                        "rank": "36162",
                        "total": "97"
                    },// data user + 2 diatasnya dan 2 dibawahnya di tingkat nasional
                ],
             },
             "city": {
                "topfive": [
                   {
                        "id": "050307011501", //String
                        "fullName": "MIRELLA HAYU NOVITASARI", //String
                        "level": "14", //String
                        "sort": "1", //String
                        "rank": "1", //String
                        "total": "114292" //String
                    }, // 5 data teratas
                ],
                "myrank": [
                    {
                        "id": "050906018901",
                        "fullName": "TIRZA KRISTIANITA",
                        "level": "14",
                        "sort": "36162",
                        "rank": "36162",
                        "total": "97"
                    },// data user + 2 diatasnya dan 2 dibawahnya di tingkat city
                ],
             },
             "gedung": {
                "topfive": [
                   {
                        "id": "050307011501", //String
                        "fullName": "MIRELLA HAYU NOVITASARI", //String
                        "level": "14", //String
                        "sort": "1", //String
                        "rank": "1", //String
                        "total": "114292" //String
                    }, // 5 data teratas
                ],
                "myrank": [
                    {
                        "id": "050906018901",
                        "fullName": "TIRZA KRISTIANITA",
                        "level": "14",
                        "sort": "36162",
                        "rank": "36162",
                        "total": "97"
                    },// data user + 2 diatasnya dan 2 dibawahnya di tingkat gedung
                ],
             }
        },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


### Leaderboard First Rank

Request :
- Method : GET
- Endpoint : `/mobile/v1/leaderboard/first-rank`
- Header : null
Response :

```json 
{
    "data" : [
            {
                "cNIS": "70511000101", //String
                "ctotal": "2819", //String
                "tipe": "Gedung", //String || enum (national,city,gedung)
                "cnamalengkap": "AZHAD MUHAMMAD SI", //String
                "noRegistrasi": "70511000101", //String
                "score": "2819", //String
                "namaLengkap": "AZHAD MUHAMMAD SI", //String
                "url": "https://firebasestorage.googleapis.com/v0/b/kreasi-f1f7b.appspot.com/o/avatar%2Fb-6.png?alt=media&token=8bfb2b14-2d49-4d7a-9917-a6966c88773a" //String
            }, //top tiap tingkat gedung, kota, nasional
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Perguruan Tinggi

### Universitas

Request :
- Method : GET
- Endpoint : `/mobile/v1/universitas`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
           {
                "idPTN": 91, // int
                "namaPTN": "INSTITUT KESENIAN JAKARTA", //String
                "aliasPTN": "IKJ",  //String
                "jenis": "Negeri"  //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Jurusan

Request :
- Method : GET
- Endpoint : `/mobile/v1/universitas/{id_universitas}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
       {
                "idPTN": 222, // int
                "idJurusan": 222016, // int
                "namaJurusan": "ADMINISTRASI BISNIS", //String
                "kelompok": "SOSHUM", //String
                "rumpun": "TERAPAN 5", //String
                "info": {
                    "peminat": [
                        {
                            "jml": 0, //int
                            "tahun": 2022 //int
                        }
                    ],
                    "tampung": [
                        {
                            "jml": 0, //int
                            "tahun": 2023 //int
                        }
                    ]
                },
                "passgrade": "481.67", //String || doubel
                "lintas": "N", //String || bool 
                "deskripsi": "Deskripsi untuk Jurusan ini masih belum tersedia Sobat", //String 
                "lapker": "Informasi Lapangan Kerja untuk Jurusan ini masih belum tersedia Sobat" //String 
            }, // list semua jurusan di universitas tersebut 
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Jurusan Detail

Request :
- Method : GET
- Endpoint : `/mobile/v1/universitas/jurusan/{id_jurusan}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
     "data": {
            "idPTN": 222, // int
            "namaPTN": "POLITEKNIK NEGERI MEDAN", //String
            "aliasPTN": "POLMED", //String
            "idJurusan": 2222013, //int
            "namaJurusan": "KEUANGAN DAN PERBANKAN SYARIAH", //String
            "kelompok": "SOSHUM", //String
            "rumpun": "SOSIAL 2", //String
            "passgrade": "500.33", //String || doubel
            "lintas": null, //String || bool
            "deskripsi": "mewujudkan sumberdaya insani yang memiliki kemampuan akademis dibidang keuangan dan perbankan syariah, mandiri berfikir dan bertindak sebagai wujud dari iman dan taqwa, serta  bertanggungjawab sosial sesuai profesi kerja. Kemampuan penunjang memiliki kemampuan akademis dibidang keuangan dan perbankan syariah, mandiri berfikir dan bertindak sebagai wujud dari iman dan taqwa, serta  bertanggungjawab sosial sesuai profesi kerja", //String
            "lapker": "Akuntan, Pengusaha, Pegawai Bank Syariah, Internal Auditor, Analis Keuangan, Staf Lembaga Islam, Manajer Investasi, Staf Keuangan Syariah, Akademisi, hli Ekonomi Islam.", //String
            "peminat": [
                {
                    "jml": 100, //int
                    "tahun": 2022 //int
                },
                {
                    "jml": 212, //int
                    "tahun": 2023 //int
                }
            ],
            "tampung": [
                {
                    "jml": 38, //int
                    "tahun": 2022 //int
                },
                {
                    "jml": 39, //int
                    "tahun": 2023 //int
                }
            ]
        },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Pilihan PTN User

Request :
- Method : GET
- Endpoint : `/mobile/v1/ptn-pilihan/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
            "pilihan1": {
                "idPTN": 332, //int
                "namaPTN": "INSTITUT TEKNOLOGI BANDUNG", //String
                "aliasPTN": "ITB",  //String
                "idJurusan": 3321034, //int
                "namaJurusan": "FAK. MATEMATIKA & ILMU PENGET. ALAM (FMIPA)",  //String
                "peminat": "Peminat: 1237",  //String
                "tampung": "Daya Tampung: 142",  //String
                "pilihan": 1, // int (1/2)
                "tanggal": "2023-09-06 11:39:26"  //String
             },
            "pilihan2": {
               "idPTN": 332, //int
                "namaPTN": "INSTITUT TEKNOLOGI BANDUNG", //String
                "aliasPTN": "ITB",  //String
                "idJurusan": 3321034, //int
                "namaJurusan": "FAK. MATEMATIKA & ILMU PENGET. ALAM (FMIPA)",  //String
                "peminat": "Peminat: 1237",  //String
                "tampung": "Daya Tampung: 142",  //String
                "pilihan": 2, // int (1/2)
                "tanggal": "2023-09-06 11:39:26"  //String
            },
           "history": [
                {
                 "idPTN": 332, //int
                "namaPTN": "INSTITUT TEKNOLOGI BANDUNG", //String
                "aliasPTN": "ITB",  //String
                "idJurusan": 3321034, //int
                "namaJurusan": "FAK. MATEMATIKA & ILMU PENGET. ALAM (FMIPA)",  //String
                "peminat": "Peminat: 1237",  //String
                "tampung": "Daya Tampung: 142",  //String
                "pilihan": 1, // int (1/2)
                "tanggal": "2023-09-06 11:39:26"  //String
                },//semua history pilihan siswa
        ]
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Pilihan PTN User

Request :
- Method : GET
- Endpoint : `/mobile/v1/ptn-pilihan/simpan`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
- pharam:
```json
    {
        "noRegistrasi":"040916026101", //String
        "pilihanKe":2, //int
        "idJurusan":2222021 //int
    }
```
Response :
```json 
{

}
```
## GOA & VAK

### List GOA

Request :
- Method : GET
- Endpoint : `/mobile/v1/goa/list`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
      "data": [
            {
                "kodeTOB": "18526", //String
                "idKelompokUjian": "36", //String
                "idJenisProduk": "80", //String
                "idSekolahKelas": "41", //String
                "kodePaket": "RAC-002051", //String
                "c_Deskripsi": "RACING-12SMA-K.MERDEKA-02 SEPTEMBER 2023", //String
                "nomorUrut": "1", //String
                "isBlockingTime": "1", //String
                "tanggalBerlaku": "2023-09-02 10:00:00", //String
                "tanggalKedaluwarsa": "2023-09-02 23:59:00", //String
                "totalWaktu": "61", //String
                "jumlahSoal": "40", //String
                "jenis": "reguler", //String
                "isSelesai": "n", //String || bool
                "isPernahMengerjakan": "n", //String || bool
                "tanggalMulai": "-", //String || date
                "tanggalDeadline": "-", //String || date
                "tanggalMengumpulkan": "-", //String || date
                "merk": "Unknown", //String
                "waktuHabis": "n", //String || bool
                "initial":"mkt", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/mapel_akm.webp", //String
                "namaKelompokUjian":"MATEMATIKA SAINTEK" //String
            }, //semua list goa 
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### List VAK

Request :
- Method : GET
- Endpoint : `/mobile/v1/vak/list`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
     "data": [
            {
                "c_KodeTOB": "18240", // String
                "c_KodePaket": "EMMA-005000", // String
                "c_Deskripsi": "EMMA-12SMA-K.Merdeka-S1-MAT UMUM-PER 04-10 SEPT 23", // String
                "isLulus": null, // bool
                "idJenisProduk": "71", // String || int
                "c_IsBlockingTime": "0", // String || bool
                "idSekolahKelas": "41", // String || int
                "tanggalBerlaku": "2023-09-04 00:00:00", // String || date
                "tanggalKedaluwarsa": "2023-09-19 23:59:00",// String || date
                "totalWaktu": "50", // String || int
                "jumlahSoal": "10", // String || int
                "jenis": "reguler" // String || enum
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal GOA

Request :
- Method : GET
- Endpoint : `/mobile/v1/goa/soal`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
        "data_detail":[
            {
                "c_idsoal": "335213", //String
                "c_soal": "<p class=&quotes;so&quotes;><span lang=&quotes;EN-US&quotes;>Sebuah industri rumah tangga yang baru beroperasi tahun 2012 membeli mesin produksi seharga Rp100.000.000,-. Dengan berjalannya proses produksi, maka harga mesin menurun 1% setiap tahun. Harga mesin pada tahun 2014 adalah</span></p>",  //String
                "c_opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>Rp98.000.000,-</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>Rp98.010.000,-</p>\", \"bobot\": 100}, \"C\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>Rp98.020.000,-</span></p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>Rp98.030.000,-</span></p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>Rp98.050.000,-</span></p>\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //object
                "c_idwacana": "0", //String
                "c_tipesoal": "PGB", //String || enum 
                "c_tingkatkesulitan": "3", //String || int
                "c_nomorsoal": "1", //String || int
                "wacana": "", //String
                "c_namakelompokujian": "MATEMATIKA UMUM", //String
                "c_kodepaket": "RAC-002051", //String
                "c_idbundel": "24606", //String
                "c_idkelompokujian": "111", //String
                "c_idvideo": "0", //String
                "c_NomorSoal": "1" //String
            },
    ],
    "waktu": "100", //String
    },
    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal VAK

Request :
- Method : GET
- Endpoint : `/mobile/v1/vak/soal`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
        "waktu": "180", //string
        "data_detail": [
            {  "wacana": "", //String
                "c_IdSoal": "320407", //String
                "c_NomorSoal": "1", //String
                "c_IdWacana": "0", //String
                "c_IdBundel": "23780", //String
                "c_IdKelompokUjian": "124", //String
                "c_IdVideo": "9829", //String
                "c_Soal": "<p>Mahasiswa baru mencari perguruan tinggi swasta sebagai alternatif perguruan tinggi negeri. Jika kualitas dosen baik dan fasilitas perguruan tinggi swasta memadai, perguruan tinggi swasta tersebut baik. Mahasiswa baru akan memilih perguruan tinggi swasta dengan biaya murah.</p><p><img src=&quotes;{{root_media}}7689ae0111c790acc1b28b7f8287297f.png&quotes;></p><p>Ada berapa argumen yang memperlemah?</p>", //String
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>Tidak ada.</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>Satu pernyataan.</p>\", \"bobot\": 100}, \"C\": {\"text\": \"<p>Dua pernyataan.</p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p>Tiga pernyataan.</p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p>Empat pernyataan.</p>\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //Object
                "c_TipeSoal": "PGB", //String || enum
                "c_TingkatKesulitan": "4", //String
                "c_NamaKelompokUjian": "KEMAMPUAN PENALARAN UMUM", //String
                "c_KodePaket": "EMWA-754" //String
            }
        ]
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
### Hasil Pengerjaan VAK

Request :
- Method : GET
- Endpoint : `/mobile/v1/hasil/vak/{kodepaket}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
           {
                "benar": 1, //int
                "salah": 1, //int
                "kosong": 0, //int
                "namaKelompokUjian": "Kemampuan Memahami Bacaan dan Menulis" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Racing

### List Racing

Request :
- Method : GET
- Endpoint : `/mobile/v1/racing/list`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "kodeTOB": "18526", //String
                "idKelompokUjian": "36", //String
                "idJenisProduk": "80", //String
                "idSekolahKelas": "41", //String
                "kodePaket": "RAC-002051", //String
                "c_Deskripsi": "RACING-12SMA-K.MERDEKA-02 SEPTEMBER 2023", //String
                "nomorUrut": "1", //String
                "isBlockingTime": "1", //String || bool
                "tanggalBerlaku": "2023-09-02 10:00:00", //String || date
                "tanggalKedaluwarsa": "2023-09-02 23:59:00", //String || date
                "totalWaktu": "61", //String
                "jumlahSoal": "40", //String
                "jenis": "reguler", //String || enum
                "isSelesai": "n", //String || bool
                "isPernahMengerjakan": "n", //String || bool
                "tanggalMulai": "-",//String || date
                "tanggalDeadline": "-", //String || date
                "tanggalMengumpulkan": "-", //String || date
                "merk": "Unknown", //String
                "waktuHabis": "n", //String || bool
                "initial":"mkt", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/mapel_akm.webp", //String
                "namaKelompokUjian":"MATEMATIKA SAINTEK" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Racing

Request :
- Method : GET
- Endpoint : `/mobile/v1/racing/soal`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
        "waktu": "60",//String
        "detail_soal":[
            {
                "c_idsoal": "335216", //String
                "c_soal": "<p class=&quotes;so&quotes;><span lang=&quotes;EN-US&quotes;>Suatu bahan radioaktif yang semula berukuran 100 gram mengalami reaksi kimia sehingga ukurannya menyusut 10% dari ukuran sebelum nya setiap 12 jam. Ukuran bahan radioaktif tersebut setelah 2 hari adalah</span></p>", //String || HTML
                "c_opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>56,16 gram.</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>56,61 gram.</p>\", \"bobot\": 0}, \"C\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>61,65 gram.</span></p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p>65,16 gram.</p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>65,61 gram.</span></p>\", \"bobot\": 100}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //object
                "c_idwacana": "0", //String
                "c_tipesoal": "PGB", //String || enum
                "c_tingkatkesulitan": "4", //String
                "c_nomorsoal": "6", //String
                "wacana": "", //String
                "c_namakelompokujian": "MATEMATIKA UMUM", //String
                "c_kodepaket": "RAC-002051", //String
                "c_idbundel": "24606", //String
                "c_idkelompokujian": "111", //String
                "c_idvideo": "0", //String
                "c_NomorSoal": "6" //String
            }, 
        ]
        
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## TOBK


### List TOBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/tryout/list`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
                "c_KodeTOB": "17053", //String
                "c_NamaTOB": "TOBK SEPTEMBER 12 IPA K13R", //String
                "jenisTOB": "UTBK", //String || enum
                "tanggalMulai": "2023-09-04 00:00:00", //String || date
                "tanggalBerakhir": "2023-09-19 23:59:00", //String || date
                "jarakAntarPaket": "5", //String
                "isTOMerdeka": "0", //String || bool
                "isBersyarat": "1", //String || bool
                "jenis": "reguler" //String || enum
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Daftar Kelompok TOBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/tryout/daftar-kelompok-ujian`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
                "kodeTOB": "13680", //String
                "idKelompokUjian": "131", //String
                "idJenisProduk": "25", //String
                "idSekolahKelas": "14", //String
                "kodePaket": "TO-844", //String
                "kode_paket": "TO-844", //String
                "c_Deskripsi": "TOBK UM UGM KE-1 TA 22/23_TPA", //String
                "nomorUrut": "1", //String
                "isBlockingTime": "0", //String
                "totalWaktu": "60", //String
                "jumlahSoal": "60",//String
                "isRandom": "0", //String
                "isSelesai": "n", //String
                "isPernahMengerjakan": "n", //String
                "isOK": "n", //String
                "tanggalMulai": "-", //String
                "tanggalDeadline": "-", //String
                "tanggalMengumpulkan": "-", //String
                "merk": "Unknown", //String
                "cKeterangan": null, //String
                "cPilihanSiswa": null, //String
                "cFlag": null, //String
                "waktuHabis": "n", //String
                "isWajib": "1", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/tps_pemahaman_membaca_dan_menulis.webp" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


### Soal TOBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/tryout/soal`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
       "waktu": "60",//String
        "detail_soal":[
            {
                "c_idsoal": "335216", //String
                "c_soal": "<p class=&quotes;so&quotes;><span lang=&quotes;EN-US&quotes;>Suatu bahan radioaktif yang semula berukuran 100 gram mengalami reaksi kimia sehingga ukurannya menyusut 10% dari ukuran sebelum nya setiap 12 jam. Ukuran bahan radioaktif tersebut setelah 2 hari adalah</span></p>", //String || HTML
                "c_opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>56,16 gram.</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>56,61 gram.</p>\", \"bobot\": 0}, \"C\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>61,65 gram.</span></p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p>65,16 gram.</p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>65,61 gram.</span></p>\", \"bobot\": 100}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //object
                "c_idwacana": "0", //String
                "c_tipesoal": "PGB", //String || enum
                "c_tingkatkesulitan": "4", //String
                "c_nomorsoal": "6", //String
                "wacana": "", //String
                "c_namakelompokujian": "MATEMATIKA UMUM", //String
                "c_kodepaket": "RAC-002051", //String
                "c_idbundel": "24606", //String
                "c_idkelompokujian": "111", //String
                "c_idvideo": "0", //String
                "c_NomorSoal": "6" //String
            }, 
        ],
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


### Kisi - Kisi TOBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/tryout/kisi-kisi`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
         {
                "kelompokUjian": "TPS - PENGETAHUAN DAN PEMAHAMAN UMUM", //String
                "info": [
                    {
                        "namaBab": "Afiksasi", //String
                        "kodeBab": "06.03.01", //String
                        "levelTeori": "SMA", //String
                        "idMapel": "6", //String
                        "initialMapel": "IND" //String
                    }
                ]
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


### Cek Boleh TOBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/tryout/cek-boleh-to`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
             "isLulus": true, //bool
            "sudahMengerjakan": false, //bool
            "jumlahBenar": 1, //int
            "jumlahSalah": 8, //int
            "jumlahKosong": 47, //int
            "jumlahSoal": 56, //int
            "listEmpati": [
                {
                    "c_KodeTOB": "16773", //String
                    "c_KodePaket": "EMWA-613", //String
                    "c_JumlahSoal": 4, //int
                    "c_JumlahBenar": 0, //int
                    "c_JumlahSalah": 0, //int
                    "c_IsBoleh": false //bool
                },
            ]
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


### Get Syarat TOBK

Request :
- Method : GET
- Endpoint : `/mobile/v1/tryout/syarat`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
         {
                "c_KodeTOB": "15737", //String
                "c_NamaTOB": "TOBK UJI COBA TIM BTI 12 IPA", //String
                "jenisTOB": "UTBK", //String
                "tanggalMulai": "2023-07-25 15:22:35", //String
                "tanggalBerakhir": "2023-08-30 23:59:00", //String
                "jarakAntarPaket": "1", //String
                "isTOMerdeka": "0", //String
                "isBersyarat": "1", //String
                "jenis": "reguler" //String
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Buku Sakti

### List Buku Sakti - EMWA

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/emwa`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "c_KodeTOB": "18240", // String
                "c_KodePaket": "EMMA-005000", // String
                "c_Deskripsi": "EMMA-12SMA-K.Merdeka-S1-MAT UMUM-PER 04-10 SEPT 23", // String
                "isLulus": null, // bool
                "idJenisProduk": "71", // String || int
                "c_IsBlockingTime": "0", // String || bool
                "idSekolahKelas": "41", // String || int
                "tanggalBerlaku": "2023-09-04 00:00:00", // String || date
                "tanggalKedaluwarsa": "2023-09-19 23:59:00",// String || date
                "totalWaktu": "50", // String || int
                "jumlahSoal": "10", // String || int
                "jenis": "reguler" // String || enum
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### List Buku Sakti - EMMA

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/emma/{kodePaket}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
        "waktu": "180", //string
        "data_detail": [
            {  "wacana": "", //String
                "c_IdSoal": "320407", //String
                "c_NomorSoal": "1", //String
                "c_IdWacana": "0", //String
                "c_IdBundel": "23780", //String
                "c_IdKelompokUjian": "124", //String
                "c_IdVideo": "9829", //String
                "c_Soal": "<p>Mahasiswa baru mencari perguruan tinggi swasta sebagai alternatif perguruan tinggi negeri. Jika kualitas dosen baik dan fasilitas perguruan tinggi swasta memadai, perguruan tinggi swasta tersebut baik. Mahasiswa baru akan memilih perguruan tinggi swasta dengan biaya murah.</p><p><img src=&quotes;{{root_media}}7689ae0111c790acc1b28b7f8287297f.png&quotes;></p><p>Ada berapa argumen yang memperlemah?</p>", //String
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>Tidak ada.</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>Satu pernyataan.</p>\", \"bobot\": 100}, \"C\": {\"text\": \"<p>Dua pernyataan.</p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p>Tiga pernyataan.</p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p>Empat pernyataan.</p>\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //Object
                "c_TipeSoal": "PGB", //String || enum
                "c_TingkatKesulitan": "4", //String
                "c_NamaKelompokUjian": "KEMAMPUAN PENALARAN UMUM", //String
                "c_KodePaket": "EMWA-754" //String
            }
        ]
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
### Hasil Pengerjaan EMMA

Request :
- Method : GET
- Endpoint : `/mobile/v1/hasil/EMMA/{kodepaket}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
           {
                "benar": 1, //int
                "salah": 1, //int
                "kosong": 0, //int
                "namaKelompokUjian": "Kemampuan Memahami Bacaan dan Menulis" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
### List Buku Sakti - Lateks

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/lateks`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "c_IdBundel": "17374", //String
                "c_KodeTOB": "14256", //String
                "c_KodePaket": "LATEKS-372", //String
                "c_Deskripsi": "12SMA-KM-S1-Fisika-TA. 23/24", //String
                "c_IdKelompokUjian": "32", //String
                "c_NamaKelompokUjian": "FISIKA", //String
                "c_Singkatan": "FIS", //String
                "c_WaktuPengerjaan": "1638", //String
                "c_JumlahSoal": "819", //String
                "c_OpsiUrut": "Bab", //String
                "idSekolahKelas": "41", //String
                "jenis": "reguler", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/tps_pemahaman_membaca_dan_menulis.webp" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### List Buku Sakti - Soal Koding

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/soal-koding`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "c_IdBundel": "17374", //String
                "c_KodeTOB": "14256", //String
                "c_KodePaket": "LATEKS-372", //String
                "c_Deskripsi": "12SMA-KM-S1-Fisika-TA. 23/24", //String
                "c_IdKelompokUjian": "32", //String
                "c_NamaKelompokUjian": "FISIKA", //String
                "c_Singkatan": "FIS", //String
                "c_WaktuPengerjaan": "1638", //String
                "c_JumlahSoal": "819", //String
                "c_OpsiUrut": "Bab", //String
                "idSekolahKelas": "41", //String
                "jenis": "reguler", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/tps_pemahaman_membaca_dan_menulis.webp" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### List Buku Sakti - Pendalaman Materi

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/pendalaman-materi`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
       {
                "c_IdBundel": "17374", //String
                "c_KodeTOB": "14256", //String
                "c_KodePaket": "LATEKS-372", //String
                "c_Deskripsi": "12SMA-KM-S1-Fisika-TA. 23/24", //String
                "c_IdKelompokUjian": "32", //String
                "c_NamaKelompokUjian": "FISIKA", //String
                "c_Singkatan": "FIS", //String
                "c_WaktuPengerjaan": "1638", //String
                "c_JumlahSoal": "819", //String
                "c_OpsiUrut": "Bab", //String
                "idSekolahKelas": "41", //String
                "jenis": "reguler", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/tps_pemahaman_membaca_dan_menulis.webp" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### List Buku Sakti - Soal Referensi

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/soal-referensi`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
       {
                "c_IdBundel": "17374", //String
                "c_KodeTOB": "14256", //String
                "c_KodePaket": "LATEKS-372", //String
                "c_Deskripsi": "12SMA-KM-S1-Fisika-TA. 23/24", //String
                "c_IdKelompokUjian": "32", //String
                "c_NamaKelompokUjian": "FISIKA", //String
                "c_Singkatan": "FIS", //String
                "c_WaktuPengerjaan": "1638", //String
                "c_JumlahSoal": "819", //String
                "c_OpsiUrut": "Bab", //String
                "idSekolahKelas": "41", //String
                "jenis": "reguler", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/tps_pemahaman_membaca_dan_menulis.webp" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### List Buku Sakti - Kuis

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/kuis`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "kodeTOB": "18526", //String
                "idKelompokUjian": "36", //String
                "idJenisProduk": "80", //String
                "idSekolahKelas": "41", //String
                "kodePaket": "RAC-002051", //String
                "c_Deskripsi": "RACING-12SMA-K.MERDEKA-02 SEPTEMBER 2023", //String
                "nomorUrut": "1", //String
                "isBlockingTime": "1", //String || bool
                "tanggalBerlaku": "2023-09-02 10:00:00", //String || date
                "tanggalKedaluwarsa": "2023-09-02 23:59:00", //String || date
                "totalWaktu": "61", //String
                "jumlahSoal": "40", //String
                "jenis": "reguler", //String || enum
                "isSelesai": "n", //String || bool
                "isPernahMengerjakan": "n", //String || bool
                "tanggalMulai": "-",//String || date
                "tanggalDeadline": "-", //String || date
                "tanggalMengumpulkan": "-", //String || date
                "merk": "Unknown", //String
                "waktuHabis": "n", //String || bool
                "initial":"mkt", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/mapel_akm.webp", //String
                "namaKelompokUjian":"MATEMATIKA SAINTEK" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### List Buku Sakti - Paket Intensif

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/list/paket-intensif`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
       {
                "c_IdBundel": "17374", //String
                "c_KodeTOB": "14256", //String
                "c_KodePaket": "LATEKS-372", //String
                "c_Deskripsi": "12SMA-KM-S1-Fisika-TA. 23/24", //String
                "c_IdKelompokUjian": "32", //String
                "c_NamaKelompokUjian": "FISIKA", //String
                "c_Singkatan": "FIS", //String
                "c_WaktuPengerjaan": "1638", //String
                "c_JumlahSoal": "819", //String
                "c_OpsiUrut": "Bab", //String
                "idSekolahKelas": "41", //String
                "jenis": "reguler", //String
                "iconMapel":"https://dltvxpypx9f25.cloudfront.net/mapel/tps_pemahaman_membaca_dan_menulis.webp" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Daftar Bab Buku Sakti - Lateks

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/daftar-bab/lateks`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data":  [
            {
                "babUtama": "PARAGRAF", //String
                "info": [
                    {
                        "c_NamaBab": "Informasi isi teks (tersurat/ tersirat)", //String
                        "c_JumlahSoal": "1", //String
                        "c_KodeBab": "06.01.31", //String
                        "c_IdBundel": "18364" //String
                    },
                ]
            }
        ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Daftar Bab Buku Sakti - Soal Koding

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/daftar-bab/soal-koding`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "babUtama": "PARAGRAF", //String
                "info": [
                    {
                        "c_NamaBab": "Informasi isi teks (tersurat/ tersirat)", //String
                        "c_JumlahSoal": "1", //String
                        "c_KodeBab": "06.01.31", //String
                        "c_IdBundel": "18364" //String
                    },
                ]
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Daftar Bab Buku Sakti - Pendalaman Materi

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/daftar-bab/pendalaman-materi`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "babUtama": "PARAGRAF", //String
                "info": [
                    {
                        "c_NamaBab": "Informasi isi teks (tersurat/ tersirat)", //String
                        "c_JumlahSoal": "1", //String
                        "c_KodeBab": "06.01.31", //String
                        "c_IdBundel": "18364" //String
                    },
                ]
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Daftar Bab Buku Sakti - Soal Referensi

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/daftar-bab/soal-referensi`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
         {
                "babUtama": "PARAGRAF", //String
                "info": [
                    {
                        "c_NamaBab": "Informasi isi teks (tersurat/ tersirat)", //String
                        "c_JumlahSoal": "1", //String
                        "c_KodeBab": "06.01.31", //String
                        "c_IdBundel": "18364" //String
                    },
                ]
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Daftar Bab Buku Sakti - Paket Intensif

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/daftar-bab/paket-intensif`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
         {
                "babUtama": "PARAGRAF", //String
                "info": [
                    {
                        "c_NamaBab": "Informasi isi teks (tersurat/ tersirat)", //String
                        "c_JumlahSoal": "1", //String
                        "c_KodeBab": "06.01.31", //String
                        "c_IdBundel": "18364" //String
                    },
                ]
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - EMWA

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal-emwa/{kodesoal}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data":  [
            {
                "wacana": "", //String
                "c_IdSoal": "320407", //String
                "c_NomorSoal": "1", //String
                "c_IdWacana": "0", //String
                "c_IdBundel": "23780", //String
                "c_IdKelompokUjian": "124", //String
                "c_IdVideo": "9829", //String
                "c_Soal": "<p>Mahasiswa baru mencari perguruan tinggi swasta sebagai alternatif perguruan tinggi negeri. Jika kualitas dosen baik dan fasilitas perguruan tinggi swasta memadai, perguruan tinggi swasta tersebut baik. Mahasiswa baru akan memilih perguruan tinggi swasta dengan biaya murah.</p><p><img src=&quotes;{{root_media}}7689ae0111c790acc1b28b7f8287297f.png&quotes;></p><p>Ada berapa argumen yang memperlemah?</p>", //String || html
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>Tidak ada.</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>Satu pernyataan.</p>\", \"bobot\": 100}, \"C\": {\"text\": \"<p>Dua pernyataan.</p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p>Tiga pernyataan.</p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p>Empat pernyataan.</p>\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //String
                "c_TipeSoal": "PGB", //String || bool
                "c_TingkatKesulitan": "4", //String
                "c_NamaKelompokUjian": "KEMAMPUAN PENALARAN UMUM", //String
                "c_KodePaket": "EMWA-754" //String
            },
        ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - EMMA

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal-emma/{kodesoal}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "wacana": "", //String
                "c_IdSoal": "320407", //String
                "c_NomorSoal": "1", //String
                "c_IdWacana": "0", //String
                "c_IdBundel": "23780", //String
                "c_IdKelompokUjian": "124", //String
                "c_IdVideo": "9829", //String
                "c_Soal": "<p>Mahasiswa baru mencari perguruan tinggi swasta sebagai alternatif perguruan tinggi negeri. Jika kualitas dosen baik dan fasilitas perguruan tinggi swasta memadai, perguruan tinggi swasta tersebut baik. Mahasiswa baru akan memilih perguruan tinggi swasta dengan biaya murah.</p><p><img src=&quotes;{{root_media}}7689ae0111c790acc1b28b7f8287297f.png&quotes;></p><p>Ada berapa argumen yang memperlemah?</p>", //String || html
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>Tidak ada.</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>Satu pernyataan.</p>\", \"bobot\": 100}, \"C\": {\"text\": \"<p>Dua pernyataan.</p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p>Tiga pernyataan.</p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p>Empat pernyataan.</p>\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //String
                "c_TipeSoal": "PGB", //String || bool
                "c_TingkatKesulitan": "4", //String
                "c_NamaKelompokUjian": "KEMAMPUAN PENALARAN UMUM", //String
                "c_KodePaket": "EMWA-754" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - Lateks

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal-lateks/{kodesoal}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
         {
                "c_IdBundel": "18364", //String
                "c_KodeBab": "06.01.37", //String
                "c_IdSoal": "170024", //String
                "c_IdKelompokUjian": "119", //String
                "c_NamaKelompokUjian": "Kemampuan Memahami Bacaan dan Menulis",
                "c_Soal": "<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (1) Bahasa merupakan satu di antara hasil budaya manusia yang sangat tinggi nilainya. (2) Tidak dapat dibayangkan jika dalam seluruh kegiatan manusia tidak menggunakan bahasa. (3) Misalnya, ketika membeli sesuatu di toko, meminta atau memberikan informasi, menyatakan cinta atau memarahi seseorang, manusia memerlukan bahasa. (4) Tidak dapat dibayangkan bagaimana wujud tingkah laku manusia tanpa kehadiran bahasa untuk berinteraksi dengan sesamanya. (5) Bahasa menjadi sangat penting karena melalui bahasa manusia dapat berkembang. (6) Bagi manusia, bahasa menjadi media abstraksi berbagai gejala yang muncul di lingkungannya. (7) Hal tersebut menggambarkan betapa penting peran bahasa dalam kehidupan sosial manusia. (8) Komunikasi akan berjalan dengan lancar apabila bahasa yang digunakan tepat. (9) Artinya, bahasa itu dipergunakan sesuai dengan situasi dan kondisi penutur serta sifat penuturan itu dilaksanakan. (10) Hal <em>itu</em> sangat bergantung pada faktor-faktor penentu dalam tindak bahasa atau tindak komunikasi, yaitu lawan bicara, tujuan pembicaraan, masalah yang dibicarakan, atau situasi pembicaraan. (11) Pengguna bahasa yang sesuai dengan situasi dan kondisi peristiwa tindak bahasa disebut berbahasa secara pragmatik.<br></p><p><br></p><p>Apakah judul yang tepat untuk teks tersebut?<br></p>", //String || Html
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"Pentingnya Penguasaan Bahasa bagi Manusia\", \"bobot\": 0}, \"B\": {\"text\": \"Peran Bahasa dalam Hubungan Sosial\", \"bobot\": 100}, \"C\": {\"text\": \"Pentingnya Kaidah Sosial dalam Berbahasa\", \"bobot\": 0}, \"D\": {\"text\": \"Faktor Penentu dalam Tindak Bahasa\", \"bobot\": 0}, \"E\": {\"text\": \"Media Abstraksi di Berbagai Lingkungan\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //String
                "c_IdWacana": null, //String
                "c_TipeSoal": "PGB", //String || ENUM
                "c_TingkatKesulitan": "3",//String
                "c_NomorSoal": "1", //String
                "c_IdVideo": null, //String
                "wacana": "", //String
                "initial":"MTK" //String
            }
            ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - Soal Koding

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal/soal-koding/{kodesoal}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
        {
                "c_IdBundel": "18364", //String
                "c_KodeBab": "06.01.37", //String
                "c_IdSoal": "170024", //String
                "c_IdKelompokUjian": "119", //String
                "c_NamaKelompokUjian": "Kemampuan Memahami Bacaan dan Menulis",
                "c_Soal": "<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (1) Bahasa merupakan satu di antara hasil budaya manusia yang sangat tinggi nilainya. (2) Tidak dapat dibayangkan jika dalam seluruh kegiatan manusia tidak menggunakan bahasa. (3) Misalnya, ketika membeli sesuatu di toko, meminta atau memberikan informasi, menyatakan cinta atau memarahi seseorang, manusia memerlukan bahasa. (4) Tidak dapat dibayangkan bagaimana wujud tingkah laku manusia tanpa kehadiran bahasa untuk berinteraksi dengan sesamanya. (5) Bahasa menjadi sangat penting karena melalui bahasa manusia dapat berkembang. (6) Bagi manusia, bahasa menjadi media abstraksi berbagai gejala yang muncul di lingkungannya. (7) Hal tersebut menggambarkan betapa penting peran bahasa dalam kehidupan sosial manusia. (8) Komunikasi akan berjalan dengan lancar apabila bahasa yang digunakan tepat. (9) Artinya, bahasa itu dipergunakan sesuai dengan situasi dan kondisi penutur serta sifat penuturan itu dilaksanakan. (10) Hal <em>itu</em> sangat bergantung pada faktor-faktor penentu dalam tindak bahasa atau tindak komunikasi, yaitu lawan bicara, tujuan pembicaraan, masalah yang dibicarakan, atau situasi pembicaraan. (11) Pengguna bahasa yang sesuai dengan situasi dan kondisi peristiwa tindak bahasa disebut berbahasa secara pragmatik.<br></p><p><br></p><p>Apakah judul yang tepat untuk teks tersebut?<br></p>", //String || Html
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"Pentingnya Penguasaan Bahasa bagi Manusia\", \"bobot\": 0}, \"B\": {\"text\": \"Peran Bahasa dalam Hubungan Sosial\", \"bobot\": 100}, \"C\": {\"text\": \"Pentingnya Kaidah Sosial dalam Berbahasa\", \"bobot\": 0}, \"D\": {\"text\": \"Faktor Penentu dalam Tindak Bahasa\", \"bobot\": 0}, \"E\": {\"text\": \"Media Abstraksi di Berbagai Lingkungan\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //String
                "c_IdWacana": null, //String
                "c_TipeSoal": "PGB", //String || ENUM
                "c_TingkatKesulitan": "3",//String
                "c_NomorSoal": "1", //String
                "c_IdVideo": null, //String
                "wacana": "", //String
                "initial":"MTK" //String
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - Pendalaman Materi

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal/pendalaman-materi`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
        {
                "c_IdBundel": "18364", //String
                "c_KodeBab": "06.01.37", //String
                "c_IdSoal": "170024", //String
                "c_IdKelompokUjian": "119", //String
                "c_NamaKelompokUjian": "Kemampuan Memahami Bacaan dan Menulis",
                "c_Soal": "<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (1) Bahasa merupakan satu di antara hasil budaya manusia yang sangat tinggi nilainya. (2) Tidak dapat dibayangkan jika dalam seluruh kegiatan manusia tidak menggunakan bahasa. (3) Misalnya, ketika membeli sesuatu di toko, meminta atau memberikan informasi, menyatakan cinta atau memarahi seseorang, manusia memerlukan bahasa. (4) Tidak dapat dibayangkan bagaimana wujud tingkah laku manusia tanpa kehadiran bahasa untuk berinteraksi dengan sesamanya. (5) Bahasa menjadi sangat penting karena melalui bahasa manusia dapat berkembang. (6) Bagi manusia, bahasa menjadi media abstraksi berbagai gejala yang muncul di lingkungannya. (7) Hal tersebut menggambarkan betapa penting peran bahasa dalam kehidupan sosial manusia. (8) Komunikasi akan berjalan dengan lancar apabila bahasa yang digunakan tepat. (9) Artinya, bahasa itu dipergunakan sesuai dengan situasi dan kondisi penutur serta sifat penuturan itu dilaksanakan. (10) Hal <em>itu</em> sangat bergantung pada faktor-faktor penentu dalam tindak bahasa atau tindak komunikasi, yaitu lawan bicara, tujuan pembicaraan, masalah yang dibicarakan, atau situasi pembicaraan. (11) Pengguna bahasa yang sesuai dengan situasi dan kondisi peristiwa tindak bahasa disebut berbahasa secara pragmatik.<br></p><p><br></p><p>Apakah judul yang tepat untuk teks tersebut?<br></p>", //String || Html
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"Pentingnya Penguasaan Bahasa bagi Manusia\", \"bobot\": 0}, \"B\": {\"text\": \"Peran Bahasa dalam Hubungan Sosial\", \"bobot\": 100}, \"C\": {\"text\": \"Pentingnya Kaidah Sosial dalam Berbahasa\", \"bobot\": 0}, \"D\": {\"text\": \"Faktor Penentu dalam Tindak Bahasa\", \"bobot\": 0}, \"E\": {\"text\": \"Media Abstraksi di Berbagai Lingkungan\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //String
                "c_IdWacana": null, //String
                "c_TipeSoal": "PGB", //String || ENUM
                "c_TingkatKesulitan": "3",//String
                "c_NomorSoal": "1", //String
                "c_IdVideo": null, //String
                "wacana": "", //String
                "initial":"MTK" //String
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - Soal Referensi

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal/soal-referensi/{kodesoal}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
        {
                "c_IdBundel": "18364", //String
                "c_KodeBab": "06.01.37", //String
                "c_IdSoal": "170024", //String
                "c_IdKelompokUjian": "119", //String
                "c_NamaKelompokUjian": "Kemampuan Memahami Bacaan dan Menulis",
                "c_Soal": "<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (1) Bahasa merupakan satu di antara hasil budaya manusia yang sangat tinggi nilainya. (2) Tidak dapat dibayangkan jika dalam seluruh kegiatan manusia tidak menggunakan bahasa. (3) Misalnya, ketika membeli sesuatu di toko, meminta atau memberikan informasi, menyatakan cinta atau memarahi seseorang, manusia memerlukan bahasa. (4) Tidak dapat dibayangkan bagaimana wujud tingkah laku manusia tanpa kehadiran bahasa untuk berinteraksi dengan sesamanya. (5) Bahasa menjadi sangat penting karena melalui bahasa manusia dapat berkembang. (6) Bagi manusia, bahasa menjadi media abstraksi berbagai gejala yang muncul di lingkungannya. (7) Hal tersebut menggambarkan betapa penting peran bahasa dalam kehidupan sosial manusia. (8) Komunikasi akan berjalan dengan lancar apabila bahasa yang digunakan tepat. (9) Artinya, bahasa itu dipergunakan sesuai dengan situasi dan kondisi penutur serta sifat penuturan itu dilaksanakan. (10) Hal <em>itu</em> sangat bergantung pada faktor-faktor penentu dalam tindak bahasa atau tindak komunikasi, yaitu lawan bicara, tujuan pembicaraan, masalah yang dibicarakan, atau situasi pembicaraan. (11) Pengguna bahasa yang sesuai dengan situasi dan kondisi peristiwa tindak bahasa disebut berbahasa secara pragmatik.<br></p><p><br></p><p>Apakah judul yang tepat untuk teks tersebut?<br></p>", //String || Html
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"Pentingnya Penguasaan Bahasa bagi Manusia\", \"bobot\": 0}, \"B\": {\"text\": \"Peran Bahasa dalam Hubungan Sosial\", \"bobot\": 100}, \"C\": {\"text\": \"Pentingnya Kaidah Sosial dalam Berbahasa\", \"bobot\": 0}, \"D\": {\"text\": \"Faktor Penentu dalam Tindak Bahasa\", \"bobot\": 0}, \"E\": {\"text\": \"Media Abstraksi di Berbagai Lingkungan\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //String
                "c_IdWacana": null, //String
                "c_TipeSoal": "PGB", //String || ENUM
                "c_TingkatKesulitan": "3",//String
                "c_NomorSoal": "1", //String
                "c_IdVideo": null, //String
                "wacana": "", //String
                "initial":"MTK" //String
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - Kuis

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal-kuis/{kodesoal}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
         {
                "c_idsoal": "335213", //String
                "c_soal": "<p class=&quotes;so&quotes;><span lang=&quotes;EN-US&quotes;>Sebuah industri rumah tangga yang baru beroperasi tahun 2012 membeli mesin produksi seharga Rp100.000.000,-. Dengan berjalannya proses produksi, maka harga mesin menurun 1% setiap tahun. Harga mesin pada tahun 2014 adalah</span></p>",  //String
                "c_opsi": "{\"opsi\": {\"A\": {\"text\": \"<p>Rp98.000.000,-</p>\", \"bobot\": 0}, \"B\": {\"text\": \"<p>Rp98.010.000,-</p>\", \"bobot\": 100}, \"C\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>Rp98.020.000,-</span></p>\", \"bobot\": 0}, \"D\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>Rp98.030.000,-</span></p>\", \"bobot\": 0}, \"E\": {\"text\": \"<p class=&quotes;2&quotes;><span lang=&quotes;EN-US&quotes;>Rp98.050.000,-</span></p>\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //object
                "c_idwacana": "0", //String
                "c_tipesoal": "PGB", //String || enum 
                "c_tingkatkesulitan": "3", //String || int
                "c_nomorsoal": "1", //String || int
                "wacana": "", //String
                "c_namakelompokujian": "MATEMATIKA UMUM", //String
                "c_kodepaket": "RAC-002051", //String
                "c_idbundel": "24606", //String
                "c_idkelompokujian": "111", //String
                "c_idvideo": "0", //String
                "c_NomorSoal": "1" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Soal Buku Sakti - Paket Intensif

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal/paket-intensif`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
         {
                "c_IdBundel": "18364", //String
                "c_KodeBab": "06.01.37", //String
                "c_IdSoal": "170024", //String
                "c_IdKelompokUjian": "119", //String
                "c_NamaKelompokUjian": "Kemampuan Memahami Bacaan dan Menulis",
                "c_Soal": "<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (1) Bahasa merupakan satu di antara hasil budaya manusia yang sangat tinggi nilainya. (2) Tidak dapat dibayangkan jika dalam seluruh kegiatan manusia tidak menggunakan bahasa. (3) Misalnya, ketika membeli sesuatu di toko, meminta atau memberikan informasi, menyatakan cinta atau memarahi seseorang, manusia memerlukan bahasa. (4) Tidak dapat dibayangkan bagaimana wujud tingkah laku manusia tanpa kehadiran bahasa untuk berinteraksi dengan sesamanya. (5) Bahasa menjadi sangat penting karena melalui bahasa manusia dapat berkembang. (6) Bagi manusia, bahasa menjadi media abstraksi berbagai gejala yang muncul di lingkungannya. (7) Hal tersebut menggambarkan betapa penting peran bahasa dalam kehidupan sosial manusia. (8) Komunikasi akan berjalan dengan lancar apabila bahasa yang digunakan tepat. (9) Artinya, bahasa itu dipergunakan sesuai dengan situasi dan kondisi penutur serta sifat penuturan itu dilaksanakan. (10) Hal <em>itu</em> sangat bergantung pada faktor-faktor penentu dalam tindak bahasa atau tindak komunikasi, yaitu lawan bicara, tujuan pembicaraan, masalah yang dibicarakan, atau situasi pembicaraan. (11) Pengguna bahasa yang sesuai dengan situasi dan kondisi peristiwa tindak bahasa disebut berbahasa secara pragmatik.<br></p><p><br></p><p>Apakah judul yang tepat untuk teks tersebut?<br></p>", //String || Html
                "c_Opsi": "{\"opsi\": {\"A\": {\"text\": \"Pentingnya Penguasaan Bahasa bagi Manusia\", \"bobot\": 0}, \"B\": {\"text\": \"Peran Bahasa dalam Hubungan Sosial\", \"bobot\": 100}, \"C\": {\"text\": \"Pentingnya Kaidah Sosial dalam Berbahasa\", \"bobot\": 0}, \"D\": {\"text\": \"Faktor Penentu dalam Tindak Bahasa\", \"bobot\": 0}, \"E\": {\"text\": \"Media Abstraksi di Berbagai Lingkungan\", \"bobot\": 0}}, \"nilai\": {\"fullcredit\": 1, \"halfcredit\": -1, \"zerocredit\": 0}}", //String
                "c_IdWacana": null, //String
                "c_TipeSoal": "PGB", //String || ENUM
                "c_TingkatKesulitan": "3",//String
                "c_NomorSoal": "1", //String
                "c_IdVideo": null, //String
                "wacana": "", //String
                "initial":"MTK" //String
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```



## Simulasi

### Get Simulasi Nilai

Request :
- Method : GET
- Endpoint : `/mobile/v1/simulasi-nilai/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "kodeTob": "819", //String
                "tob": "TOBK 13 IPA_UAT JAN_17940", //String
                "isSelected": false, //bool
                "isFix": false, //bool
                "detailNilai": {
                    "TPS - PENGETAHUAN DAN PEMAHAMAN UMUM": "800", //String
                    "Kemampuan Memahami Bacaan dan Menulis": "850", //String
                    "PENALARAN MATEMATIKA": "700", //String
                    "LITERASI DALAM BAHASA INDONESIA": "100", //String
                    "LITERASI DALAM BAHASA INGGRIS": "850", //String
                    "PENGETAHUAN KUANTITATIF": "700", //String
                    "KPU_PENALARAN DEDUKTIF": "635", //String
                    "KPU_PENALARAN INDUKTIF": "650", //String
                    "KPU_PENALARAN KUANTITATIF": "820" //String
                }
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Get Simulasi Pilihan

Request :
- Method : GET
- Endpoint : `/mobile/v1/simulasi-pilihan/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
         {
                "prioritas": "1", //String
                "status": "1", //String
                "ptn": "INSTITUT TEKNOLOGI KALIMANTAN", //String
                "jurusanId": "5421124", //String
                "jurusan": "INFORMATIKA", //String
                "pg": "552.99", //String
                "peminat": {
                    "jml": 292, //int
                    "tahun": 2021 //int
                },
                "tampung": {
                    "jml": 60, //int
                    "tahun": 2022 //int
                }
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Get Simulasi Hasil

Request :
- Method : GET
- Endpoint : `/mobile/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "prioritas": "1", //String
                "ptn": "Belum ada data",//String
                "jurusanId": null, //String
                "jurusan": "Belum ada data", //String
                "rumpun": null, //String
                "pg": "0", //String
                "peminat": {
                    "jml": 0, //int
                    "tahun": 2021 //int
                },
                "tampung": {
                    "jml": 0, //int
                    "tahun": 2022 //int
                },
                "total": "0", //String
                "saran": null // //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Bookmark

### My Bookmark 

Request :
- Method : GET
- Endpoint : `/mobile/v1/bookmark/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                    "iconMapel": "https://firebasestorage.googleapis.com/v0/b/kreasi-f1f7b.appspot.com/o/icon%2Fmapel%2Fmapel_indo.webp?alt=media&token=c2641f9f-b8f0-42c9-90e7-488a759aaf78", //String
                    "listBookmark": [
                        {
                            "idSoal": "278136", //String
                            "isPaket": false, //bool
                            "kodeBab": "06.02.05", //String
                            "kodeTOB": "574", //String
                            "namaBab": "Tanda Baca", //String
                            "idBundel": "2015", //String
                            "isSimpan": true, //bool
                            "kodePaket": "LATEKS-118", //String
                            "nomorSoal": 37, //int
                            "lastUpdate": "2023-02-16 09:07:54", //String || date
                            "idJenisProduk": 76, //int
                            "nomorSoalSiswa": 1, //int
                            "namaJenisProduk": "e-Latihan Extra", //String
                            "tanggalKedaluwarsa": null //String || date
                        },
                       
                    ],
                    "idKelompokUjian": "109", //String
                    "namaKelompokUjian": "LITERASI DALAM BAHASA INDONESIA", //String
                    "initial":"PK" //String
                },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Pembayaran

### Get Pembayaran

Request :
- Method : GET
- Endpoint : `/mobile/v1/Payment/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": 
       {
            "id": "070917008001", //String
            "total": "7498000", //String
            "current": "7498000", //String
            "remainin": "0", //String
            "status": "Lunas", //String
            "message": "Jika tidak sesuai silahkan hubungi 0853 5199 1159 (WA)" //String
        },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


### Get Pembayaran Detail

Request :
- Method : GET
- Endpoint : `/mobile/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
                "c_idpembelian": "1793357", //String
                "total": "7498000", //String
                "current": "7498000", //String
                "remaining": "0", //String
                "status": "LUNAS", //String
                "c_jatuhtempo": null //String
            }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Berita

### Get Daily Berita

Request :
- Method : GET
- Endpoint : `/mobile/v1/news/daily`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
         {
                    "id": "489", //String
                    "title": "", //String
                    "description": "<p><span style=\"font-size:11pt\"><span style=\"font-family:&quot;Calibri&quot;,sans-serif\"><strong>PENTING !!!</strong></span></span><br type=\"_moz\"></p><p><span style=\"font-size:11pt\"><span style=\"font-family:&quot;Calibri&quot;,sans-serif\">Bagi siswa GO yang belum mengerjakan soal EMPATI WAJIB di GO Kreasi agar segera kerjakan karena EMPATI WAJIB adalah syarat siswa untuk mengikuti TOBK September dengan minimal benar 50%. Ayo segera kerjakan agar adik paham soal-soal yang akan keluar pada TOBK September sekaligus sebagai tiket adik bisa ikut TOBK. Sukses buat Adik-adik</span></span><br type=\"_moz\"></p>", //String || HTML
                    "image": "http://images.ganeshaoperation.com/berita/e60a454996821fe57f86b572a78d6d27.png", //String
                    "date": "28 August 2023  00:00", //String
                    "url": "", //String
                    "jmlhviewer": "7", //String
                    "summary": "PENTING !!!Bagi siswa GO yang belum mengerjakan soal EMPATI WAJIB di GO Kreasi agar segera kerjakan karena EMPATI WAJIB adalah syarat siswa untuk mengikuti TOBK September dengan minimal benar 50%. Ayo segera kerjakan agar adik paham soal-soal yang akan keluar pada TOBK September sekaligus sebagai tiket adik bisa ikut TOBK. Sukses buat Adik-adik" //String
                }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Get List Berita

Request :
- Method : GET
- Endpoint : `/mobile/v1/news`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
         {
      "id": "490", //String
      "title": "Jangan Lupa Kerjain TOBK!", //String
      "description":
          "<p style=\"margin-left:24px\"><span style=\"font-size:11pt\"><span style=\"font-family:Calibri,sans-serif\">Selain rutin mengerjakan soal-soal di GO Kreasi, aku harus apa lagi ya biar bisa menjadi juara di sekolah? Jawabannya adalah rajin mengerjakan TOBK!</span></span></p><p style=\"margin-left:24px\"><span style=\"font-size:11pt\"><span style=\"font-family:Calibri,sans-serif\"><em>Try Out</em> Berbasis Komputer atau TOBK adalah salah satu fitur unggulan yang dimiliki oleh GO Kreasi. Perbedaan TOBK GO Kreasi dengan <em>Try Out</em> yang lain adalah adanya sistem <em>blocking time</em> dan penilaian <em>Item Response Theory</em> (IRT), yang mana kedua sistem tersebut digunakan pada UTBK-SNBT sesungguhnya. Engga hanya 12 SMA dan <em>Gap Year, </em>fasilitas TOBK ini juga ada&nbsp;untuk kamu dari kelas 3 SD lho!</span></span><br></p><p style=\"margin-left:24px\"><span style=\"font-size:11pt\"><span style=\"font-family:Calibri,sans-serif\">TOBK di GO Kreasi diadakan sekali dalam sebulan biar kamu bisa me-<em>review</em> kemampuanmu dalam memahami materi. Khusus untuk kelas 12 dan <em>Gap Year, </em>kamu akan&nbsp;TOBK seminggu sekali saat akan mendekati UTBK-SNBT, agar kamu semakin terlatih mengerjakan soal-soal sehingga siap memenangkan pertempuran di UTBK-SNBT.</span></span></p><p style=\"margin-left:24px\"><span style=\"font-size:11pt\"><span style=\"font-family:Calibri,sans-serif\">Keunggulan lain dari TOBK GO Kreasi ini adalah hasilnya akan dianalisis perbutir soal, <em>which is</em> kamu bisa menganalisis kemampuanmu dalam mengerjakan soal, <em>and</em> <em>we called it</em> Evaluasi Prestasi Belajar (EPB). Di EPB, akan ketahuan nih kamu kurang memahami soal yang mana dan materi apa, sehingga kamu bisa mempelajarinya lagi atau bisa menanyakan langsung materi yang kurang kamu pahami ke pengajar GO melalui <em>Tutorial Service Time</em> (TST). <em>So</em>, mulai sekarang jangan <em>skip</em> TOBK ya..!</span></span></p>", //String || HTML
      "image":
          "http://images.ganeshaoperation.com/berita/2ba6ccde5623b2b1128d8360c635f89d.png", //String
      "date": "01 September 2023  00:00", //String
      "url": "", //String
      "jmlhviewer": "684", //String
      "summary":
          "Selain rutin mengerjakan soal-soal di GO Kreasi, aku harus apa lagi ya biar bisa menjadi juara di sekolah? Jawabannya adalah rajin mengerjakan TOBK!Try Out Berbasis Komputer atau TOBK adalah salah satu fitur unggulan yang dimiliki oleh GO Kreasi. Perbedaan TOBK GO Kreasi dengan Try Out yang lain adalah adanya sistem blocking time dan penilaian Item Response Theory (IRT), yang mana kedua sistem tersebut digunakan pada UTBK-SNBT sesungguhnya. Engga hanya 12 SMA dan Gap Year, fasilitas TOBK ini juga ada&nbsp;untuk kamu dari kelas 3 SD lho!TOBK di GO Kreasi diadakan sekali dalam sebulan biar kamu bisa me-review kemampuanmu dalam memahami materi. Khusus untuk kelas 12 dan Gap Year, kamu akan&nbsp;TOBK seminggu sekali saat akan mendekati UTBK-SNBT, agar kamu semakin terlatih mengerjakan soal-soal sehingga siap memenangkan pertempuran di UTBK-SNBT.Keunggulan lain dari TOBK GO Kreasi ini adalah hasilnya akan dianalisis perbutir soal, which is kamu bisa menganalisis kemampuanmu dalam mengerjakan soal, and we called it Evaluasi Prestasi Belajar (EPB). Di EPB, akan ketahuan nih kamu kurang memahami soal yang mana dan materi apa, sehingga kamu bisa mempelajarinya lagi atau bisa menanyakan langsung materi yang kurang kamu pahami ke pengajar GO melalui Tutorial Service Time (TST). So, mulai sekarang jangan skip TOBK ya..!" //String
    },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```

## Buku
### Get List Buku Teori

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku/Teori`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
       {
                "iconMapel":"https://firebasestorage.googleapis.com/v0/b/kreasi-f1f7b.appspot.com/o/icon%2Fmapel%2Fmapel_indo.webp?alt=media&token=c2641f9f-b8f0-42c9-90e7-488a759aaf78", //String
                "c_IdKelompokUjian": "40", //String
                "c_NamaKelompokUjian": "BAHASA INDONESIA", //String
                "c_Singkatan": "IND", //String
                "c_KodeBuku": "2814", //String
                "c_NamaBuku": "Ebook Teori B.Indonesia 12 IPA TA.23/24 (Teaser)", //String
                "c_Semester": "2", //String
                "kelengkapan": "Lengkap", //String
                "idSekolahKelas": "14", //String
                "levelTeori": "SMA", //String
                "jenis": "teaser" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```

### Get List Bab Buku Teori

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku/Teori/{kodebuku}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
      {
                "babUtama": "EJAAN", //String
                "info": [
                    {
                        "c_NamaBab": "Penulisan Huruf", //String
                        "c_KodeBab": "06.02.01", //String
                        "c_IdTeoriBab": "2324" //String
                    }
                ]
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```

### Get Buku Teori

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku/Teori/{kodebuku}/{kodebab}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
            "c_idteoribab": "552", //String
            "c_Uraian": "<p style=&quotes;text-align: justify;&quotes;>Pidato merupakan kegiatan berbicara di depan umum mengenai suatu hal untuk menyampaikan maksud dan pendapat. Sementara itu, pidato persuasif merupakan kegiatan berbicara di depan umum untuk menyampaikan informasi yang berisi ajakan kepada masyarakat untuk melakukan sesuatu. Pidato persuasif bersifat mengimbau atau mengajak masyarakat untuk berbuat hal yang positif bagi kehidupannya. Pidato persuasif pun sebagai salah satu cara menggerakkan masyarakat untuk berbuat lebih baik dan lebih kreatif sehingga tidak jarang pada setiap acara-acara tertentu pidato persuasif dirasa cukup efektif untuk menginspirasi khalayak.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Pidato persuasif disampaikan secara jelas dan logis. Persuasif mula-mula memaparkan gagasan. Namun, gagasan tersebut tidak hanya gagasan semata, tetapi juga disertai alasan, bukti, atau contoh yang relevan dengan topik yang disampaikan untuk meyakinkan khalayak. Seluruh argumen tersebut diikuti dengan ajakan, bujukan, rayuan, imbauan, atau saran. Upaya persuasif akan berhasil dengan baik bila pesan yang disampaikan memiliki akibat sesuai dengan yang diharapkan.</p><p>Pidato persuasif merupakan bagian dari eksposisi. Dalam pengembangannya, ada tiga tipe eksposisi. Ketiga tipe tersebut sebagai berikut.</p><ol><li>Eksposisi yang dapat mengubah sikap orang atau mengubah pandangan orang tentang suatu hal. Tulisan yang persuasif ini dapat kita temui pada editorial surat kabar; pidato politik atau kampanye; media cetak; teks informasi dalam buku; surat kepada editor; pidato; ceramah; mempertahankan hak hukum; khotbah; dan sebagainya.</li><li>Eksposisi yang dapat dimanfaatkan untuk mempromosikan dan menjual barang, jasa, dan aktivitas. Misalnya penggunaan bahasa persuasif pada iklan dan poster, slogan yang memikat. Misalnya, “Sepuluh langkah memiliki tubuh indah”.</li><li>Eksposisi yang dapat digunajan untuk membela suatu kasus. Misalnya, “Selamatkan Terumbu Karang. Sekarang!”</li></ol><p style=&quotes;text-align: justify;&quotes;>Eksposisi persuasif memiliki satu sudut pandang yang didukung oleh argumen logis dan bukti.</p><p style=&quotes;text-align: justify;&quotes;><strong>A.&nbsp; Tujuan Pidato Persuasif<br></strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Tujuan pidato persuasif adalah untuk meyakinkan pendengar atau audiens untuk melakukan sesuatu, misalnya pidato kampanye dan pidato keagamaan. Selain itu, tujuan dari pidato persuasif lainnya, yakni pembentukan, penguatan, dan pengubahan tanggapan. Ketiga tujuan tersebut dirincikan pada penjelasan berikut.</p><p><strong>1.&nbsp; Pembentukan Tanggapan<br></strong>Satu di antara tujuan pidato persuasif adalah membentuk cara khalayak dalam memberikan tanggapan. Nantinya, pembicara akan menghubungkan gagasan yang dimilikinya dengan nilai-nilai yang melekat atau berkembang di masyarakat. Dari hal tersebut, proses pertalian gagasan dan nilai mampu menghasilkan suatu argumen yang diharapkan mampu meberikan perubahan perilaku kepada khalayak yang menjadi sasaran.</p><p style=&quotes;text-align: justify;&quotes;><strong>2.&nbsp; Penguatan Tanggapan<br></strong>Penguatan tanggapan diharapkan mampu memberikan kesinambungan perilaku saat ini terhadap topik, gagasan, atau isu yang sedang berkembang. Penguatan tanggapan akan dikaitkan dengan nilai-nilai dan sikap yang sudah tertanap dalam diri khalayak. Nilai-nilai tersebut bercirikan kesenangan, kekuatan, dan kepentingan.</p><p style=&quotes;text-align: justify;&quotes;><strong>3.&nbsp; Pengubahan Tanggapan<br></strong>Terakhir, pidato persuasif bertujuan untuk pengubahan tanggapan seseorang atau sekelompok khalayak. Dari hal itulah, seseorang, sekolompok, atau khalayak mampu mengubah perilaku yang dimiliki pada masing-masing pribadi menjadi lebih baik lagi berdasarkan konsep atau gagasan yang sudah mereka pahami secara mandiri dan diperkuat dengan argumen dari pembicara. Artinya, pembicara dalam pidato persuasif akan berupaya untuk mengubah tanggapan atau bahkan mengentikan beberapa perilaku kurang baik yang dimiliki seseorang, sekelompok, atau khalayak. Sebagai contoh, perilaku <em>merokok </em>dan <em>buang sampah sembarangan.</em></p><p><strong>B.&nbsp; Cara-Cara Memersuasi<br></strong><em>&nbsp; &nbsp; &nbsp; </em>Untuk memberikan pernyataan persuasi yang mampu memberikan efek yang positif kepada pembaca atau pendengar, seseorang yang akan memberikan pidato persuasi hendaknya memperhatikan tiga aspek pendekatan dalam cara memersuasi. Ketiga aspek tersebut dapat dilihat pada bagan cara memersuasi berikut ini.</p><p style=&quotes;text-align: center;&quotes;><em><img src=&quotes;{{root_media}}d637beb3498063880980680862f21366.png&quotes;></em></p><p style=&quotes;line-height: 1; text-align: justify;&quotes;><strong>1.&nbsp; Etika<br></strong>Pendekatan etika yang berarti menyentuh audiensi lewat nilai-nilai moral dan kebenaran yang harus ditegakkan.<br>Contoh:<br>&quotes;Daur ulang adalah hal benar yang kita lakukan. Memubazirkan sumber daya kita yang terbatas sama dengan mencuri hak anak cucu kita di masa depan, ini tidak bermoral.&quotes;</p><p style=&quotes;line-height: 1; text-align: justify;&quotes;><strong>2.&nbsp; Emosi<br></strong>Sentuh perasaan audiensi dengan cara membakar semangatnya atau justru membuat pendengar merasa terharu akan suatu kenyataan.<br>Contoh:<br>&quotes;Coba pikirkan jutaan hewan yang kehilangan rumahnya setiap hari akibat pohon yang ditebang. Jika daur ulang berkelanjutan, kita dapat menyelamatkan banyak hutan yang indah.&quotes;</p><p style=&quotes;line-height: 1; text-align: justify;&quotes;><strong>3. Logika<br></strong>Pendekatan Logika berarti memanfaatkan logika untuk memberikan efek setuju karena argumen masuk akal dan dapat dibuktikan secara ilmiah.<br>Contoh:<br><em>&quotes;Kita paham bahwa cadangan sumber daya alami kita terbatas. Kita dapat memperpanjang cadangan kita dengan daur ulang.&quotes;<br></em></p><p style=&quotes;line-height: 1; text-align: justify;&quotes;><strong>C.&nbsp; Struktur Teks Pidato Persuasif<br></strong>Karena teks pidato persuasif termasuk dalam pengembangan eksposisi, penyusunan teks pidato persuasif tersebut dimulai dari bagian pendahuluan yang berisi pernyataan pendapat dari sudut pendang penulis kemudian diikuti dengan argumen dan diakhiri dengan penguatan pernyataan posisi untuk menyimpulkan atau memperkuat sudut pandang penulis.</p><p style=&quotes;text-align: justify;&quotes;><img src=&quotes;{{root_media}}529042312e12db2ea7a8a02113cd48cb.png&quotes;></p><p style=&quotes;text-align: justify;&quotes;>1. <em> </em><strong>Pernyataan Posisi<br></strong>Pernyataan posisi merupakan bagian awal yang disebut juga pendahuluan dalam pidato persuasif. Bagian ini berisi pendapat penulis mengenai suatu topik, isu, atau permasalahan yang akan dibahas.</p><p style=&quotes;text-align: justify;&quotes;><strong>2.&nbsp; Argumen<br></strong>Argumen merupakan pendapat (opini) yang disertai dengan data, fakta, bukti, atau contoh yang relevan mengenai suatu topik, isu, atau permasalahan yang dibahas. Argumen dikembangkan secara logis dan sistematis. Dengan begitu, argumen yang disampaikan diharapkan efektif memberikan dan menumbuhkan keyakinan kepada pembaca, pendengar, atau khalayak.</p><p style=&quotes;text-align: justify;&quotes;><strong>3.&nbsp; Penguatan Pernyataan Posisi<br></strong>Pada bagian inilah, hal yang dipaparkan pada bagian sebelumnya lebih ditekankan lagi. Selain itu, simpulan dari argumen yang telah dipaparkan akan digabungkan dengan kalimat-kalimat persuasif guna memperkuat penyataan posisi atau pernyataan pendapat pada bagian awal.</p><p style=&quotes;text-align: justify;&quotes;>&nbsp;</p><p style=&quotes;text-align: justify;&quotes;><strong>D.&nbsp; Kaidah Kebahasaan Pidato Persuasif</strong></p><p style=&quotes;text-align: justify;&quotes;><strong>1.&nbsp; Nominalisasi (Pembendaan)<br></strong>Nominalisasi atau pembendaan merupakan proses pengubahan kata benda, kerja, dan sifat menjadi kata benda. Fungsinya untuk menghubungkan makna antarkalimat. Perhatikan contoh berikut.<br>(1)&nbsp;&nbsp;&nbsp; Pemerintah memberlakukan Undang-Undang Antikekerasan.<br>(2)&nbsp;&nbsp;&nbsp; Pemberlakukan tersebut melegakan banyak pihak di negeri ini.<br>Kalimat (1) dan (2) saling berhubungan yang dihubungkan oleh kata <em>memberlakukan-pemberlakuan.<br></em>Nominasi (pembendaan) digunakan saat kata benda dibentuk dari kata kerja, misalnya, <em>membangun-pembangunan, mendaur ulang-pendaurulangan, berhasil-keberhasilan, merintis-perintisan.</em></p><p style=&quotes;text-align: justify;&quotes;><strong>2.&nbsp; Bentuk Pasif dan Kata Ganti Orang<br></strong>Bentuk pasif digunakan untuk mengungkapkan sesuatu secara formal dan lebih kuat. Bentuk pasif dalam kalimat ditandai dengan imbuhan <em>di- </em>pada kata kerja yang berposii sebagai predikatnya.<br>Contoh: <em>Ini harus dihentikan.<br></em>Sementara itu, kata ganti orang yang sering digunakan dalam pidato persuasif ialah kata ganti orang ketiga atau merujuk pada sesuatu hal.<br>Contoh: <em>dia, mereka, bangsa Indonesia, warga negara.<br></em></p><p style=&quotes;text-align: justify;&quotes;><strong>3.&nbsp; Kosakata<br></strong>(1) Kosakata yang digunakan sering berupa istilah teknis. Kosakata dapat menyertakan abstrak. Sementara itu, sinonim digunakan untuk menghindari pengulangan dan menjaga agar tetap membaca tulisan.<br>(2) Rantai kata, pasangan kata (sinonim dan antonim), serta rumpun kata yang saling berkaitan makna, seperti <em>tanah, regenerasi, </em>dan <em>sumber daya alam </em>banyak digunakan.<br>(3) Kata benda abstrak yang digunakan, seperti kegembiraan, takut, dan kata-kata teknis, seperti <em>spesies </em>dan <em>genus.</em> Persoalan menjadi lebih ilmiah karena merujuk pendapat ahli.<br>(4) Kata emotif digunakan untuk melibatkan perasaan audiens, misalnya <em>Penggunaan sumber daya kita secara berlebihan akan menghancurkan tanah.<br></em>(5) Ciri penting kebahasaan adalah penggunaan kata tugas (konjungsi) yang berfungsi menghubungkan bagian-bagian teks. Kata tugas ini dapat mengaitkan gagasan dan menghubungkan sebab-akibat. Contoh kata-kata ini adalah <em>pertama kali, akhirnya, sebagai tambahan, sebab/karena, sebagai hasil dari, di pihak lain.<br></em>(6) Kata tugas menciptakan kohesi (keterpautan bentuk) dan mengekspresikan hubungan sebab-akibat, seperti, <em>sebab, karena, oleh sebab itu, </em>dan <em>maka.<br></em>(7) Alasan untuk tindakan atau pilihan ditunjukkan melalui penggunaan kata hubung antarkalimat, misalnya <em>bagaimanapun, hal yang mirip, utamanya, oleh karena itu, maka, sebab, </em>dan alasan pertama.</p><p style=&quotes;text-align: justify;&quotes;><strong>4.&nbsp; Modalitas<br></strong>Modalitas atau kepastian mulai dari yang moderat hingga derajat tinggi ditemukan dalam kata-kata terpilih, sebagai <em>contoh sering, nyaris, paling banyak, umumnya, mungkin, dapat. </em>Hal ini bergantung apakah penulis ingin merasa mendesak, membatasi diri, atau diskusi terbuka.<br>(1)&nbsp; Kalimat persuasif<br>Kalimat persuasif adalah kalimat yang berisi ajakan dan bertujuan untuk memengaruhi pembaca atau pendengar untuk melakukan sesuatu sesuai dengan kehendak penulis atau pembacanya.<br>Ciri-ciri kalimat persuasif:<br>a. Bertujuan untuk membujuk, mengajak, dan memengaruhi seseorang.<br>b. Biasanya menggunakan kata ayo, mari, dan kata-kata yang bersifat mengajak lainnya.<br><br></p><p style=&quotes;text-align: justify;&quotes;><strong>E.&nbsp; Menyimpulkan Pidato Persuasif<br></strong>Untuk dapat menyimpulkan isi dari pidato persuasif, baik yang dibaca maupun yang didengar, ada beberapa hal yang harus diperhatikan.<br><strong><br>1. Pembukaan<br></strong>Kita harus memperhatikan terlebih dahulu dari segi pembukaan yang terdapat dalam pidato persuasif tersebut. Pidato persuasif harus memiliki daya tarik tersendiri dari segi pembukaan. Cara pembukaan yang dapat memberikan daya tarik pembaca atau pendengar adalah sebagai berikut.</p><ol style=&quotes;list-style-type: lower-alpha;&quotes;><li><em>Merebut perhatian</em>, melalui pernyataan yang dramatis atau dengan bantuan visual.</li><li><em>Hubungan dengan audiensi</em>,<strong> </strong>Menunjukkan kesamaan dan empati kepada audiensi.</li><li><em>Kelayakan</em>, tunjukkan bahwa kamu layak berbicara tentang topik sebab pengalaman personal atau profesional yang kamu lakukan. Lakukan dengan santun dan berdasarkan data.</li><li><em>Tujuan</em>, jelaskan apa harapanmu setelah pidato selesai.</li><li><em>Peta jalan</em>, katakan kepada audiens pokok-pokok pikiran pidato.</li></ol><p style=&quotes;text-align: justify;&quotes;><strong>2.&nbsp; Isi<br></strong>Isi pidato merupakan penjabaran topik yang berisi pokok-pokok penting yang disertai alasan meyakinkan untuk mendukung pandanganmu. Susun secara logis, gunakan sumber tepercaya, contoh yang logis, dan dikenal audiens.</p><p style=&quotes;text-align: justify;&quotes;><strong>3.&nbsp; Penutup<br></strong>Cara menutup pidato yang menarik dan mengesankan. Tentunya, terdapat simpulan dan kalimat persuasif sebagai penutup.<br><br><img src=&quotes;{{root_media}}6ad2a535f0b5053cb6c9ba9e6369d386.png&quotes;></p><p><em>Perhatikan cuplikan ilustrasi berikut ini!</em></p><p style=&quotes;text-align: justify;&quotes;>OSIS SMA Merdeka Jaya akan melaksanakan program penyuluhan kepada masyarakat di daerah terpencil Kabupaten Bandung. Tema yang diangkat dalam penyuluhan tersebut yakni “Bahaya Penggunaan dan Penyalahgunaan Narkoba”. Kegiatan tersebut akan dihadiri oleh narasumber dari pihak berwajib, kepolisian, setempat. Sebagai ketua OSIS sekaligus ketua pelaksanan penyuluhan tersebut, Maharaja akan menyampaikan pidatonya.</p><p style=&quotes;text-align: justify;&quotes;>Bagian penutup pidato persuasif Maharaja yang tepat berdasarkan ilustrasi tersebut adalah ....<br>(A) Demikian teman-teman, semoga program ini dapat membuat kita menjadi waspada dan tertib terhadap kegiatan berlalu lintas.<br>(B) Demikian pidato saya kali ini. Saya selaku perwakilan pihak berwajib meminta agar seluruh masyarakat tetap waspada dengan kejahatan narkoba dan menolak dengan keyakinan yang pasti jika ditawari barang tersebut, meskipun secara cuma-cuma.<br>(C) Demikian teman-teman, sesuai dengan program yang telah disepakati bersama dalam penuluhan ini. Mari, kita ikuti kegiatan ini sampai selesai guna mendapatkan informasi yang menyeluruh dan memahami dampak narkoba bagi diri sendiri, keluarga, lingkungan, dan masyakarat.<br>(D) Teman-teman yang saya sayangi, mari kita ikuti kegiatan ini dengan penuh khidmat sampai selesai agar mendapatkan manfaat.<br>(E) Teman-temanku sekalian, kegiatan ini kita lakukan hanya dengan satu tujuan yakni menjaga diri kita dari perbuatan tercela dan berbahaya.</p><p style=&quotes;text-align: justify;&quotes;><img src=&quotes;{{root_media}}1cb4cf429db95682d1ee96eafd859310.png&quotes;></p><p style=&quotes;text-align: justify;&quotes;><strong>Soal</strong><strong> </strong><strong>Latihan<br></strong><em>Perhatikan kalimat berikut ini!<br></em>Kampus ini lajak menjadi tempat yang dapat dijadikan sebagai teladan dan belajar untuk mewujudkan kesuksesan yang diimpikan setiap orang.<br>Jenis nominalisasi yang terdapat pada kalimat tersebut adalah<br>(A)&nbsp; Konfiks pada kata <em>mewujudkan</em>.<br>(B)&nbsp; Konfiks pada kata <em>dijadikan</em>.<br>(C)&nbsp; Prefiks pada kata <em>menjadi</em>.<br>(D)&nbsp; Prefiks pada kata <em>belajar</em>.<br>(E)&nbsp; Konfiks pada kata <em>kesuksesan</em>.<br><img src=&quotes;{{root_media}}4f8826d332b4de355cf7e7626b5858c7.png&quotes;></p><p style=&quotes;text-align: justify;&quotes;>&nbsp;</p><p style=&quotes;text-align: justify;&quotes;>&nbsp;</p><p style=&quotes;text-align: justify;&quotes;>&nbsp;</p>" //String || html
        },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```
## pilihan Kelompok Ujian
### Get Opsi Kelompok Ujian 

Request :
- Method : GET
- Endpoint : `/mobile/v1/opsiKelompokUjian`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
       {
                "idKelompokUjian":122, //int
                "nama":"Matematika", //String
                "initial":"Mtk" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```
### Get pilihan Kelompok Ujian 

Request :
- Method : GET
- Endpoint : `/mobile/v1/pilihan/kelompokUjian`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
       {
                "idKelompokUjian":122, //int
                "nama":"Matematika", //String
                "initial":"Mtk" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```
## profile

### Get Avatar Profile

Request :
- Method : GET
- Endpoint : `/mobile/v1/profile/avatar/{noRegistrasi}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data":  "https://firebasestorage.googleapis.com/v0/b/kreasi-f1f7b.appspot.com/o/avatar%2Fb-1.png?alt=media&token=8bfb2b14-2d49-4d7a-9917-a6966c88773a",//String

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```

## Get Version

Request :
- Method : GET
- Endpoint : `/mobile/v1/version`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
            "isWajib": true, //bool
            "isWajibIOS": true, //bool
            "isWajibANDRO": true, //bool
            "title": "Update GO Kreasi", //String
            "description": "Hallo Sobat GO! MinGO mau infoin nih klo GO Kreasi ada update versi terbaru loh! Update dulu yuk Sobat, biar kegiatan belajar kamu lebih nyaman lagi Sobat. Kasih tau MinGO yaa kalau Sobat ada pertanyaan. :)", //String
            "notes": [
                "Update persiapan TOBK januari 2023.", //String
                "Update lihat laporan." //String
            ],
            "ios": {
                "url": "https://apps.apple.com/app/id1634767332",//String
                "altUrl": "https://apps.apple.com/app/go-kreasi-siswa-ortu/id1634767332", //String
                "version": "1.1.2", //String
                "versionNumber": 112, //int
                "buildNumber": 1 //int
            },
            "android": {
                "url": "market://details?id=com.ganeshaoperation.kreasiv4", //String
                "altUrl": "https://play.google.com/store/apps/details?id=com.ganeshaoperation.kreasiv4", //String
                "version": "1.1.2", //String
                "versionNumber": 112, //int
                "buildNumber": 47 //int
            }
        },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
} 
```
### Set Aktivitas Belajar Siswa (ABS)

Request :
- Method : post
- Endpoint : `/mobile/v1/simpan/log`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
- body :
```json
    {"nis":"040916026101", //String
    "jenis":"SISWA", //String
    "menu":"Buku Teori", //String
    "keterangan":"BAHASA INDONESIA, Teks Anekdot", //String
    "akses":"Masuk", //String
    "lastupdate":"2023-09-15 22:01:11" //String
    }
```
Response :

```json 
{
   "data": [
            {
                "c_NoRegistrasi": "050111114701", //String
                "c_Menu": "Buku Teori", //String
                "c_Keterangan": "BAHASA INDONESIA, Teks Cerita Sejarah/ Rekon", //String
                "c_WaktuAwal": "2023-09-05 14:04:28" //String
            }
        ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### get Notif

Request :
- Method : get
- Endpoint : `/mobile/v1/notif`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
   "data": [
     {
                "notifId": "139284", // String
                "sourceId": "130913848001", // String
                "sourceName": "Dzakhwan Djalaluddin M Akbar", // String
                "classlevelid": "4", // String
                "role": "SISWA", // String
                "notifType": "comment new", // String
                "isSeen": true, //bool
                "date": "2023-07-22 14:13:15", // String || date
                "className": "12-IPA-R-N-103", // String
                "info": {
                    "role": "SISWA", // String
                    "image": "http://images.ganeshaoperation.com/gokreasi/feed/981123000001/033af7bf2f5c1f0c3f395dee036ecfd7.jpeg", // String
                    "feedId": 26353, //int
                    "isLike": 1, //int
                    "status": "publik", // String
                    "content": "[FLEXING TRYOUT]\nHai guys, saya dapat nilai tryout segini loh!\nJangan mau kalah ya Sobat", // String
                    "tanggal": "2023-06-13 14:55:52.000000", // String
                    "fullname": "DZAKHWAN DJALALUDDIN M AKBAR", // String
                    "creatorId": "981123000001", // String
                    "totalLike": 1 //int
                }
            },
        ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## jadwal dan Video

### get Jadwal
 Request :
- Method : get
- Endpoint : `/mobile/v1/jadwal`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
     "2023-09-08": [
            {
                "classId": "269227", //String
                "date": "2023-09-08", //String
                "start": "18:30", //String
                "finish": "20:00", //String
                "lesson": "BIOLOGI", //String
                "package": "2", //String
                "info": "Paket Ke", //String
                "id": "1402503048",
                "fullName": "ISTIANATIN NURIYAH", //String
                "activity": "KBM JPMP", //String
                "planId": "10527161", //String
                "placeName": "Citra Utama Timur 1B", //String
                "remainingMeeting": "-", //String
                "available": "no", //String
                "feedbackPermission": false, //bool
                "session": 1 //int
            }
        ]
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
### get List Video Mapel
 Request :
- Method : get
- Endpoint : `/mobile/v1/video/mapel`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {   "iconMapel":"https://firebasestorage.googleapis.com/v0/b/kreasi-f1f7b.appspot.com/o/icon%2Fmapel%2Fmapel_indo.webp?alt=media&token=c2641f9f-b8f0-42c9-90e7-488a759aaf78", //String
                "c_IdMataPelajaran": "6", //String
                "c_NamaMataPelajaran": "BAHASA INDONESIA", //String
                "c_Level": "SMA" //String
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
### get List Video Bab
 Request :
- Method : get
- Endpoint : `/mobile/v1/video/mapel/{kodeMapel}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
       {
                "babutama": "SASTRA", //String
                "info": [
                    {
                        "c_namabab": "Puisi", //String
                        "c_kodebab": "06.07.01", //String
                        "c_IdVideo": "3080", //String
                        "c_JudulVideo": "Puisi", //String
                        "c_Deskripsi": "Puisi adalah bentuk karya sastra dari hasil ungkapan rasa dan perasaan penyair yang penuh makna.", //String
                        "c_LinkVideo": "http://streaming.ganeshaoperation.com/index.php?v=Wkcxc2ExcFhPVEJhVnpsNVlWTTVhRTVxV21oYVIxSnRUVVJKTkZwRWJHaFBSRUV6VDFkU2JGbHFaR2hOTWs1dFdtMVJNRmxxYkd4T2VUVjBZMFJSUFE9PQ==" //String
                    },
                   
                ]
            },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### get Jadwal TST
 Request :
- Method : get
- Endpoint : `/mobile/v1/jadwal/tst`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [  //data harus 2 tanggal hari ini dan besok.
      {
                "date": "2023-09-16", //String || date
                "teachers": [
                    {
                        "teacher": "Rayhan Hudan Satrio", //String
                        "lesson": "MATEMATIKA", //String
                        "schedule": [
                            {
                                "planId": "10608883", //String
                                "teacherId": "2023540051", //String
                                "buildingName": "SARIKAYA 148", //String
                                "activity": "TST Super", //String
                                "start": "14:30", //String
                                "finish": "16:30", //String
                                "isTST": true, //bool
                                "available": true, //bool
                                "registered": "Belum" //String
                            }
                        ]
                    }
                ]
            },
            {
                "date": "2023-09-17",
                "teachers": []
            },
            
                ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### get video Teaser
 Request :
- Method : get
- Endpoint : `/mobile/v1/video/teaser`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": "http://streaming.ganeshaoperation.com/index.php?v=Wkcxc2ExcFhPVEJhVjBaNldsaEpkazlFUVhwT1ZHTjRUbXBvYkZsNldYZFBWRnB0VGxkT2FVMVhVWHBPVjBWM1RVZFplbGxYVm1sT1JFVjFZbGhCTUE9PQ==", //String

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```






*[Dokumentasi Endpoint API](https://docs.google.com/spreadsheets/d/1-BoVrjKcfo3SslzNT5Me3HpYR5e_83Fb8Hmfc1VDYE0/edit#gid=0)*.