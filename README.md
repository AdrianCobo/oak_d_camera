# 🧠 computer_vision

[![ROS 2 Humble](https://img.shields.io/badge/ROS2-Humble-blue)](https://docs.ros.org/en/humble/)
![distro](https://img.shields.io/badge/ROS2-Jazzy-blue)

Este repositorio contiene el código necesario para inicializar y lanzar múltiples cámaras **OAK** con una configuración optimizada para el sistema de percepción multivista. Está diseñado para trabajar en conjunto con el sistema completo de reconstrucción 3D, facilitando una adquisición eficiente y sincronizada de imágenes en tiempo real.

---

## 🛠️ Instalación

Asegúrate de estar trabajando dentro de un workspace de ROS 2 (por ejemplo, `~/ros2_ws/src`):

```bash
cd ~/ros2_ws/src
git clone -b multicam https://github.com/AdrianCobo/oak_d_camera.git
cd ..
colcon build --packages-select oak_d_camera
```

Una vez finalice la compilación, no olvides fuentear el entorno:
```bash
source install/setup.bash
```

## 🎯 Funcionalidades principales

- Inicialización y configuración de cámaras OAK para visión estéreo.
- Configuraciones optimizadas de resolución, framerate y formatos de salida.
- Preparado para ejecutar múltiples cámaras en paralelo con bajo consumo de recursos.
- Publicación de topics compatibles con otros nodos de ROS 2 dentro del sistema de SLAM visual.

---

## 🗂️ Estructura relevante del repositorio

```bash
computer_vision/
├── include/
│   ├── DepthSync.hpp                  # Genera la nube de puntos del sistema usando imágenes de disparidad sincronizadas
│   ├── PlcSyncIcp.hpp                # ICP usando imágenes de disparidad
│   ├── PlcSyncIcppclfrompcd.hpp      # ICP usando archivos .pcd
│   ├── PlcSyncIcppcl.hpp             # ICP en tiempo real desde topics de ROS 2
│
├── launch/                           # Launchers para facilitar el uso del código anterior
