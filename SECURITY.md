# Security Policy

## Safe lab usage

- Never commit real `.env` files, passwords, tokens, certificates, or private keys.
- Keep database and cache ports internal unless external access is explicitly required.
- Restrict published lab ports with the host firewall when the server is reachable by other networks.
- Pin container image versions and review image updates before deployment.
- Back up named volumes before destructive cleanup.
- Do not expose Adminer to the public internet.

## Destructive cleanup

The following command deletes named volumes and their stored data for the selected session:

```bash
docker compose down -v
```

Use it only when permanent data removal is intended.

## Reporting

This is a private educational repository. Report security findings directly to the repository owner.
