# Diksuchi × Supabase Integration Documentation

## Overview

Diksuchi EdTech integrates **Supabase** as the primary backend platform for powering authentication, databases, storage, and real-time features across learning programs and **Diksuchi BuildExpo Hackathons**.

This integration enables students, developers, and hackathon participants to build **production-ready full-stack applications** quickly using Supabase’s open-source backend-as-a-service.

---

## Why Supabase at Diksuchi?

Supabase is used at Diksuchi to:

* Enable **quick backend setup** for learners
* Provide **secure authentication** for apps and dashboards
* Power **PostgreSQL databases** for real-world data modeling
* Store project files, assets, and submissions
* Enable **real-time collaboration** in hackathon projects
* Teach industry-standard backend workflows

---

## Supported Supabase Features

Diksuchi uses and recommends the following Supabase features:

### 🔐 Authentication

* Email & password authentication
* Magic link authentication
* OAuth (Google, GitHub – optional)
* Role-based access for teams and mentors

### 🗄️ Database (PostgreSQL)

* Project data storage
* Hackathon submissions
* Team management
* User profiles and roles
* Learning progress tracking

### 📦 Storage

* Project assets
* Design exports
* Pitch decks
* Screenshots and demo files

### ⚡ Realtime

* Live team updates
* Collaboration status
* Hackathon activity feeds
* Real-time dashboards

---

## Architecture Overview

Typical Diksuchi project architecture using Supabase:

```
Frontend (Next.js / React)
        ↓
Supabase Client SDK
        ↓
Supabase Services
- Auth
- PostgreSQL Database
- Storage
- Realtime
```

Supabase acts as the backend layer, while learners focus on frontend development and product logic.

---

## Getting Started

### Step 1: Create a Supabase Project

1. Visit [https://supabase.com](https://supabase.com)
2. Create a new project
3. Copy your:

   * Project URL
   * Anon Public API Key

---

### Step 2: Install Supabase Client

For JavaScript / Next.js projects:

```bash
npm install @supabase/supabase-js
```

---

### Step 3: Initialize Supabase Client

```js
import { createClient } from '@supabase/supabase-js'

const supabaseUrl = process.env.NEXT_PUBLIC_SUPABASE_URL
const supabaseAnonKey = process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY

export const supabase = createClient(
  supabaseUrl,
  supabaseAnonKey
)
```

---

## Authentication Setup

### Email Authentication Example

```js
const { data, error } = await supabase.auth.signUp({
  email: 'user@example.com',
  password: 'securepassword'
})
```

Used for:

* Student login
* Hackathon participant access
* Admin & mentor dashboards

---

## Database Usage Example

Creating a table (example: projects):

```sql
create table projects (
  id uuid primary key default uuid_generate_v4(),
  title text,
  description text,
  user_id uuid,
  created_at timestamp default now()
);
```

Used for:

* Hackathon projects
* Student portfolios
* MVP tracking

---

## Storage Usage

Uploading project assets:

```js
await supabase.storage
  .from('project-assets')
  .upload('demo.png', file)
```

Used for:

* Screenshots
* Demo files
* Pitch materials

---

## Realtime Example

Listening to project updates:

```js
supabase
  .channel('projects')
  .on('postgres_changes', { event: '*', schema: 'public', table: 'projects' }, payload => {
    console.log(payload)
  })
  .subscribe()
```

Used in:

* Live hackathon dashboards
* Mentor review panels

---

## Use Cases at Diksuchi

* 🚀 BuildExpo Hackathon project backend
* 🎓 Student learning applications
* 🧪 MVP validation for early-stage startups
* 📂 Portfolio-ready full-stack apps
* 👥 Team collaboration platforms

---

## Security Best Practices

* Use **Row Level Security (RLS)** for all tables
* Never expose service role keys to frontend
* Use environment variables for keys
* Enable email verification for auth

---

## Learning & Hackathon Templates

Diksuchi provides Supabase-powered starter templates for:

* Next.js + Supabase Auth
* Hackathon submission systems
* Portfolio platforms
* Admin dashboards

(Templates shared during programs & hackathons.)

---

## Support & Resources

* Supabase Docs: [https://supabase.com/docs](https://supabase.com/docs)
* Diksuchi Programs: [https://diksuchi.com](https://diksuchi.com)
* Community Support: [https://github.com/diksuchi](https://github.com/diksuchi)

---

## Partnership Note

Diksuchi actively promotes Supabase across:

* Hackathons
* Workshops
* Learning modules
* Community challenges

This integration helps onboard the **next generation of developers and founders** to Supabase.
