# 💡 IdeaBox

IdeaBox is a simple Laravel-based web application that allows users to submit ideas, vote on them, and comment. It’s designed for educational and practice purposes, focusing on Laravel fundamentals like Blade templates, Eloquent models, authentication, and relational database management.

---

## 🚀 Features

-   User registration and login
-   Submit new ideas
-   View ideas by status and category
-   Vote for ideas (one vote per idea per user)
-   Comment on ideas
-   Admin panel to update idea statuses (e.g. In Progress, Rejected)
-   Filter ideas by popularity or status
-   Responsive UI using Blade and Tailwind CSS

---

## 📦 Technologies Used

-   Laravel 11
-   Laravel Breeze (authentication)
-   Blade templating engine
-   Eloquent ORM
-   MySQL or SQLite
-   Tailwind CSS (for styling)

---

## 🧱 Database Structure

### `users`

|      Field | Type      | Description           |
| ---------: | --------- | --------------------- |
|         id | BIGINT    | Primary key           |
|       name | VARCHAR   | Full name of the user |
|      email | VARCHAR   | Unique email          |
|   password | VARCHAR   | Hashed password       |
| created_at | TIMESTAMP | Creation timestamp    |
| updated_at | TIMESTAMP | Last update timestamp |

### `ideas`

|       Field | Type      | Description                                |
| ----------: | --------- | ------------------------------------------ |
|          id | BIGINT    | Primary key                                |
|       title | VARCHAR   | Short title of the idea                    |
| description | TEXT      | Full description of the idea               |
|    category | VARCHAR   | E.g., Tech, UI, Marketing                  |
|      status | ENUM      | proposed, in_progress, completed, rejected |
|     user_id | BIGINT    | Foreign key linked to users                |
|  created_at | TIMESTAMP | Creation timestamp                         |
|  updated_at | TIMESTAMP | Last update timestamp                      |

### `votes`

|      Field | Type      | Description                 |
| ---------: | --------- | --------------------------- |
|         id | BIGINT    | Primary key                 |
|    user_id | BIGINT    | Foreign key linked to users |
|    idea_id | BIGINT    | Foreign key linked to ideas |
| created_at | TIMESTAMP | Vote timestamp              |
| updated_at | TIMESTAMP | Update timestamp            |

### `comments`

|      Field | Type      | Description                 |
| ---------: | --------- | --------------------------- |
|         id | BIGINT    | Primary key                 |
|    idea_id | BIGINT    | Foreign key linked to ideas |
|    user_id | BIGINT    | Foreign key linked to users |
|       body | TEXT      | Content of the comment      |
| created_at | TIMESTAMP | Creation timestamp          |
| updated_at | TIMESTAMP | Update timestamp            |

---

## ⚙️ Installation Guide

1. **Clone the repository**

```bash
git clone https://github.com/your-username/ideabox.git
cd ideabox
```

2. **Install dependencies**

```bash
composer install
npm install && npm run dev
```

3. **Configure the environment**

```bash
cp .env.example .env
php artisan key:generate
```

4. **Update `.env` database settings** and then run migrations:

```bash
php artisan migrate
```

5. **Seed optional demo data** (if available)

```bash
php artisan db:seed
```

6. **Run the local development server**

```bash
php artisan serve
```

Then go to [http://localhost:8000](http://localhost:8000)

---

## 🧑‍💻 User Roles

-   **Regular User**: can submit ideas, vote, and comment.
-   **Admin**: can view all ideas and update their status (`in_progress`, `completed`, `rejected`).

---

## 📅 Project Timeline (Gantt Overview)

| Task                              | Duration | Start Day | End Day |
| --------------------------------- | -------- | --------- | ------- |
| Laravel project setup             | 1 day    | Day 1     | Day 1   |
| Models and migrations             | 1 day    | Day 2     | Day 2   |
| Auth with Laravel Breeze          | 1 day    | Day 3     | Day 3   |
| CRUD for ideas                    | 2 days   | Day 4     | Day 5   |
| Voting system                     | 1 day    | Day 6     | Day 6   |
| Comment system                    | 1 day    | Day 7     | Day 7   |
| Filtering and idea listing        | 1 day    | Day 8     | Day 8   |
| Admin interface (status workflow) | 1 day    | Day 9     | Day 9   |
| UI/UX polishing with Blade & CSS  | 2 days   | Day 10    | Day 11  |
| Testing and deployment            | 1 day    | Day 12    | Day 12  |

---

## 📸 Screenshots

_Add screenshots of idea submission, voting, admin panel, etc. once UI is ready._

---

## 📄 License

This project is open-source and licensed under the [MIT License](LICENSE).

---
