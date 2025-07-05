# 📦 Kubernetes Cluster - WordPress + MySQL Deployment

Este repositorio contiene una solución funcional para desplegar WordPress junto a MySQL sobre un clúster Kubernetes compuesto por dos nodos Ubuntu Server (master y worker). Se incluyen todos los manifiestos YAML necesarios, así como un diagrama detallado de la arquitectura.

---

## 📁 Estructura del Proyecto
<pre>
k8s-cluster/
│
├── cluster_setup/
│   ├── wordpress-deployment.yaml
│   ├── mysql-deployment.yaml
│   ├── storage_setup.yaml
│   └── calico.yaml
│
├── README.md
└── Diagrama_ev3.jpg
</pre>

## 🚀 Tecnologías Utilizadas
- Kubernetes (kubeadm)
- Ubuntu Server 22.04
- WordPress (contenedor oficial)
- MySQL 5.6 (contenedor oficial)
- Git + GitHub

## 📌 Descripción de la Solución
El clúster implementa WordPress y MySQL en pods separados. Cada uno cuenta con almacenamiento persistente definido mediante PVC y PV. El acceso externo a WordPress se realiza a través de un servicio NodePort. Las credenciales de conexión están gestionadas mediante un recurso Secret.

## 🧩 Componentes Kubernetes
- Deployments: WordPress y MySQL
- Pods: wordpress-pod y mysql-pod
- PVC / PV: Almacenamiento persistente para ambos servicios
- Secrets: mysql-pass con credenciales seguras
- Services: wordpress-service: tipo NodePort (ej: 31497) / mysql-service: tipo ClusterIP (interno)

## 🖼️ Diagrama de Arquitectura
![Diagrama_ev3](https://github.com/user-attachments/assets/38a08645-b877-481c-bdc5-304aaabfc278)

## ⚙️ Despliegue Manual
- kubectl apply -f cluster_setup/secret.yaml
- kubectl apply -f cluster_setup/storage_setup.yaml
- kubectl apply -f cluster_setup/mysql-deployment.yaml
- kubectl apply -f cluster_setup/wordpress-deployment.yaml

## 🌐 Acceso a WordPress
http://"IP_del_nodo":31497

## 🎓 Autor
### Christopher Cabrera González
- 📧 chr.cabrera@duocuc.cl
- 📘 Duoc UC – Ingeniería en Infraestructura y Plataformas Tecnológicas
- 🧪 Evaluación 3 – Asignatura: Diseño de Soluciones de Infraestructura (DIY7121)
