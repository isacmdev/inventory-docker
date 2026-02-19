## 🐳 Inventory Docker Compose

Este proyecto usa Docker Compose para orquestar múltiples microservicios backend.

## 📥 Clonar el repositorio
git clone https://github.com/isacmdev/inventory-docker.git
cd inventory-docker

## 🚀 Docker Compose
Construir y levantar los servicios
docker-compose up -d --build

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

## Debes crear un archivo .env en la raíz del proyecto con la variable JWT_SECRET.

PowerShell (Windows)
"JWT_SECRET=$([Convert]::ToBase64String((1..32 | % {Get-Random -Max 256})))" | Set-Content .env

Linux / macOS
echo "JWT_SECRET=$(openssl rand -base64 32)" > .env

Alternativa (urandom)
echo "JWT_SECRET=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1 | base64)" > .env