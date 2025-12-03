# 🌐 Trabajo Práctico Final – Administración de Sistemas Linux

**Alumno:** Facundo Rodriguez Ventura  
**Materia:** Arquitectura y Sistemas Operativos – UTN FRA  
**División:** 313  
**Año:** 2025  

<div align="center">

## 🐧 Entorno Linux + Virtualización + Contenedores

![Vagrant](https://img.shields.io/badge/Vagrant-1868F2?style=flat-square&logo=vagrant&logoColor=white) 
![VirtualBox](https://img.shields.io/badge/VirtualBox-183A61?style=flat-square&logo=virtualbox&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![LVM](https://img.shields.io/badge/LVM-800080?style=flat-square) 
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)  
**Monitoring Stack:** Grafana + Prometheus + Loki

</div>

---

## 📁 Estructura del Proyecto

<div align="center">

<img width="320" alt="Estructura de Carpetas" src="https://github.com/user-attachments/assets/03bbfabf-c5d4-4df7-8921-7186a3c82929" />

</div>

---

## 🚀 Resumen por Ejercicio

### 🔍 0. Descubrimiento de la IP de la VM

- Se levantó la VM con `vagrant up`
- Se identificó su IP mediante:  
  `ip a`  
  `hostname -I`
- La dirección final quedó registrada en:  
  `informacion/ip_vm.txt`

---

### 🏗️ 1. Configuración Inicial + Git + Repositorio

- Creación del repositorio en GitHub
- Clonado desde la VM con SSH
- Configuración de Git (`user.name`, `user.email`)
- Verificación de acceso y commits colaborativos

**Archivos:**  
- `informacion/system_info.txt`

---

### ⚙️ 2. Fastfetch colaborativo

- Desde cada una de las maquinas virtuales (admin, dev, ops) se generó su captura del sistema con `fastfetch`
- Consolidación de capturas en  
  `informacion/system_info.txt`

---

### 🔐 3. Permisos y Usuarios

- Creación y administración de usuarios
- Asignación de grupos
- Permisos: **600**, **644**, y colaborativos (**770**)
- Directorio de trabajo: `equipotrabajo`

**Verificaciones:**  
- `permisos/usuarios_admin.txt`  
- `permisos/usuarios_dev.txt`  
- `permisos/usuarios_ops.txt`  
- `permisos/verificacion_permisos.txt`

---

### 💾 4. Administración de LVM (Logical Volume Manager)

- Detección del disco adicional
- Creación de:
    - PV – Physical Volume
    - VG – Volume Group
    - LV – Logical Volume
- Formateo, montaje y configuración de `/etc/fstab`
- Verificaciones:  
  `pvscan`, `vgscan`, `lvscan` antes y después de montar

**Archivo:**  
- `lvm/lvm-admin.txt`
- `lvm/lvm-dev.txt`
- `lvm/lvm-ops.txt`

---

### 📁 5. Estructura de Archivos y Directorios

- Creación del árbol de carpetas solicitado por el TP
- Archivos:
    - Creación: `1–10`
    - Copia: `1–5`
    - Movimiento: `6–8`
    - Respaldos: `9–10`
    - Limpieza: temporales

**Verificación:**  
- `archivos/verificacion_archivos.txt`

---

### 🐳 6. Contenedores y Monitoreo – Docker Compose

- Corrección, depuración y ejecución de stack:
    - Nginx
    - Redis
    - Postgres
    - Prometheus
    - Loki
    - Grafana

#### 🛠️ Errores encontrados (y resueltos)

- ❌ Volúmenes mal declarados  
- ❌ Redes con nombres inconsistentes (`monitoring-network`)  
- ❌ Versión obsoleta (`docker-compose` vs `docker compose`)  
- ❌ Contenedores existentes bloqueando nombres  
- ❌ Indentación YAML dañada

**Documentación:**  
- `contenedores/errores_encontrados.md`  
- `contenedores/verificacion_contenedores.txt`  
- `contenedores/logs_completos.txt`

## 📘 Conclusión

La soltura con la que me puedo mover con linux al haber terminado el tp se nota y mucho. Lo mismo con respecto a las maquinas virtuales (que al inicio de la cursada no entendía nada).
Valoro lo aprendido este cuatri. El dinamismo y la cercanía de las clase ayudó bastante a hacer llevadera la materia.
Me copó mucho el trabajo profe. 

---

## 👤 Autor

Facundo Rodríguez  
📌 [GitHub: Facurv8714](https://github.com/Facurv8714)
