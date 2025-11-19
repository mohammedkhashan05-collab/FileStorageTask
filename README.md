# File Storage & Document Management

A file storage system built with ASP.NET Core 8 and Angular 17.

## Features

- File upload, download, and preview
- User authentication with JWT
- File search and pagination
- Soft and hard delete
- Image and PDF preview

## Setup

### Backend

```bash
cd Backend
dotnet restore
cd src/FileStorage.API
dotnet ef database update --project ../FileStorage.Infrastructure
dotnet run
```

### Frontend

```bash
cd Frontend
npm install
npm start
```

## Default Users

- Username: `admin` (role: admin)
- Username: `user` (role: user)
- Password: any password works for demo

## API Endpoints

- `POST /api/auth/login` - Login
- `POST /api/files` - Upload file
- `GET /api/files` - List files
- `GET /api/files/{id}/download` - Download file
- `GET /api/files/{id}/preview` - Preview file
- `DELETE /api/files/{id}` - Soft delete
- `DELETE /api/files/{id}/hard` - Hard delete (admin only)
"# FileStorageTask" 
