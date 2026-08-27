# Security Notes

- Do not commit the real `.env` file.
- Replace the example PostgreSQL password before running the lab.
- PostgreSQL port `5432` is intentionally not published on the Docker host.
- Adminer is a lab administration tool and must not be exposed to the public internet.
- If UFW is active on `DEV-2`, allow TCP `8086` only from `192.168.94.90`.
- Back up `db_data` before any destructive volume operation.

The following command permanently deletes the PostgreSQL volume:

```bash
docker compose down -v
```
