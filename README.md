# TP10-DevOps

Para este Proyecto utilizamos de base el tp6 que levanta una pagina web de administracion de personas creada con Pyhton-Django y incluye un motor de base de datos Postgresql.

## Paso 0: Instalar Herramientas/Entorno de trabajo

1. En este repositorio veran un directorio llamado Vagrant, el cual nos permitira levantar una maquina virtual con las herramientas necesarias para el workshop (docker, minikube, kubectl, argocd cli, etc)

Para poder levantar esta maquina, iremos al directorio Vagrant y corremos el siguiente comando:

```
vagrant up
```

1. Ya con la maquina virtual levantada, nos podremos conectar con el siguiente comando

```
vagrant ssh
```

1. Es importante destacar que podemos hacer un tunel de vagrant a nuestra maquina host, esto nos permitira acceder a algun servicio corriendo en la VM desde el host. Para esto, usaremos el siguiente comando:

```
vagrant ssh -- -L 5000:localhost:5000
```

## Paso 1: Dockerfile

1. Para construir la imagen de docker podremos hacerlo de forma manual descargando el codigo y haciendo un docker build del directorio Parte 2 

## Paso 2: Kubernetes

1. Para este paso es tan simple como verificar estar conectados a nuestro cluster de kubernetes (poder ejecutar un kubectl get pods -A sin errores) y asi crear nuestros recursos dentro del directorio Kubernetes con el siguiente comando:

```
kubectl apply -f Kubernetes/kubectl.yaml
```

## Paso 3: ArgoCD y Helm

1. Por ultimo, tendremos la parte de ArgoCD. Podremos crear aplicaciones ya sea utilizando la CLI o utilizando la interfaz grafica de Argo. En este caso utilizaremos el archivo kubectl.yaml dentro del directorio Parte 5  Por ejemplo si quisieramos hacerlo con el ArgoCD CLI:

una vez creado el argo cd vamos a convertir este yaml a Helm con la aplicacion Helmify que la descargamos de la siguiente URL:
