# Atualizando o Fork

## Setup inicial (só 1 vez)

```bash
cd ~/Desktop/@dev/wuzapi
git remote add upstream https://github.com/asternic/wuzapi.git
```

## Atualizar com o repositório original

```bash
cd ~/Desktop/@dev/wuzapi

# Puxar e mergear atualizações
git fetch upstream
git merge upstream/main

# Se houver conflito em handlers.go, resolver e commitar

# Push pro fork
git push origin main
```

## Deploy no VPS

```bash
cd /home/codewo/wuzapi

# Rebuild da imagem com as atualizações
docker build -t wuzapi-custom https://github.com/dumilani/wuzapi.git

# Restart do container
docker compose down && docker compose up -d

# Verificar logs
docker logs wuzapi --tail 20
```
