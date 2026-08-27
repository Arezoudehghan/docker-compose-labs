# Docker Compose Labs

[![Validate Docker Compose Labs](https://github.com/Arezoudehghan/docker-compose-labs/actions/workflows/validate.yml/badge.svg)](https://github.com/Arezoudehghan/docker-compose-labs/actions/workflows/validate.yml)

A structured collection of hands-on Docker Compose labs designed for a two-VM DevOps learning environment.

## Lab environment

| Host | Address | Primary role |
|---|---|---|
| `DEV-1` | `192.0.2.10` | Build, GitLab, Runner, Nexus, and client tests |
| `DEV-2` | `192.0.2.11` | Deploy, Docker Compose, and monitoring |

> `192.0.2.10` and `192.0.2.11` are documentation-only example addresses. Replace them with the addresses assigned to your own lab VMs.

## Available sessions

| Session | Topic | Lab directory | Execution host |
|---|---|---|---|
| 36 | Docker Compose networks | [`session-36-networks`](session-36-networks/) | `DEV-1` |
| 37 | `depends_on` and restart policy | [`session-37-depends-on-restart`](session-37-depends-on-restart/) | `DEV-2` |

Each session is isolated in its own directory and contains its own Compose file, safe environment example, documentation, troubleshooting guide, interview questions, and verification scripts.

## Clone the repository

```bash
git clone https://github.com/Arezoudehghan/docker-compose-labs.git
cd docker-compose-labs
```

Then enter the directory for the session you want to run and follow its `README.md`.

## Repository rules

- Never commit a real `.env` file.
- Use `.env.example` only as a safe template.
- Run `docker compose config --quiet` before starting a lab.
- Do not run two labs on the same host when they publish the same host port.
- Read the cleanup warning before using `docker compose down -v`.

## Automated validation

GitHub Actions validates both Compose labs on every push to `main` and on every pull request. The workflow also checks shell-script syntax, builds the images used by Session 36, and pulls the pinned images used by Session 37.

## License

This repository is licensed under the [MIT License](LICENSE).

## Scope

These projects are educational labs. Production deployments also require organization-specific secrets management, TLS, access control, monitoring, backup, resource limits, and change-management procedures.
