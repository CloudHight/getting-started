# Getting Started — Simple Node CRUD App

A minimal Node.js + Express sample application with a small static frontend.  
Provides REST routes for create/read/update/delete and two persistence backends (SQLite for local/dev and MySQL for production).

## Features
- REST endpoints: addItem, getItems, updateItem, deleteItem
- Persistence adapters: SQLite (default) and MySQL
- Small static frontend located in `src/static`
- Unit tests under `app/spec`

## Prerequisites
- Node.js 14+ (recommended)
- npm
- For MySQL usage: a running MySQL server and credentials

## Quickstart (local / SQLite)
1. Open a terminal (Mac):
   cd /path/to/getting-started/app
2. Install:
   npm install
3. Start the app:
   npm start
4. Visit:
   http://localhost:3000 (or the port printed by the server)

## Use MySQL instead of SQLite
Set environment variables before starting the server:
- MYSQL_HOST
- MYSQL_PORT (optional, default 3306)
- MYSQL_USER
- MYSQL_PASSWORD
- MYSQL_DATABASE
- USE_MYSQL=true

Example (macOS / Linux):
export MYSQL_HOST=127.0.0.1
export MYSQL_USER=myuser
export MYSQL_PASSWORD=mypass
export MYSQL_DATABASE=mydb
export USE_MYSQL=true
npm start

The app will use the MySQL adapter in `src/persistence/mysql.js` when `USE_MYSQL` is truthy.

## Tests
Run unit tests (uses SQLite by default):
cd app
npm test

Tests live in `app/spec`:
- `spec/routes/*` — route tests
- `spec/persistence/*` — persistence adapter tests

## Project layout (important files)
- app/src/index.js — server entrypoint
- app/src/routes/* — route handlers
- app/src/persistence/sqlite.js — SQLite adapter
- app/src/persistence/mysql.js — MySQL adapter
- app/src/static — frontend assets
- app/spec — tests

## Notes
- The SQLite DB is file-based and suitable for development only.
- When adding a production DB, ensure correct network/security settings for MySQL.
- Adjust the port and other settings in `app/src/index.js` if needed.

## License
This project is provided under the repository LICENSE file.
