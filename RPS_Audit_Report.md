# RPS Accreditation Readiness Audit — S1 Informatika FT UKWMS

Audit date: 9 Oct 2026 · Reference: `Tabel 7. Pemetaan CPL – MK` (71 rows) · Criteria: see `CLAUDE.md`

## 1. Verdict

**Not ready for accreditation.** No course passes all checks yet.

| Severity | Courses | Meaning |
|---|---|---|
| **HIGH** | **61** | No RPS (16), a blank template (4), an old or skeleton form (3), or a header that is filled in while the weekly plan, rubric and RTM are missing or copied from another course (38) |
| **MEDIUM** | **9** | The weekly plan is genuine, but the rubric or RTM is missing or wrong, or the identity, CPL or form is outdated |
| LOW / OK | 0 | — |

(70 distinct courses. Row 68 INF470 duplicates row 60 INF455 in Tabel 7. See §5.)

### The main problem: template leftovers in every UKWMS-format RPS
All **43** `.docx` RPS files in the new UKWMS template (Andrew, Devi, Philipus, Slamet), not counting the 10 "Copy of" duplicates, still contain sample content from the template:

| Section | What is actually in the file | Affected |
|---|---|---|
| Rencana mingguan (minggu 1–16) | Week 1 is "Pengenalan web dan dasar pemrograman" and weeks 2–UAS are **Social Network Analysis** ("sentralitas jaringan", "AJS", CPMK081–084). The text is byte-identical across files (one variant only edits week 1) | 31 files |
| Rencana mingguan | **Empty** table (no weeks filled in) | Slamet: 8 files |
| Rencana mingguan | Copied from **Basis Data** | Basis Data Lanjut, PWL, Prak. Basis Data |
| Rubrik penilaian | Template "Contoh RUBRIK" for **SNA** with CPMK081–084 | **all 43** |
| Rencana Tugas Mahasiswa | **"Front End Web Programming"**, dosen Devi, Tugas 1 = HTML | **all 43** |
| Title line | "Lampiran 8. Contoh RPS" still at the top of the document | most files |

I checked the raw XML, so these findings do not come from tracked changes or hidden text. The page headers (identity, deskripsi, CPL, CPMK, penilaian table) are usually well written and specific to each course. The bottom half of each RPS (weekly plan, rubric and RTM) still has to be written.

---

## 2. Per-course results (Tabel 7 order)

Legend: ✔ matches Tabel 7 · ✘ mismatch · "Leftover" = SNA/Web template schedule · "Empty" = blank schedule

