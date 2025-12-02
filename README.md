# Demo

Schone demo-omgeving voor nieuwe klantprojecten.

## Server Info

| Item | Waarde |
|------|--------|
| URL | https://demo.havun.nl |
| Database | demo_staging |
| DB User | demo |
| Git deploy | `git push staging main` |

## Setup

```bash
# Staging remote toevoegen
git remote add staging root@188.245.159.115:/var/www/demo/repo.git

# Deploy
git push staging main
```
