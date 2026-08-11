# Reference: Database Setup

> Confirm current version-specific syntax/defaults against the chosen
> database's official docs (PostgreSQL, MySQL, MongoDB, etc.).

## 1. Purpose
General guidance for choosing, installing, configuring, securing, and
validating a database for an application — relational (PostgreSQL, MySQL/
MariaDB) or non-relational (MongoDB, Redis, etc.).

## 2. When to use it
- Any application needs persistent structured (or semi-structured) data
  storage beyond simple flat files.

## 3. When NOT to use it
- Very small/simple apps with minimal, non-critical data may be fine with
  flat files (JSON/SQLite) — don't over-engineer with a full DB server
  unless the workload justifies it.

## 4. Requirements
- Server/host to run the database (or a managed database service).
- Sufficient disk space and RAM for expected data volume and query load.
- A plan for backups from day one, not as an afterthought.

## 5. Setup overview
1. Choose engine type based on data shape and query needs (relational
   for structured/relational data with transactions; document store for
   flexible schemas; key-value/cache like Redis for ephemeral/fast-access
   data).
2. Choose self-hosted (on the same VPS, or a dedicated DB server) vs.
   managed database service, weighing maintenance burden against cost.
3. Install the database engine (or provision the managed instance).
4. Create a dedicated database and a least-privilege application user
   (not the admin/root DB user) for the app to connect with.
5. Store connection credentials via environment variables — never
   hardcoded in application code.
6. Configure network access: bind to localhost only unless remote access
   is genuinely required; if remote access is needed, restrict by
   IP allowlist and require TLS where supported.
7. Set up automated backups (e.g. daily dumps, or the managed service's
   backup feature) and periodically test restoring from one.

## 6. Key configuration concepts
- Connection pooling matters once the app has meaningful concurrent
  traffic — plan for it before it becomes a bottleneck, not after.
- Indexes: added based on actual query patterns, not preemptively on
  every column.
- Migrations: use a migration tool/framework appropriate to the stack
  rather than manual ad hoc schema edits, once the schema needs to
  evolve over time.

## 7. Validation
- App can connect using the dedicated application user (not admin).
- Basic CRUD operation succeeds end-to-end from the app.
- Database survives a service/server restart with data intact.
- A backup file/snapshot exists and a test restore has been verified at
  least once.
- Database is not reachable from the public internet unless explicitly
  required and secured.

## 8. Common errors
- Connection refused: database not running, wrong host/port, or bound to
  localhost when the app expects a remote connection (or vice versa).
- Authentication failed: wrong credentials, or user lacks privileges on
  the target database.
- "Too many connections": connection pool not configured / connections
  not being closed properly in the app.
- Disk full: no rotation/cleanup of logs or old data, or backups
  accumulating unmanaged.

## 9. Troubleshooting
- Confirm the database service is actually running before debugging the
  app's connection logic (`systemctl status <db>` or equivalent).
- Check the database's own logs for the specific rejection reason before
  guessing.
- Isolate whether the issue is network-level (can't reach the port) or
  application-level (reaches the port but auth/query fails).

## 10. Security considerations
- Least-privilege application DB user; never have the app connect as the
  database superuser.
- No direct public exposure of the database port unless firewalled to
  specific IPs and using TLS.
- Store credentials via environment variables / secret manager; exclude
  any local `.env` from version control.
- Before any `DROP DATABASE`, `TRUNCATE`, or bulk delete, confirm a
  recent backup exists and warn the user explicitly.

## 11. Cost considerations
- Self-hosted: cost is the server it runs on plus your time for
  maintenance/backups.
- Managed service: higher direct cost, lower operational burden — weigh
  against team size/expertise and how critical uptime is.

## 12. Maintenance
- Regular backups (automated) with periodic restore tests.
- Monitor disk usage and query performance as data grows.
- Apply security patches for the database engine promptly.

## 13. Upgrade / scaling considerations
- Vertical scaling (bigger instance) first for most small/medium apps.
- Read replicas, sharding, or managed scaling features only once there's
  actual evidence of load justifying the added complexity.
