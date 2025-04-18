
# TreinamentoDocker
Treinamento em Docker e Kubernetes

# Ambiente Docker - WordPress + OwnCloud + MySQL + phpMyAdmin

Este projeto utiliza **Docker Compose** para criar rapidamente um ambiente completo com:

- MySQL 5.7 (Banco de Dados)
- WordPress (Gerenciamento de conteúdo on line)
- phpMyAdmin (Administração do mySQL)
- OwnCloud (Armazenamento de Arquivos)

---

## Como usar

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/edumqes/TreinamentoDocker
   cd TreinamentoDocker
   ```

2. **Suba os containers:**
   ```bash
   docker-compose up -d
   ```

3. **Acesse os serviços:**

| Serviço      | URL                   |
|--------------|------------------------|
| WordPress    | http://localhost:8081  |
| phpMyAdmin   | http://localhost:8080  |
| OwnCloud     | http://localhost:8082  |

---

## Configurações importantes

### uploads.ini

O arquivo `uploads.ini` é montado dentro do container do WordPress e aumenta os limites de upload:

```ini
file_uploads = on
memory_limit = 256M
upload_max_filesize = 256M
post_max_size = 300M
max_execution_time = 600
```

---

## Persistência de Dados

O projeto utiliza volumes nomeados para manter dados mesmo após reiniciar os containers:

- `vol-db` → dados do MySQL
- `vol-html` → arquivos do WordPress
- `vol-conf` → configs PHP do WordPress
- `vol-apps`, `vol-data` → dados do OwnCloud

---

## Testado em

- Docker 28.0.4
- Docker Compose 2.35.0
- Arch Linux
- Windows 11 (necessário instalar WSL e Docker Desktop)

---

## Autor

Eduardo Marques

---

## Licença

Este projeto é livre para uso em treinamentos e ambientes de testes.
