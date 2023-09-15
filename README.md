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


*[Dokumentasi Endpoint API](https://docs.google.com/spreadsheets/d/1-BoVrjKcfo3SslzNT5Me3HpYR5e_83Fb8Hmfc1VDYE0/edit#gid=0)*.