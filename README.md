# AS241S5_FRI_42

## Docker en Linux Cloud | Contenedor mínimo para Microservicio

## Entorno utilizado
- Plataforma: GitHub Codespaces (Azure)
- Sistema Operativo: Linux Ubuntu 22.04
- Tecnología de contenedor: Docker
- Imagen base: Alpine Linux

## Dockerfile
```dockerfile
FROM alpine:latest
RUN apk add --no-cache busybox-extras
EXPOSE 8080
CMD ["httpd", "-f", "-p", "8080"]
```

## Comandos ejecutados
```bash
# Verificar entorno Linux
uname -a

# Verificar Docker instalado
docker --version

# Construir imagen mínima
docker build -t micro-alpine .

# Ejecutar contenedor
docker run -d -p 8080:8080 --name microservicio micro-alpine

# Ver contenedor corriendo
docker ps

# Ver tamaño de la imagen
docker images

# Ver tamaño exacto en MB
docker image inspect micro-alpine --format='{{.Size}}' | awk '{printf "%.2f MB\n", $1/1024/1024}'

# Ver consumo de recursos
docker stats microservicio --no-stream
```

## Evidencia
- El contenedor corre un servidor HTTP funcional en el puerto 8080
- La imagen Alpine pesa aproximadamente 7MB
- Consume recursos mínimos de CPU y RAM

## Enlace del video
[Docker en Linux Cloud | Contenedor mínimo para Microservicio | GitHub Codespaces](#)
