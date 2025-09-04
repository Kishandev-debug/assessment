# School App (Next.js + MySQL)

Two pages:
- `addSchool.jsx`: Form with validation (react-hook-form) + image upload to `public/schoolImages`
- `showSchools.jsx`: Grid cards list (name, address, city, image)

## Tech
Next.js (Pages Router), TailwindCSS, MySQL (mysql2), formidable for uploads.

## Setup

1) Install
```bash
npm install
```

2) Create DB & table
```sql
CREATE DATABASE IF NOT EXISTS schooldb;
USE schooldb;
CREATE TABLE IF NOT EXISTS schools (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name TEXT,
  address TEXT,
  city TEXT,
  state TEXT,
  contact VARCHAR(20),
  image TEXT,
  email_id TEXT
);
```

3) Configure environment
Copy `.env.example` to `.env.local` and set DB credentials.

4) Run locally
```bash
npm run dev
```

Open http://localhost:3000
- Add: http://localhost:3000/addSchool
- View: http://localhost:3000/showSchools

## Notes on Hosting
- For persistent image uploads, host on a server with writeable disk (e.g., Render, Railway, VPS). 
  Vercel/Netlify file systems are ephemeral; images may not persist across deploys. This project
  saves images to `public/schoolImages` to match assignment requirements.

## Folder Structure
- `pages/addSchool.jsx`
- `pages/showSchools.jsx`
- `pages/api/addSchool.js`
- `pages/api/getSchools.js`
- `lib/db.js`
- `public/schoolImages/`
- `styles/globals.css`
- `schema.sql` (table schema)
- `.env.example`

## Validation
- Email regex
- Contact number digits (7–15)
- Required fields

## Credits
Built for assessment submission.