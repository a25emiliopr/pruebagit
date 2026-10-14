# DOCUMENTACION DEL USO BÁSICO DEL VIRTUALBOX

## INDICE
- 1.Introduccion
- 2.Crear Maquinas
    - 2.1Creacion de discos virtuales
- 3.Instalacion de Sistemas operativos
- 4.Modos de red
- 5.Guest Additions
---

### INTRODUCCION

- **Sistema Anfitrión (Host):** Tu sistema operativo físico (Windows, macOS o Linux).

- **Sistema Invitado (Guest):** El sistema operativo que se ejecuta dentro de la máquina virtual.

- **ISO:** Archivo de imagen que contiene el instalador del sistema operativo invitado (por ejemplo, ubuntu.iso o windows11.iso).

- **Guest Additions:** Conjunto de controladores y aplicaciones que se instalan en la máquina virtual para habilitar funciones avanzadas como resolución dinámica, carpetas compartidas y portapapeles bidireccional.
---

### Crear una nueva Máquina Virtual

1. **Iniciar el asistente:**
    - *Paso inicial en el administrador de VirtualBox.*
    Abre VirtualBox y haz clic en el botón **Nueva** (icono azul) en el menú superior.
2. **Configurar nombre y tipo de sistema:**
    - Asigna un nombre a tu máquina virtual (ej. Ubuntu Test). Selecciona la carpeta de destino, la imagen ISO si deseas detección automática, y verifica que el **Tipo** (Linux, Windows) y la **Versión** sean correctos.
    
3. **Asignar recursos de hardware:** 
    - *No asignes más del 50% de los recursos del Host.*

    - **Memoria RAM:** Asigna el tamaño adecuado según el sistema (ej. mínimo 2048 MB para Linux sin interfaz pesada, 4098 MB para Windows 10/11 o Linux con entorno gráfico).
    - **Procesadores (CPU):** Asigna 2 o más núcleos si tu procesador lo permite (mantén la barra dentro del rango verde).

4. **Crear disco duro virtual:** 
    - Selecciona **Crear un disco duro virtual ahora.**
    
    - **Tipo de archivo:** Deja la opción por defecto (**VDI** - VirtualBox Disk Image).
    
    - **Almacenamiento:** Elige **Reservado dinámicamente** (el archivo del disco crecerá solo conforme uses espacio en el sistema invitado).
    - **Tamaño:** Define la capacidad máxima (ej. 20 GB para Linux, 64 GB para Windows). Haz clic en **Terminar.**
---

### Instalación del Sistema Operativo

1. Selecciona tu máquina virtual en la lista de la izquierda y haz clic en **Iniciar** (flecha verde).

2. Si no seleccionaste una ISO previamente, la máquina te pedirá la **Unidad óptica virtual:** selecciona el archivo .iso descargado en tu equipo.

3. Completa el proceso habitual de instalación del sistema operativo tal como lo harías en un equipo físico.
---

### Modos de red principales

Puedes cambiar el tipo de red en **Configuración > Red > Conectado a:**

          
|Modo de Red|Descripcion|Caso de Uso|
|---|---|---|
|**NAT**|Asigna una IP privada aislada. Permite salir a Internet pero oculta la VM de tu red local.|Navegación estándar e instalaciones sencillas.|
|**Adaptador Puente(Bridget)**|La VM obtiene una IP asignada directamente por tu router como un equipo físico más.|Crear servidores o cuando requieres comunicación directa en la red local.|
|**Red Interna**|Crea una red aislada únicamente entre las máquinas virtuales que compartan el mismo nombre.|Pruebas de seguridad, laboratorios o entornos aislados.|
|**Solo-Anfitrion(Host-Only)**|La VM solo se comunica con tu equipo anfitrión y otras máquinas virtuales en ese adaptador.|Entornos de desarrollo local sin acceso a Internet externo.|
           
---

### Instalación de Guest Additions

Para mejorar el rendimiento y habilitar el ajuste automático de pantalla y portapapeles:
1. Inicia la máquina virtual con el sistema operativo cargado.
2. En la barra de menú superior de la ventana de la VM, ve a **Dispositivos > Insertar imagen de CD de las "Guest Additions"...**
3. Abre la unidad de CD virtual montada dentro del sistema invitado y ejecuta el instalador (VBoxWindowsAdditions.exe en Windows o ejecutable ejecutable de shell en Linux).
4. Reinicia la máquina virtual una vez completada la instalación.


## prueba