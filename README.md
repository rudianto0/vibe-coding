# VibeCoding

API backend menggunakan .NET Core dengan PostgreSQL.

## Tech Stack

| Komponen     | Teknologi                        |
|-------------|----------------------------------|
| Framework   | .NET 10 Web API                  |
| Database    | PostgreSQL                       |
| ORM         | Entity Framework Core (LINQ)     |
| Dokumentasi | Swagger / OpenAPI                |

## Struktur Project

```
MyApi/
├── Controllers/        # API endpoints
├── Data/               # DbContext & konfigurasi database
├── Models/             # Entity models
├── Migrations/         # EF Core migrations
├── Program.cs          # Entry point
└── appsettings.json    # Konfigurasi (connection string, dll)
```

## Menjalankan Project

### Prasyarat
- [.NET 10 SDK](https://dotnet.microsoft.com/download)
- [PostgreSQL](https://www.postgresql.org/download/)

### Setup

```bash
# Clone repository
git clone https://github.com/rudianto0/vibe-coding.git
cd vibe-coding

# Restore packages
dotnet restore MyApi.slnx

# Sesuaikan connection string di MyApi/appsettings.json

# Jalankan migration
dotnet-ef database update --project MyApi\MyApi.csproj

# Jalankan API
dotnet run --project MyApi\MyApi.csproj
```

API berjalan di `https://localhost:5001`, dokumentasi Swagger di `https://localhost:5001/swagger`.

---

## Fitur

### Users API
| Method   | Endpoint         | Deskripsi              |
|----------|------------------|------------------------|
| `GET`    | `/api/users`     | Ambil semua user       |
| `GET`    | `/api/users/{id}`| Ambil user by ID       |
| `POST`   | `/api/users`     | Tambah user baru       |
| `PUT`    | `/api/users/{id}`| Update user            |
| `DELETE` | `/api/users/{id}`| Hapus user             |

### Entity: User
| Field | Type   | Deskripsi    |
|-------|--------|-------------|
| Id    | int    | Primary key |
| Name  | string | Nama user   |
| Email | string | Email user  |

---

## Catatan
README ini akan di-update setiap ada penambahan fitur baru. Tambahkan endpoint, entity, atau konfigurasi baru di bagian **Fitur** di atas.
