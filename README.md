# 📚 EduConnect

> A collaborative, scalable, and modern web platform for students and university learners.  
> Features: global & private discussion forums, free & paid courses, educational events, real-time chat, dynamic dataset uploads, and educational news.

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