| # | Kode | Mata Kuliah | Dosen / File | Sev | Findings |
|---|---|---|---|---|---|
| 1 | INF105 | Pengantar Pemrograman | Slamet | **HIGH** | Schedule empty. **CPL ✘**: the RPS has CPL01, 04 and **08**, but Tabel 7 has CPL01 and 04 only. Rubric and RTM are leftovers |
| 2 | INF100P | Prak. Pengantar Pemrograman | Slamet | **HIGH** | Schedule leftover (week 1 is OOAD text, then SNA). Rubric and RTM leftovers. CPL ✔ |
| 3 | INF106 | Pengantar Teknologi Informasi | Philipus/PTI | **HIGH** | **Kode ✘** (INF104). Schedule leftover. Penilaian table identical to HCI and WPF. CPL ✔ |
| 4 | ENG151 | Bahasa Inggris I | Peter | **HIGH** | **Blank template**: no CPL, CPMK, materi or schedule. Page header says "Prodi S1 Teknik Elektro" |
| 5 | INF107 | Pemrograman Web | Devi | **HIGH** | **Kode ✘** (INF101). **SKS ✘** (2, should be 3). **CPL ✘**: CPL01, 04, 06 instead of CPL02, 04, 06. Schedule leftover |
| 6 | INF107P | Prak. Pemrograman Web | Devi | **HIGH** | **Kode ✘** (INF101). **CPL ✘** (same as #5). Schedule leftover |
| 7 | MAT108 | Kalkulus | Peter (old form) | **HIGH** | Old 2019 form with header "Teknik Elektro" and Kode empty. **SKS ✘** (3, should be 4). CPL-1 and CPL-8 use the old numbering. CPMK and Sub-CPMK descriptions are **blank**. Weekly "bahan kajian" is blank. Rubric is a generic grade table. No RTM |
| 8 | REL100 | Pendidikan Agama | MKDU (pdf) | MEDIUM | Weekly plan is complete. Dated 2022/23. Uses university CPL, not prodi CPL. Program Studi field is empty. No analytic rubric or RTM |
| 9 | INF156 | Algoritma | Slamet | **HIGH** | Schedule empty. CPMK004 is listed twice. Rubric and RTM leftovers. CPL ✔ |
| 10 | INF151 | Basis Data | Devi | MEDIUM | Weekly plan is **genuine** (16 weeks). **SKS ✘** (3, should be 2). The CPMK→CPL column is **blank**. Rubric is the SNA template. RTM is HTML tasks |
| 11 | INF151P | Prak. Basis Data | Devi | **HIGH** | Schedule is a copy of the Basis Data lecture ("Ceramah", TM 2×50') and is not a lab plan. SKS is typed as "1sss". CPMK→CPL is blank. Rubric and RTM leftovers |
| 12 | MAT153 | Aljabar Linier | Peter (old form) | **HIGH** | Same skeleton as Kalkulus. **SKS ✘** (3, should be 4). CPL and CPMK are blank. **No pustaka** |
| 13 | INF157 | Interaksi Manusia-Komputer | Philipus/HCI | **HIGH** | **Kode ✘** (INF305). Schedule leftover. CPL ✔ |
| 14 | INF154 | Matematika Diskrit | Peter | **HIGH** | **Blank template** (2 copies) |
| 15 | INF158 | Sistem Digital | Slamet | **HIGH** | Schedule empty. Rubric and RTM leftovers. CPL ✔ |
| 16 | INF200 | Analisa dan Desain Sistem | Philipus | **HIGH** | Schedule leftover. CPL ✔ |
| 17 | INF201 | Kecerdasan Buatan | Philipus | **HIGH** | Schedule leftover. There are **two versions** (`Kecerdasan Buatan.docx` and `…2026.docx`) with different CPMK, so you need to pick one. CPL ✔ |
| 18 | INF202 | Arsitektur & Organisasi Komputer | Slamet | **HIGH** | Schedule empty. CPL ✔ |
| 19 | INF206 | Pemrograman Web Lanjut | Devi | **HIGH** | **Kode is empty**. Schedule is a copy of **Basis Data** (SQL/ERD). **CPL ✘**: has an extra CPL04 (Tabel 7 has CPL02 and 06) |
| 20 | MAT230 | Pengantar Probabilitas & Statistik | Peter (.doc 2021) | **HIGH** | Old-curriculum RPS from Oct 2021 using CPL-9, 10 and 14, which do not match CPL01. No Kode. The weekly table is essentially empty. Signatories are the former Kaprodi |
| 21 | INF208 | Pemrograman Berorientasi Obyek | Philipus | **HIGH** | **Kode ✘** (INF152). **SKS ✘** (2, should be 3). Schedule leftover |
| 22 | INF208P | Prak. PBO | Philipus | **HIGH** | **Kode ✘** (INF152P). **CPL ✘**: CPL04 is missing. Schedule leftover |
| 23 | INF250 | Jaringan Komputer | — | **HIGH** | **No RPS** |
| 24 | INF251 | Sistem Operasi | Andrew | **HIGH** | Schedule leftover. Header is good. CPL ✔ |
| 25 | INF253 | ADS Berorientasi Objek | Philipus/OOAD | **HIGH** | Schedule leftover. CPL ✔ |
| 26 | INF254 | Grafika Komputer | Slamet | **HIGH** | Schedule empty. Only 2 CPMK. The "Penilaian" label is broken ("nilaian"). CPL ✔ |
| 27 | INF256 | Rekayasa Perangkat Lunak | Peter (pdf 2025) | MEDIUM | Weekly plan is genuine (weeks 1–16). **Nama MK, Kode and SKS are empty**. Semester says "I". Uses old CPL-1, 2 and 8, but Tabel 7 has CPL02, 04 and 06. Rubric is a generic grade table. No RTM. "Dipersiapkan oleh" has no name |
| 28 | INF257 | Keamanan Data dan Informasi | Andrew | **HIGH** | Schedule leftover. CPL ✔ |
| 29 | ETH100 | Etika Sosial | MKDU | MEDIUM | Weeks 1–16 are complete. 2022/23 edition. No analytic rubric or RTM. PJMK is empty |
| 30 | INF306 | Manajemen Proyek | — | **HIGH** | **No RPS** |
| 31 | INF301 | Pengolahan Citra Digital | Andrew | **HIGH** | Schedule leftover. CPL ✔ |
| 32 | INF302 | Basis Data Lanjut | Devi | **HIGH** | **Kode ✘** (INF151). Schedule is a copy of Basis Data. **CPL ✘**: CPL07 is missing |
| 33 | INF302P | Prak. Basis Data Lanjut | Devi | **HIGH** | **Kode ✘** (INF101). Schedule leftover |
| 34 | INF307 | Komputasi Awan | — | **HIGH** | **No RPS** |
| 35 | INF308 | Pengujian Perangkat Lunak | Andrew + Philipus | **HIGH** | Schedule leftover. **CPL ✘**: CPL09 is missing. There are **two near-identical versions** (Andrew and Philipus "2026"), so you need to decide who owns the course |
| 36 | POL150 | Pendidikan Kewarganegaraan | MKDU | MEDIUM | Weekly plan is complete. 2022/23. Program Studi field is empty. No analytic rubric or RTM |
| 37 | POL153 | Pendidikan Pancasila | MKDU (pdf) | MEDIUM | Placeholders "Prodi S1 ……", "FAKULTAS ……". Tahun Akademik is 2020–2021. No rubric or RTM |
| 38 | INF356 | Pembelajaran Mesin | Andrew | **HIGH** | Schedule leftover. CPL ✔ |
| 39 | INF357 | Pemrograman Perangkat Seluler | Andrew | **HIGH** | **Kode ✘** (INF351). Schedule leftover |
| 40 | INF357P | Prak. Pemrograman Perangkat Seluler | Andrew | **HIGH** | **Kode ✘** (INF351P). Schedule leftover |
| 41 | INF352 | Metodologi Penelitian | — | **HIGH** | **No RPS** |
| 42 | LAN122 | Bahasa Indonesia | Peter | **HIGH** | **Blank template** (2 copies, one named LAN135) |
| 43 | CHE373 | Capstone Design | — | **HIGH** | **No RPS** |
| 44 | INF354 | Internet of Things | Slamet | **HIGH** | Schedule empty. CPL ✔ |
| 45 | INF400 | Kerja Praktik | — | **HIGH** | **No RPS** |
| 46 | ENG451 | Bahasa Inggris II | Peter | **HIGH** | **Blank template** |
| 47 | INF416 | Kewirausahaan dan Desain Inovasi | — | **HIGH** | **No RPS** |
| 48 | INF417 | Keamanan Siber | Peter (pdf 2025) | MEDIUM | Weeks 1–16 are complete. **Kode is empty**. Uses old CPL-2 and 3, and the schedule also cites CPL-4 and 7. The weekly "Bobot" column is empty. Rubric is a generic grade table. No RTM. Pustaka have no year |
| 49 | PHL100 | Filsafat Manusia | MKDU | MEDIUM | Weekly plan has gaps (weeks 13–15 not shown separately). 2022/23. No rubric or RTM |
| 50 | INF402 | Web Mining | Devi | **HIGH** | **The header says "Data Mining" / INF403** and the deskripsi is copied from Data Mining. Schedule leftover |
| 51 | INF403 | Data Mining | Devi | **HIGH** | Schedule leftover. No UTS/UAS column in penilaian. CPL ✔ |
| 52 | INF410 | Design Patterns | Andrew | **HIGH** | Schedule leftover. The penilaian header has "Tugas 1" twice. CPL ✔ |
| 53 | INF411 | Social Network Analysis | Devi | MEDIUM | Schedule weeks 2–16 and the rubric **are** SNA content, but they use CPMK081–084 while the header defines CPMK011–013. Week 1 is web content. RTM is web tasks |
| 54 | INF412 | Pemrosesan Bahasa Alami | Devi | **HIGH** | **CPL ✘**: CPL02 and 06, but Tabel 7 has **CPL03 and 07** (fully different). Schedule leftover |
| 55 | INF406 | Distributed Database | Devi | **HIGH** | **Kode ✘** (INF404). Schedule leftover |
| 56 | INF407 | E-Bisnis Revolution | — | **HIGH** | **No RPS** |
| 57 | INF408 | UI and UX for Mobile Apps | Slamet | **HIGH** | Schedule empty. Semester is "-". CPL ✔ |
| 58 | INF409 | Digital Product Management | — | **HIGH** | **No RPS** |
| 59 | INF420 | Multimedia & Extended Reality | Slamet | **HIGH** | Schedule empty. CPL ✔ |
| 60 | INF455 | Business Intelligence & Analytics | Andrew | **HIGH** | **Kode ✘** (INF451). Schedule leftover. CPL ✔ |
| 61 | INF456 | Big Data Analytics | Philipus/Analisa Data Besar | **HIGH** | **Kode ✘** (INF452). Schedule leftover |
| 62 | INF457 | Special Topics in Data Science | — | **HIGH** | **No RPS** |
| 63 | INF458 | Deep Learning & Adv. Computation | — | **HIGH** | **No RPS** |
| 64 | INF459 | Special Topics in AI | — | **HIGH** | **No RPS** |
| 65 | INF467 | Decision Support Systems | Devi | **HIGH** | **Kode is empty**. Schedule leftover. CPMK are thin (e.g. "memahami tentang MODM") |
| 66 | INF468 | Multi-platform Mobile Programming | Andrew | **HIGH** | Schedule leftover. CPL ✔ |
| 67 | INF469 | Enterprise Resource Planning | — | **HIGH** | **No RPS** |
| 68 | INF470 | Business Intelligence & Analytics | — | (Tabel 7) | Duplicate of #60. See §5 |
| 69 | INF471 | Special Topics in SW Development | — | **HIGH** | **No RPS** |
| 70 | INF454 | Etika dan Profesi | — | **HIGH** | **No RPS** |
| 71 | INF498 | Tugas Akhir | — | **HIGH** | **No RPS** |

---

## 3. Summary by lecturer

| Dosen | RPS files | HIGH | MEDIUM | Main action |
|---|---|---|---|---|
| Andrew | 10 (+10 identical "Copy of") | 10 | 0 | Headers are excellent. Write the weekly plan, rubric and RTM. Fix kode for INF357, INF357P and INF455 |
| Devi | 13 | 11 | 2 | Write the schedule, rubric and RTM. Fix kode (Web, Prak Web, BDL, Prak BDL, DDB, PWL, DSS, Web Mining) and CPL (Web, Prak Web, PWL, BDL, NLP) |
| Philipus | 11 (incl. KB ×2, WPF not in Tabel 7) | 9 | 0 | Write the schedule, rubric and RTM. Fix kode (PTI, HCI, PBO, Prak PBO, Big Data). Pick one KB version and agree with Andrew on Pengujian PL |
| Slamet | 9 | 9 | 0 | The weekly plan is **completely empty** in 8 files. Also write the rubric and RTM |
| Peter / faculty | 25 files | 7 | 7 | Fill in the blank Bahasa/Matdis templates. Migrate Kalkulus, Aljabar, Probstat, RPL and Cyber to the UKWMS template with current CPL |
| Unassigned | — | 16 | — | Assign PJMK and write the RPS from scratch |

---

## 4. Fix checklist for each RPS
1. Remove "Lampiran 8. Contoh RPS" and all SNA and "Front End Web Programming" content.
2. **Rencana mingguan**: write 16 rows (UTS = week 8, UAS = week 16), each with the course's own CPMK IDs, Sub-CPMK, indikator, bentuk asesmen and bobot, materi and pustaka, metode, and TM/BT/BM matching the SKS. For a 1-SKS praktikum, plan 170' of lab work, not "ceramah 2×50'".
3. **Rubrik**: write a rubric for this course's own CPMK (CPMK001…), not the SNA example.
4. **RTM**: write one per Tugas or Proyek in the penilaian table, with the correct MK name, kode, SKS, dosen, Sub-CPMK, deskripsi, luaran, kriteria and bobot, jadwal and rujukan. Bobot must equal the penilaian table.
5. Check that **Kode, SKS and CPL match Tabel 7** (see the ✘ items above). Fill in the CPMK→CPL column. Remove duplicate CPMK rows.
6. Keep only one final file per course. Delete the "Copy of …" files and the docx/pdf twins, or move them to an archive folder.

## 5. Tabel 7 itself needs correction
- **INF455 and INF470 are both "Business Intelligence and Analytics"**, with different CPL.
- **INF417 Keamanan Siber has no CPL ticked.** A core technical course should carry at least one CPL. The same applies to INF352 Metodologi Penelitian.
- **CHE373 Capstone Design** uses a non-INF code prefix (CHE = Teknik Kimia?). Please confirm.
- The SUB-TOTAL and TOTAL rows are empty.
- **Web Programming Framework (INF255, Philipus)** has an RPS but is **not in Tabel 7**. Either add it or archive the RPS.
- Codes used inside RPS files (INF101, INF104, INF152, INF305, INF351, INF404, INF451, INF452) look like older-curriculum codes. Decide which list is official and apply it consistently.

## 6. Priority order
1. **Unassigned courses (16)**: assign PJMK now. Start with core and early-semester courses: Jaringan Komputer, Manajemen Proyek, Metodologi Penelitian, Kerja Praktik, Capstone, Tugas Akhir, Etika dan Profesi.
2. **Blank or old-form courses (7)**: Bahasa Inggris I/II, Bahasa Indonesia, Matematika Diskrit, Kalkulus, Aljabar Linier, Probstat.
3. **Courses where only the bottom half is missing (38)**: the header is already done, so this is the fastest gain per hour.
4. **MEDIUM (9)**: add rubrics and RTM, and update identity and CPL.
