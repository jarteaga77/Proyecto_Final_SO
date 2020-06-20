# Proyecto_Final_SO
Este informe presenta las actividades realizadas para llevar a cabo el despliegue de tecnologías FaaS (Function as a Service), K8S (Kubernetes) e Inlets.

Despliegue de Kubernetes
El ambiente que se eligió para llevar a cabo el despliegue de kubernetes fue Minikube en sistema Operativo Linux Ubuntu 20.04 LTS.
Minikube es una versión reducida de Kubernetes que permite correr en una máquina virtual, un nodo único de clúster de kubernetes, que hace las veces de máster y workers.

A continuación se presentan los pasos realizados para instalar Minikube de acuerdo a :
Consideraciones Iniciales: 
- Verificar si la virtualización es soportada en Linux ejecutando el siguiente comando y verificar que la salida no esta vacía.
grep -E --color 'vmx|svm' /proc/cpuinfo
- Instalar un hipervisor: Hipervisor elegido VirtualBox,

Instalar kubectl


Descargar la versión mas reciente 
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

Dar permisos de ejecución al binario kubectl
chmod +x ./kubectl

Mover el binario al path del usuario
sudo mv ./kubectl /usr/local/bin/kubectl

Verificar que la verion instalada sea la mas reciente
kubectl version –client


3) Instalar Minikube via descarga directa

curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \  && chmod +x minikube

    4) Adicionar el ejecutable de Minikube al path del usuario
    sudo mkdir -p /usr/local/bin/
sudo install minikube /usr/local/bin/

    5) Instalar helm que es un gestor de paquetes de kubernetes. (Versiones de Ubuntu 16.04 o     superiores ya tienen instalado snap, versiones inferiores no lo incluyen y debe ser instalado     previamente). 
sudo snap install helm –classic

    6) Confirmar la instalación iniciando el cluster de Minikube
    minikube start --driver=virtualbox
    minikube status
    
    

