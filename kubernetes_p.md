# Instalación credenciales de webserver:

Instalar apache:
```sh
sudo apt install apache2
sudo apt install apache2-utils
```
Creamos un fichero de credenciales, llamado ".cred", con un usuario "test" y contraseña "D3v0ps.2023"<br>
-c: Crear nuevo fichero.<br>
-B: Forzar cifrado bcrypt en la contraseña.<br>
-b: Usar el password desde la linea de comandos en vez de preguntar por ella.<br>
`htpasswd -cBb .cred test D3v0ps.2023`

Crear una clave privada:<br>
`openssl genrsa -out localhost.key 2048`<br>
Crear una clave pública a partir de un certificado:<br>
`openssl req -key localhost.key -new -out localhost.csr -subj "/C=ES/ST=Murcia/L=Murcia/O=DevOps/OU=Prueba/CN=vm1"`<br>
Crear certificado autofirmado a partir de las claves privadas y públicas anteriores:<br>
`openssl x509 -signkey localhost.key -in localhost.csr -req -days 365 -out localhost.crt`


## Creación del cluster de kubernetes

Crear en azure

Una vez creado todo se hará un deploy de los pods 


```bash
az login

kubectl get --version
kubectl get version
kubectl version
kubectl get nodes
kubectl get namespaces
kubectl describe nodes
kubectl describe
kubectl api-resources
kubectl pods
kubectl get pods
kubectl get pods -n kube-system
kubectl get sc
kubectl get deployment
kubectl get deployment -n kube-system
kubectl get statefulset -n kube-system
kubectl get deployment 
kubectl get deployment coredns -n kube-system -o yaml
kubectl get sc azurefile -o yaml
```

Los namespaces:

```bash
kubectl create namespace example
kubectl get namespaces
kubectl create -f app.yaml
kubectl get deployment,pods,services -n example
kubectl get pods -n example
kubectl get deployment -n example
kubectl scale deployment/azure-vote-front --scale=10 -n example
kubectl scale deployment/azure-vote-front --replicas=10 -n example
kubectl get deployment -n example
kubectl get pods -n example
```