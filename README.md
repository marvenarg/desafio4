# Desafío 4 del Modulo 4 - Bootcamp Devops Engineer <br><br>

## Instructivo para la creación del cluster de Kubernetes (Minikube)

### Requisitos previos

- Tener instalado:
  - Docker
  - kubectl
  - minikube

### Instalación de Minikube

```bash
# En Linux (Debian/Ubuntu)
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

### Crear el cluster

```bash
minikube start
```

### Aplicar los manifiestos de Kubernetes

```bash
kubectl apply -f desafio4.yaml
```

### Acceder a la aplicación

1. Obtener la IP de Minikube:

```bash
minikube ip
```

2. Acceder en el navegador o con `curl`:

```
http://<MINIKUBE_IP>:30036
```

### Realizar rollback manual

Para realizar un rollback distinto al predeterminado:

```bash
kubectl set image deployment/desafio4-web webapp=mysven/desafio3:v12
```

Para volver a la última versión:

```bash
kubectl set image deployment/desafio4-web webapp=mysven/desafio3:v13
```

---

## Archivos incluidos

- `desafio4.yaml`: Contiene los manifiestos de Kubernetes (Secrets, PVCs, Deployments, Services).


## Desinstalación 

Para eliminar completamente todos los recursos creados por este despliegue (Deployments, Services, Secrets, ConfigMaps, PVCs), se puede usar el siguiente comando:

kubectl delete -f desafio4.yaml




