# Duplicate Killer (`spoonart-duplicate-killer`)

**Duplicate Killer** adalah *meta-engineering skill* yang dirancang untuk mengaudit, menganalisis, dan mengeliminasi instruksi atau skill yang terduplikasi dan saling tumpang tindih (*overlapping*) pada sistem multi-agent (seperti Google Antigravity, Cursor, Claude Code, dan AI agent frameworks lainnya).

---

## 🎯 Tujuan Utama

- **Menghemat Token Context Window:** Mengurangi overhead token instruksi hingga 40%–70% dengan memangkas aturan berulang pada system prompt.
- **Mencegah Tabrakan Instruksi (*Instruction Collision*):** Menghilangkan konflik aturan antar-skill yang memicu kebingungan model (*hesitation*), output non-deterministik, atau halusinasi.
- **Konsolidasi Skill Tanpa Kehilangan Informasi (*Lossless Consolidation*):** Menggabungkan beberapa skill domain yang terfragmentasi menjadi satu *master skill* berdensitas tinggi dengan tetap mempertahankan seluruh batasan teknis, regex, konfigurasi, dan edge cases penting.

---

## 🔍 Analisis 4-Dimensi Redundansi

Skill ini mengevaluasi duplikasi instruksi berdasarkan 4 aspek:
1. **Lexical & Semantic Redundancy:** Membandingkan daftar kata terlarang (*banned words*), panduan gaya penulisan, nada bicara (*tone*), dan format output.
2. **Constraint & Threshold Duplication:** Mendeteksi batasan teknis, aturan performa, atau validasi yang secara fungsional identik.
3. **Tool & Resource Redundancy:** Memeriksa deklarasi MCP tools, perintah CLI, skrip pendukung, atau API wrapper yang duplikat.
4. **Artifact Output Overlap:** Mengidentifikasi skill yang menghasilkan skema output atau tipe berkas yang sama.

---

## ⚡ Protokol Eksekusi 5 Langkah

```
[1. SCAN & PROFILE] ──► [2. PAIRWISE MATRIX] ──► [3. AUDIT REPORT (GATE)]
                                                           │
                                                           ▼ (User Approval)
[5. VERIFY & CLEAN] ◄── [4. LOSSLESS MERGE] ◄──────────────┘
```

1. **Scan & Token Profile:** Memindai file skill (`SKILL.md`, rules) dan mengestimasi beban token per turn.
2. **Pairwise Comparison Matrix:** Mengelompokkan skill ke dalam kategori domain dan menghitung persentase tumpang tindih (*Overlap Ratio*). Klaster dengan rasio $\ge 50\%$ ditandai untuk konsolidasi.
3. **Pre-Merge Audit Report (Mandatory Gate):** Menyajikan laporan audit transparan kepada pengguna sebelum melakukan modifikasi berkas apa pun.
4. **Lossless Synthesis Engine:** Mensintesis *master skill* berdensitas tinggi dengan membuang basa-basi/filler tanpa mengurangi fakta konkret.
5. **Agent Rebinding & Verification:** Memperbarui konfigurasi agent ke *master skill* baru serta mengarsipkan skill lama yang redundan.

---

## 📁 Direktori & Berkas

- [spoonart-duplicate-killer/SKILL.md](file:///Volumes/Work/skills-collection/spoonart-duplicate-killer/SKILL.md) : Spesifikasi dan protokol lengkap skill.
