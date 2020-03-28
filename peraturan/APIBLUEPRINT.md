FORMAT: 1A
HOST: http://api.pemiluapi.org/pertanyaan/api/

# Peraturan API
The Peraturan API is a service that provides answers to questions about rules and regulations affecting the 2014 Indonesian elections.  It's part of [API Pemilu](http://developer.pemiluapi.org/)

Sample call: [http://api.pemiluapi.org/pertanyaan/api/questions?apiKey=fea6f7d9ec0b31e256a673114792cb17](http://api.pemiluapi.org/pertanyaan/api/questions?apiKey=fea6f7d9ec0b31e256a673114792cb17)


# Group Questions
Question related resources of the **Peraturan API**

## Question Collection [/questions?apiKey={apiKey}&tags={tags}&law={law}&limit={limit}&offset={offset}]
A list of Question objects with abbreviated details (no riwayat pendidikan, pekerjaan, or organisasi)

+ Parameters
    + offset (optional, number, `300`) ... Number the offset from the beginning of the list of records to return (use in combination with `limit` to support pagination)
    + limit (optional, number, `25`) ... Number the number of records to return (use in combination with `offset` to support pagination)
    + law (optional, string, `UU No. 8 Tahun 2012`) ... String full or partial name of a `law` relevant to the question. Will return all matching records.
    + tags (optional, string, `women,participation`) ... String list of `tags` by which to filter the questions.
    + apiKey (required, string, `06ec082d057daa3d310b27483cc3962e`) ... String `apiKey` of the application.

### List Pertanyaan [GET]
+ Response 200 (application/json)

        {
            "data": {
                "results": {
                    "count": 86,
                    "total": 86,
                    "questions": [{
                        "id": "001",
                        "question": "Apakah perempuan bisa mencalonkan diri dalam pemilu?",
                        "answer": "Ya, setiap warga negara indonesia baik perempuan maupun laki-laki memiliki hak untuk terlibat dalam pemerintahan",
                        "reference_law": "UUD 1945 Pasal 26 Ayat (1),",
                        "excerpt_law": "Pasal 26: (1) Yang menjadi warga negara ialah orang orang bangsa Indonesia asli dan orang orang bangsa lain yang disahkan dengan undangundang sebagai warga negara.",
                        "tags": ["Perempuan", "Hak Asasi Manusia", "Emansipasi", "Women"]
                    }, {
                        "id": "002",
                        "question": "Berapa jumlah perempuan yang dibolehkan mengikuti pemilu?",
                        "answer": "Tidak ada jumlah maksimal perempuan yang boleh menjadi peserta pemilu. Sebaliknya, partai politik yang menjadi peserta pemilu wajib menyertakan calon perempuan sebanyak minimal 30% (tiga puluh persen) dari total calon yang diajukannya.",
                        "reference_law": "UU No. 8 Tahun 2012 Pasal 8 Ayat (2) Huruf (e) dan Pasal 15 Huruf (d),",
                        "excerpt_law": "Pasal 8: Ayat (2) Partai politik yang tidak memenuhi ambang batas perolehan suara pada Pemilu sebelumnya atau partai politik baru dapat menjadi Peserta Pemilu setelah memenuhi persyaratan: (e) Menyertakan sekurang-kurangnya 30% (tiga puluh persen) keterwakilan perempuan pada kepengurusan partai politik tingkat pusat; Pasal 15 : Dokumen persyaratan sebagaimana dimaksud dalam Pasal 14 ayat (3) tentang Pendaftaran Partai Politik sebagai Calon Peserta Pemilu meliputi: (d) surat keterangan dari pengurus pusat partai politik tentang penyertaan keterwakilan perempuan sekurang-kurangnya 30% (tiga puluh persen) sesuai dengan ketentuan peraturan perundang-undangan;",
                        "tags": ["Perempuan", "Affirmative Action", "Partisipasi", "Ambang Batas", "Pendaftaran", "Caleg", "Women", "First Time Voters"]
                    }]
                }
            }
        }

## Question [/questions/{id}?apiKey={apiKey}]
A single Pertanyaan object with all its details

+ Parameters
    + apiKey (required, string, `06ec082d057daa3d310b27483cc3962e`) ... String `apiKey` of the application.
    + id (required, string, `002`) ... String `id` of the Question to perform action with.

### Retrieve a Question [GET]
+ Response 200 (application/json)

        {
            "data": {
                "results": {
                    "count": 1,
                    "total": 1,
                    "questions": [{
                        "id": "002",
                        "question": "Berapa jumlah perempuan yang dibolehkan mengikuti pemilu?",
                        "answer": "Tidak ada jumlah maksimal perempuan yang boleh menjadi peserta pemilu. Sebaliknya, partai politik yang menjadi peserta pemilu wajib menyertakan calon perempuan sebanyak minimal 30% (tiga puluh persen) dari total calon yang diajukannya.",
                        "reference_law": "UU No. 8 Tahun 2012 Pasal 8 Ayat (2) Huruf (e) dan Pasal 15 Huruf (d),",
                        "excerpt_law": "Pasal 8: Ayat (2) Partai politik yang tidak memenuhi ambang batas perolehan suara pada Pemilu sebelumnya atau partai politik baru dapat menjadi Peserta Pemilu setelah memenuhi persyaratan: (e) Menyertakan sekurang-kurangnya 30% (tiga puluh persen) keterwakilan perempuan pada kepengurusan partai politik tingkat pusat; Pasal 15 : Dokumen persyaratan sebagaimana dimaksud dalam Pasal 14 ayat (3) tentang Pendaftaran Partai Politik sebagai Calon Peserta Pemilu meliputi: (d) surat keterangan dari pengurus pusat partai politik tentang penyertaan keterwakilan perempuan sekurang-kurangnya 30% (tiga puluh persen) sesuai dengan ketentuan peraturan perundang-undangan;",
                        "tags": ["Perempuan", "Affirmative Action", "Partisipasi", "Ambang Batas", "Pendaftaran", "Caleg", "Women", "First Time Voters"]
                    }]
                }
            }
        }

# Group Tags
Tag related resources of the **Peraturan API**

## Tags Collection [/tags?apiKey={apiKey}]
A list of Tags objects

+ Parameters
    + apiKey (required, string, `06ec082d057daa3d310b27483cc3962e`) ... String `apiKey` of the application.

### List all Tags [GET]
+ Response 200 (application/json)

        {
            "data": {
                "results": {
                    "count": 9,
                    "tags": [{
                        "tag": "2014",
                        "question_count": 1
                    }, {
                        "tag": "Aceh",
                        "question_count": 3
                    }, {
                        "tag": "Affirmative Action",
                        "question_count": 3
                    }, {
                        "tag": "Akreditasi",
                        "question_count": 6
                    }, {
                        "tag": "Ambang Batas",
                        "question_count": 2
                    }, {
                        "tag": "Aspirasi",
                        "question_count": 1
                    }, {
                        "tag": "Badan",
                        "question_count": 1
                    }, {
                        "tag": "Bantuan Khusus",
                        "question_count": 5
                    }, {
                        "tag": "Batas Usia",
                        "question_count": 1
                    }]
                }
            }
        }
