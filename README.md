# API Spec

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

### Laporan Aktivitas Belajar Siswa (ABS)
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
            "kode_tob": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_jenis_produk": "string, unique",
            "id_sekolah_kelas": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "nomor_urut": "number",
            "isBlockingTime": "boolean",
            "tanggal_berlaku": "date",
            "tanggal_kadaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string",
            "isSelesai": "boolean",
            "isPernahMengerjakan": "boolean",
            "tanggal_mulai": "date",
            "tanggal_deadline": "date",
            "tanggal_pengumpulan": "date",
            "merk": "Unknown",
            "waktu_habis": "boolean"
        }
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
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "isLulus": "boolean",
            "id_jenis_produk": "string, unique",
            "IsBlockingTime": "boolean",
            "id_sekolah_kelas": "41",
            "tanggal_berlaku": "date",
            "tanggal_kedaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string"
        }
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
    "data" : {
        {
            "id_soal": "string, unique",
            "soal": "string",
            "opsi": [
                {
                    "pilihan": "string, unique", // cnth:  A, B, C, D
                    "text": "string",
                    "isJawaban": "boolean",
                }
            ],
            "id_wacana": "string, unique",
            "id_tipe_soal": "string, unique",
            "tipe_soal": "string",
            "tingkat_kesulitan": "number",
            "wacana": "string",
            "nama_kelompok_ujian": "string",
            "kode_paket": "string, unique",
            "id_bundel": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_video": "string, unique",
            "nomor_soal": "number"
        },
        "waktu": "time",
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
        "waktu": "time",
        "data_detail": [
            {
                "wacana": "",
                "id_soal": "string, unique",
                "nomor_soal": "1",
                "id_wacana": "string, unique",
                "id_bundel": "string, unique",
                "id_kelompok_ujian": "string, unique",
                "nama_kelompok_ujian": "string",
                "id_video": "string, unique",
                "soal": "string",
                "opsi": [
                    {
                        "pilihan": "string, unique", // cnth:  A, B, C, D
                        "text": "string",
                        "isJawaban": "boolean",
                    }
                ],
                "tipe_soal": "enum || string",
                "tingkat_kesulitan": "number",
                "kode_paket": "EMWA-754" //cnth: EMWA-754
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
            "kode_tob": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_jenis_produk": "string, unique",
            "id_sekolah_kelas": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "nomor_urut": "number",
            "isBlockingTime": "boolean",
            "tanggal_berlaku": "date",
            "tanggal_kadaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string",
            "isSelesai": "boolean",
            "isPernahMengerjakan": "boolean",
            "tanggal_mulai": "date",
            "tanggal_deadline": "date",
            "tanggal_pengumpulan": "date",
            "merk": "Unknown",
            "waktu_habis": "boolean"
        }
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
        {
            "id_soal": "string, unique",
            "soal": "string",
            "opsi": [
                {
                    "pilihan": "string, unique", // cnth:  A, B, C, D
                    "text": "string",
                    "isJawaban": "boolean",
                }
            ],
            "id_wacana": "string, unique",
            "id_tipe_soal": "string, unique",
            "tipe_soal": "string",
            "tingkat_kesulitan": "number",
            "wacana": "string",
            "nama_kelompok_ujian": "string",
            "kode_paket": "string, unique",
            "id_bundel": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_video": "string, unique",
            "nomor_soal": "number"
        },
        "waktu": "time",
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
            "kode_tob": "string, unique",
            "nama_tob": "string",
            "jenis_tob": "string || enum",
            "tanggal_mulai": "date",
            "tanggal_selesai": "date",
            "jarak_antar_paket": "number",
            "isKurikulumMerdeka": "boolean",
            "isBersyarat": "boolean",
            "jenis": "string",
        }
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
            "kode_tob": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_jenis_produk": "string, unique",
            "id_sekolah_kelas": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "nomor_urut": "number",
            "isBlockingTime": "boolean",
            "totalWaktu": "time",
            "total_soal": "number",
            "isRandom": "boolean",
            "isSelesai": "boolean",
            "isPernahMengerjakan": "boolean",
            "isOK": "boolean",
            "tanggal_mulai": "date",
            "tanggal_deadline": "date",
            "tanggal_pengumpulan": "date",
            "merk": "Unknown",
            "keterangan": null,
            "pilihan_siswa": null,
            "flag": null,
            "waktu_habis": "boolean",
            "isWajib": "boolean"
        }
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
        {
            "id_soal": "string, unique",
            "soal": "string",
            "opsi": [
                {
                    "pilihan": "string, unique", // cnth:  A, B, C, D
                    "text": "string",
                    "isJawaban": "boolean",
                }
            ],
            "id_wacana": "string, unique",
            "id_tipe_soal": "string, unique",
            "tipe_soal": "string",
            "tingkat_kesulitan": "number",
            "wacana": "string",
            "nama_kelompok_ujian": "string",
            "kode_paket": "string, unique",
            "id_bundel": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_video": "string, unique",
            "nomor_soal": "number"
        },
        "waktu": "time",
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
           "kelompok_ujian": "string",
           "info": [
                {
                    "nama_bab": "string",
                    "kode_bab": "string",
                    "level_teori": "string || enum",
                    "id_mapel": "string",
                    "inisial_mapel": "string"
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
            "isLulus": "boolean",
            "isSelesai": "boolean",
            "total_soal": "number",
            "total_benar": "number",
            "total_salah": "number",
            "total_kosong": "number",
            "listEmpati": [
                {
                    "kode_tob": "string, unique",
                    "kode_paket": "string, unique",
                    "total_soal": "number",
                    "total_benar": "number",
                    "total_salah": "number",
                    "isBoleh": "boolean",
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
            "kode_tob": "string, unique",
            "nama_tob": "string",
            "jenis_tob": "string || enum",
            "tanggal_mulai": "date",
            "tanggal_selesai": "date",
            "jarak_antar_paket": "number",
            "isKurikulumMerdeka": "boolean",
            "isBersyarat": "boolean",
            "jenis": "string",
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
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "isLulus": "boolean",
            "id_jenis_produk": "string, unique",
            "IsBlockingTime": "boolean",
            "id_sekolah_kelas": "41",
            "tanggal_berlaku": "date",
            "tanggal_kedaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string"
        }
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
- Endpoint : `/mobile/v1/buku-sakti/list/emma`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "isLulus": "boolean",
            "id_jenis_produk": "string, unique",
            "IsBlockingTime": "boolean",
            "id_sekolah_kelas": "41",
            "tanggal_berlaku": "date",
            "tanggal_kedaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string"
        }
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
            "id_bundel": "string, unique",
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial": "string",
            "waktu_pengerjaan": "time",
            "total_soal": "number",
            "opsi_urut": "string",
            "id_sekolah_kelas": "string, unique",
            "jenis": "string" //cnth: teaser
        }
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
            "id_bundel": "string, unique",
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial": "string",
            "waktu_pengerjaan": "time",
            "total_soal": "number",
            "opsi_urut": "string",
            "id_sekolah_kelas": "string, unique",
            "jenis": "string" //cnth: teaser
        }
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
            "id_bundel": "string, unique",
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial": "string",
            "waktu_pengerjaan": "time",
            "total_soal": "number",
            "opsi_urut": "string",
            "id_sekolah_kelas": "string, unique",
            "jenis": "string" //cnth: teaser
        }
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
            "id_bundel": "string, unique",
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial": "string",
            "waktu_pengerjaan": "time",
            "total_soal": "number",
            "opsi_urut": "string",
            "id_sekolah_kelas": "string, unique",
            "jenis": "string" //cnth: teaser
        }
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
            "kode_tob": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_jenis_produk": "string, unique",
            "id_sekolah_kelas": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "nomor_urut": "number",
            "isBlockingTime": "boolean",
            "tanggal_berlaku": "date",
            "tanggal_kadaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string",
            "isSelesai": "boolean",
            "isPernahMengerjakan": "boolean",
            "tanggal_mulai": "date",
            "tanggal_deadline": "date",
            "tanggal_pengumpulan": "date",
            "merk": "Unknown",
            "waktu_habis": "boolean"
        }
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
            "id_bundel": "string, unique",
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial": "string",
            "waktu_pengerjaan": "time",
            "total_soal": "number",
            "opsi_urut": "string",
            "id_sekolah_kelas": "string, unique",
            "jenis": "string" //cnth: teaser
        }
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
    "data": [
        {
            "bab_utama": "string",
            "info": [
                {
                    "nama_bab": "string",
                    "jumlah_soal": "number",
                    "kode_bab": "string, unique",
                    "id_bundel": "string, unique",
                }
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
            "bab_utama": "string",
            "info": [
                {
                    "nama_bab": "string",
                    "jumlah_soal": "number",
                    "kode_bab": "string, unique",
                    "id_bundel": "string, unique",
                }
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
            "bab_utama": "string",
            "info": [
                {
                    "nama_bab": "string",
                    "jumlah_soal": "number",
                    "kode_bab": "string, unique",
                    "id_bundel": "string, unique",
                }
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
            "bab_utama": "string",
            "info": [
                {
                    "nama_bab": "string",
                    "jumlah_soal": "number",
                    "kode_bab": "string, unique",
                    "id_bundel": "string, unique",
                }
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
            "bab_utama": "string",
            "info": [
                {
                    "nama_bab": "string",
                    "jumlah_soal": "number",
                    "kode_bab": "string, unique",
                    "id_bundel": "string, unique",
                }
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
- Endpoint : `/mobile/v1/buku-sakti/soal-emwa`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
        "waktu": "time",
        "data_detail": [
            {
                "wacana": "",
                "id_soal": "string, unique",
                "nomor_soal": "1",
                "id_wacana": "string, unique",
                "id_bundel": "string, unique",
                "id_kelompok_ujian": "string, unique",
                "nama_kelompok_ujian": "string",
                "id_video": "string, unique",
                "soal": "string",
                "opsi": [
                    {
                        "pilihan": "string, unique", // cnth:  A, B, C, D
                        "text": "string",
                        "isJawaban": "boolean",
                    }
                ],
                "tipe_soal": "enum || string",
                "tingkat_kesulitan": "number",
                "kode_paket": "EMWA-754" //cnth: EMWA-754
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

### Soal Buku Sakti - EMMA

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal-emma`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
        "waktu": "time",
        "data_detail": [
            {
                "wacana": "",
                "id_soal": "string, unique",
                "nomor_soal": "1",
                "id_wacana": "string, unique",
                "id_bundel": "string, unique",
                "id_kelompok_ujian": "string, unique",
                "nama_kelompok_ujian": "string",
                "id_video": "string, unique",
                "soal": "string",
                "opsi": [
                    {
                        "pilihan": "string, unique", // cnth:  A, B, C, D
                        "text": "string",
                        "isJawaban": "boolean",
                    }
                ],
                "tipe_soal": "enum || string",
                "tingkat_kesulitan": "number",
                "kode_paket": "EMWA-754" //cnth: EMWA-754
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

### Soal Buku Sakti - Lateks

Request :
- Method : GET
- Endpoint : `/mobile/v1/buku-sakti/soal-lateks`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
        {
            "waktu": "time",
            "data_detail": [
                {
                    "id_bundel": "string, unique",
                    "kode_bab": "string, unique",
                    "id_soal": "string, unique",
                    "id_kelompok_ujian": "string, unique",
                    "nama_kelompok_ujian": "string",
                    "soal": "string",
                    "opsi": [
                        {
                            "opsi_detail": [
                                {
                                    "pilihan": "string, unique", // cnth:  A, B, C, D
                                    "text": "string",
                                    "isJawaban": "boolean",
                                }
                            ],
                            "nilai": {
                                "fullcredit": "number",
                                "halfcredit": "number",
                                "zerocredit": "number",
                            }
                        }
                    ],
                    "id_wacana": "string, unique",
                    "tipe_soal": "string || enum",
                    "tingkat_kesulitan": "number",
                    "nomor_soal": "number",
                    "id_video": null,
                    "wacana": "string",
                    "inisial_mapel": "string"
                }
            ],
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
- Endpoint : `/mobile/v1/buku-sakti/soal/soal-koding`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
        {
            "waktu": "time",
            "data_detail": [
                {
                    "id_bundel": "string, unique",
                    "kode_bab": "string, unique",
                    "id_soal": "string, unique",
                    "id_kelompok_ujian": "string, unique",
                    "nama_kelompok_ujian": "string",
                    "soal": "string",
                    "opsi": [
                        {
                            "opsi_detail": [
                                {
                                    "pilihan": "string, unique", // cnth:  A, B, C, D
                                    "text": "string",
                                    "isJawaban": "boolean",
                                }
                            ],
                            "nilai": {
                                "fullcredit": "number",
                                "halfcredit": "number",
                                "zerocredit": "number",
                            }
                        }
                    ],
                    "id_wacana": "string, unique",
                    "tipe_soal": "string || enum",
                    "tingkat_kesulitan": "number",
                    "nomor_soal": "number",
                    "id_video": null,
                    "wacana": "string",
                    "inisial_mapel": "string"
                }
            ],
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
            "waktu": "time",
            "data_detail": [
                {
                    "id_bundel": "string, unique",
                    "kode_bab": "string, unique",
                    "id_soal": "string, unique",
                    "id_kelompok_ujian": "string, unique",
                    "nama_kelompok_ujian": "string",
                    "soal": "string",
                    "opsi": [
                        {
                            "opsi_detail": [
                                {
                                    "pilihan": "string, unique", // cnth:  A, B, C, D
                                    "text": "string",
                                    "isJawaban": "boolean",
                                }
                            ],
                            "nilai": {
                                "fullcredit": "number",
                                "halfcredit": "number",
                                "zerocredit": "number",
                            }
                        }
                    ],
                    "id_wacana": "string, unique",
                    "tipe_soal": "string || enum",
                    "tingkat_kesulitan": "number",
                    "nomor_soal": "number",
                    "id_video": null,
                    "wacana": "string",
                    "inisial_mapel": "string"
                }
            ],
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
- Endpoint : `/mobile/v1/buku-sakti/soal/soal-referensi`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
        {
            "waktu": "time",
            "data_detail": [
                {
                    "id_bundel": "string, unique",
                    "kode_bab": "string, unique",
                    "id_soal": "string, unique",
                    "id_kelompok_ujian": "string, unique",
                    "nama_kelompok_ujian": "string",
                    "soal": "string",
                    "opsi": [
                        {
                            "opsi_detail": [
                                {
                                    "pilihan": "string, unique", // cnth:  A, B, C, D
                                    "text": "string",
                                    "isJawaban": "boolean",
                                }
                            ],
                            "nilai": {
                                "fullcredit": "number",
                                "halfcredit": "number",
                                "zerocredit": "number",
                            }
                        }
                    ],
                    "id_wacana": "string, unique",
                    "tipe_soal": "string || enum",
                    "tingkat_kesulitan": "number",
                    "nomor_soal": "number",
                    "id_video": null,
                    "wacana": "string",
                    "inisial_mapel": "string"
                }
            ],
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
- Endpoint : `/mobile/v1/buku-sakti/soal-kuis`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
        {
            "id_soal": "string, unique",
            "soal": "string",
            "opsi": [
                {
                    "pilihan": "string, unique", // cnth:  A, B, C, D
                    "text": "string",
                    "isJawaban": "boolean",
                }
            ],
            "id_wacana": "string, unique",
            "id_tipe_soal": "string, unique",
            "tipe_soal": "string",
            "tingkat_kesulitan": "number",
            "wacana": "string",
            "nama_kelompok_ujian": "string",
            "kode_paket": "string, unique",
            "id_bundel": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_video": "string, unique",
            "nomor_soal": "number"
        },
        "waktu": "time",
    },

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
            "waktu": "time",
            "data_detail": [
                {
                    "id_bundel": "string, unique",
                    "kode_bab": "string, unique",
                    "id_soal": "string, unique",
                    "id_kelompok_ujian": "string, unique",
                    "nama_kelompok_ujian": "string",
                    "soal": "string",
                    "opsi": [
                        {
                            "opsi_detail": [
                                {
                                    "pilihan": "string, unique", // cnth:  A, B, C, D
                                    "text": "string",
                                    "isJawaban": "boolean",
                                }
                            ],
                            "nilai": {
                                "fullcredit": "number",
                                "halfcredit": "number",
                                "zerocredit": "number",
                            }
                        }
                    ],
                    "id_wacana": "string, unique",
                    "tipe_soal": "string || enum",
                    "tingkat_kesulitan": "number",
                    "nomor_soal": "number",
                    "id_video": null,
                    "wacana": "string",
                    "inisial_mapel": "string"
                }
            ],
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
            "kode_tob": "string, unique",
            "tob": "string",
            "isSelected": "boolean",
            "isFix": "boolean",
            "detail_nilai": {
                "nama_subtes":  "string",
                "nilai_score": "number",
            }
        }
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
            "prioritas": "number",
            "status": "boolean",
            "universitas": "string",
            "id_jurusan": "string, unique",
            "nama_jurusan": "string",
            "passing_grade": "number",
            "peminat": {
                "total": "number",
                "tahun": "string"
            },
            "tampung": {
                "total": "number",
                "tahun": "string"
            }
        }
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
            "prioritas": "number",
            "status": "boolean",
            "universitas": "string",
            "id_jurusan": "string, unique",
            "nama_jurusan": "string",
            "rumpun": "string || null",
            "passing_grade": "number",
            "peminat": {
                "total": "number",
                "tahun": "string"
            },
            "tampung": {
                "total": "number",
                "tahun": "string"
            },
            "total": "number",
            "saran": "string || null"
        }
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
- Endpoint : `/mobile/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "icon_mapel": "string",
            "list_bookmark": [
                {
                    "id_soal": "string, unique",
                    "isPaket": "boolean",
                    "kode_bab": "string, unique",
                    "kode_tob": "string, unique",
                    "nama_bab": "string",
                    "id_bundel": "string, unique",
                    "isSimpan": "boolean",
                    "kode_paket": "string, unique",
                    "nomor_soal": "number",
                    "last_update": "date",
                    "id_jenis_produk": "number",
                    "nomor_soal_siswa": "number",
                    "nama_jenis_produk": "string",
                    "tanggal_kadaluwarsa": "date || null"
                },
            ],
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial_kelompok_ujian": "string"
        }
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
- Endpoint : `/mobile/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "id_pembelian": "string, unique",
            "total_harga": "number",
            "total_dibayar": "number",
            "sisa_bayar": "number",
            "status": "enum",
        }
    ],

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
            "id_pembelian": "string, unique",
            "total_harga": "number",
            "total_dibayar": "number",
            "sisa_bayar": "number",
            "status": "enum",
            "tanggal_jatuhtempo": "Date"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


*[Dokumentasi Endpoint API](https://docs.google.com/spreadsheets/d/1-BoVrjKcfo3SslzNT5Me3HpYR5e_83Fb8Hmfc1VDYE0/edit#gid=0)*.