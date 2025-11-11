# 🐝 Budget Bees DB

A simple and efficient database management project for **Budget Bees**, built using **Gradle**.  
This project automates build, update, and rollback operations to keep your database migrations clean and consistent.

---

## 🧱 Project Setup


## ⚙️ Build the Project

Clean and build the project with Gradle:

```bash
./gradlew clean build
```

This will compile the project, run tests, and prepare all necessary build artifacts.

---

## 🔄 Database Migrations

### Update the Database
To apply the latest migration scripts to your database:

```bash
./gradlew update
```

---

### Rollback Changes
To revert the most recent database migration:

```bash
./gradlew rollbackCount
```

> **Note:**  
> `rollbackCount` is set to **rollback one change at a time**.  
> Run the command multiple times to roll back additional versions incrementally.

---

## 🧩 Tips
- Always run `./gradlew clean build` before applying or rolling back migrations.
- Keep your migration scripts organized in the `resources/db/migration` directory.
- Use version control to track all migration and rollback changes.

---

## 🐝 License
This project is licensed under the [MIT License](LICENSE).

---

### 💬 About
Budget Bees DB is part of the **Budget Bees** suite — lightweight tools for personal budgeting.
