# Módulo 2: Instalación de Kubernetes

Teniendo en cuenta que nuestro sistema operativo es Ubuntu (Probado en Ubuntu 20.04 y Ubuntu 22.04):

1. Necesitamos instalar Docker (si no lo tenemos instalado ya):

``sudo apt update``

``sudo apt install ca-certificates curl gnupg lsb-release``

``sudo mkdir -m 0755 -p /etc/apt/keyrings``

``curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg``

``echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null``

``sudo apt update``

``sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin``


2. Instalamos un orquestador de Kubernetes (existen varios pero utilizaremos Minikube):

``curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb``

``sudo dpkg -i minikube_latest_amd64.deb``


3. Cada vez que queramos iniciar el servicio de Kubernetes tendremos que usar:

``minikube start``


4. Además, necesitaremos el paquete kubectl:

``minikube kubectl -- get po -A``


**¡Ya tendríamos listo Kubernetes para ser usado!**
