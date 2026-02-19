# 🐳 Inventory Docker Compose

Proyecto backend con **Docker Compose** para orquestar microservicios (autenticación, productos y administración).

---

## 📥 Clonar el repositorio

```bash
git clone https://github.com/isacmdev/inventory-docker.git
cd inventory-docker

🚀 Docker Compose

Levantar y reconstruir servicios
docker-compose up -d --build
Detener servicios
docker-compose down


📂 Estructura del proyecto
.
├── docker-compose.yml
├── dockerfile.storelogin
├── dockerfile.products
├── dockerfile.administration
└── .env


Archivo	Descripción
docker-compose.yml	Orquestación de servicios Docker
dockerfile.storelogin	Dockerfile del servicio de autenticación
dockerfile.products	Dockerfile del servicio de productos
dockerfile.administration	Dockerfile del servicio de administración

🔐 Variable de entorno JWT_SECRET
Debes crear un archivo .env en la raíz del proyecto con la variable JWT_SECRET.

No subas .env al repositorio. Agregar a .gitignore.

🪟 PowerShell (Windows)
"JWT_SECRET=$([Convert]::ToBase64String((1..32 | % {Get-Random -Max 256})))" | Set-Content .env

🐧 Linux / 🍎 macOS
echo "JWT_SECRET=$(openssl rand -base64 32)" > .env

Alternativa (urandom)
echo "JWT_SECRET=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1 | base64)" > .env
