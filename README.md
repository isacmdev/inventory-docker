## 🐳 Inventory Docker Compose

Este proyecto usa Docker Compose para orquestar múltiples microservicios backend.

---

## 📥 Clonar el repositorio

```bash
git clone https://github.com/isacmdev/inventory-docker.git
cd inventory-docker


- **Reconstruir y levantar en un solo comando:**

  docker compose up -d --build
  ```
## 📂 Estructura del proyecto
.
├── docker-compose.yml
├── dockerfile.storelogin
├── dockerfile.products
├── dockerfile.administration
└── .env

## ArchivoDescripción
docker-compose.yml	Orquestación de servicios
dockerfile.storelogin	Servicio de autenticación de tiendas
dockerfile.products	Servicio CRUD de productos
dockerfile.administration	Servicio de administración
🔐 Variable de entorno JWT_SECRET

### PowerShell (Windows)

```powershell
"JWT_SECRET=$([Convert]::ToBase64String((1..32 | % {Get-Random -Max 256})))" | Set-Content .env
```

```bash
Linux / macOS
echo "JWT_SECRET=$(openssl rand -base64 32)" > .env
```

```bash
Alternativa (urandom)
echo "JWT_SECRET=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1 |
```