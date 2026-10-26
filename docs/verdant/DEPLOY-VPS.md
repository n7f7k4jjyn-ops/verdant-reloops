# Implantacao na VPS Hostinger

O Reloops upstream executa app + Supabase via Docker Compose e foi documentado para localhost.
Antes de publicar: configure proxy reverso HTTPS, URLs publicas do frontend e Supabase,
redirects de autenticacao, volumes persistentes e backups. Nao exponha as portas
internas 56321, 56322 e 56323 diretamente a Internet.

## Inicializacao de teste (acesso local apenas)
```bash
git clone https://github.com/n7f7k4jjyn-ops/verdant-reloops.git
cd verdant-reloops
docker compose up -d --build --wait --wait-timeout 600
docker compose ps
curl -fsS http://127.0.0.1:6173/healthz
```

Consulte docs/SETUP.md e docs/TESTING.md para validar o ambiente antes da publicacao.
