# 📚 EduConnect

## 📝 Business Idea & Flow

**EduConnect** adalah platform edukasi global yang dirancang khusus untuk pelajar SMA/SMK, mahasiswa, dan komunitas pendidikan di seluruh dunia.  
Aplikasi ini menggabungkan **forum diskusi global & privat**, **kursus online gratis maupun berbayar**, **event edukasi**, **berita pendidikan terkini**, serta **fitur chat real-time** dalam satu ekosistem terpadu yang dapat diakses dari mana saja.

### 🎯 Tujuan Bisnis
- Menjadi pusat informasi dan interaksi bagi pelajar & mahasiswa di seluruh dunia.
- Menyediakan wadah pembelajaran kolaboratif dan berbasis komunitas.
- Menghadirkan peluang monetisasi melalui kursus, event, dan fitur premium.
- Mendukung pendidikan berkelanjutan dengan materi yang mudah diakses dan relevan

![EduConnect Banner](docs/banner.png)

---

## 🌟 Features
- **Forum Diskusi** — Publik & privat, mendukung markdown, gambar, dan lampiran file.
- **Kursus Gratis & Berbayar** — Video, PDF, kuis, sertifikat.
- **Event Edukasi** — RSVP, reminder, berbayar atau gratis.
- **Berita Pendidikan** — Post berita terkini seputar pendidikan.
- **Chat Real-Time** — Personal & grup (Socket.IO).
- **Upload Dataset Dinamis** — Admin upload CSV/XLSX/JSON dan tampilkan tabel interaktif.
- **Panel Admin** — Kelola user, kursus, event, berita, dan data.

---

## 🛠 Tech Stack

### Backend
- **Express.js** + **TypeScript**
- **Drizzle ORM** (`mysql2`, `drizzle-kit`)
- **JWT Auth**
- **Valibot** (validasi)
- **Socket.IO** (real-time)
- **Swagger/OpenAPI** (API docs)

### Frontend
- **Next.js** (React + SSR/SSG)
- **TailwindCSS**
- **shadcn/ui**
- **TanStack Query**
- **Framer Motion**

### Tools & Dev Experience
- **MySQL** ≥5.7
- **ESLint**, **Prettier**, **EditorConfig**
- **Husky** + **lint-staged**
- **Vitest/Jest**
- **Docker** + docker-compose
- **pnpm**

---

## 📈 Business Flow

### User Roles
- **Guest** → Lihat kursus gratis, event publik, berita.
- **Student** → Ikut forum, daftar kursus, ikut event, chat real-time.
- **Instructor** → Buat & kelola kursus.
- **Admin** → Kelola semua konten & data, unggah dataset, lihat analitik.

### Monetization
- Kursus berbayar (revenue split).
- Event berbayar.
- Iklan edukasi.
- Fitur premium.

---

## 📊 Diagram Business Flow
```mermaid
flowchart TD
    A[Guest] -->|Register/Login| B[Student]
    B --> C[Join Forum]
    B --> D[Enroll Kursus]
    B --> E[Join Event]
    B --> F[View Berita]

    C -->|Public/Private Forum| G[Realtime Discussion]
    D -->|Gratis| H[Enroll Success]
    D -->|Berbayar| I[Payment Gateway] --> H
    E -->|Gratis| J[Join Success]
    E -->|Berbayar| I --> J

    B --> K[Realtime Chat]
    Admin[Admin] --> L[Manage Forum]
    Admin --> M[Manage Courses]
    Admin --> N[Manage Events]
    Admin --> O[Manage News]
    Admin --> P[Upload Dataset]
