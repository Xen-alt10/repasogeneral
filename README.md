# Proyecto: Taller Práctico de Repaso y Consolidación en C++ — LPR 2026

**Escuela de Educación Secundaria Técnica N° 1 — Vicente López**  
**Asignatura:** Laboratorio de Programación (LPR) — 5° Año  
**Profesor:** Prof. Mansilla Muñoz York  
**Ciclo Lectivo:** 2026  
**Estudiante:** Alexander Luca Veit

## 🎯 Descripción del Proyecto

Este repositorio contiene la suite modular de C++ correspondiente a la Actividad 6, orientada a ejercitar y consolidar tres pilares fundamentales de programación de bajo nivel:

- **Reto 1 (Recursividad):** Gestión de la Pila de Llamadas (Stack) y aplicación de caso base de parada para evitar el colapso por *Stack Overflow*.
- **Reto 2 (Búsqueda Secuencial):** Recorrido indexado en arreglos contiguos de memoria RAM, optimizando el tiempo de ejecución con la instrucción `break`.
- **Reto 3 (Punteros e Intercambio Físico):** Pasaje por dirección (`&`) y desreferenciación (`*`) para la modificación directa de celdas de memoria.

## 🗂️ Estructura del Repositorio

```text
repasogeneral/
├── .gitattributes      # Normalización de finales de línea
├── .gitignore          # Reglas de exclusión de binarios (.exe, .vscode)
├── LICENSE             # Licencia MIT de uso escolar
├── README.md           # Portada técnica del proyecto
├── src/                # Código fuente compilable
│   ├── main.cpp        # Código fuente C++ unificado
│   └── repasogeneral.exe  # Ejecutable local
├── docs/               # Documentación y manuales técnicos
│   ├── InformeEEST1_LPR2026_ACT06_G99_Informe_v1.1.0.pdf
│   ├── CHANGELOG.md    # Bitácora de versionado SemVer
│   └── manuales/
│       ├── manual_del_programador_v1.0.0.pdf
│       ├── manual_del_usuario_v1.0.0.pdf
│       └── manual_usuario_v1.0.0.md (si aplica)
└── capturas/           # Evidencias de ejecución (.png)
    ├── ejecucion_repasogeneral.png
    ├── traza_memoria.png
    └── git_remote.png
```

## 💻 Implementación

El programa `src/main.cpp` integra los tres retos:

### Reto 1: Suma Recursiva
Función `int sumaRecursiva(int n)` con caso base `if (n <= 0) return 0;` para evitar desbordamiento de pila. Calcula la suma acumulada de `1` hasta `n` mediante recursividad.

### Reto 2: Búsqueda Secuencial
Recorre un arreglo contiguo `vectorDatos[10] = {12, 45, 78, 90, 122, 5, 18, 33, 67, 99}` en búsqueda del valor `18`. Al encontrarlo, muestra el índice, la dirección RAM hexadecimal (`&vectorDatos[i]`) e interrumpe la búsqueda con `break`.

### Reto 3: Intercambio con Punteros
Función `void intercambiarValores(int* ptrA, int* ptrB)` que utiliza una variable temporal para intercambiar físicamente los valores de `x` e `y` mediante desreferenciación (`*ptrA`, `*ptrB`), modificando directamente las celdas de memoria.

## 🧠 Diagrama de Traza de Memoria RAM

Esquema de distribución en la Pila (Stack):

| DIRECCIÓN HEX | VARIABLE / CONCEPTO | VALOR EN CELDA |
|---|---|---|
| `0x61fe1c` | `int x (main)` | `500` (ex `100`) |
| `0x61fe18` | `int y (main)` | `100` (ex `500`) |
| `0x61fe08` | `vectorDatos[6]` | `18` |
| `0x61fdf0` | `int* ptrA` | `0x61fe1c` |
| `0x61fde8` | `int* ptrB` | `0x61fe18` |
| `0x61fde0` | `int temporal` | `100` (búfer) |

**Pila de llamadas recursivas (Stack Frames):**

1. `[ sumaRecursiva(0) ]` → Retorna `0` (Caso Base)
2. `[ sumaRecursiva(1) ]` → Retorna `1 + 0 = 1`
3. `[ sumaRecursiva(2) ]` → Retorna `2 + 1 = 3`
4. `[ sumaRecursiva(3) ]` → Retorna `3 + 3 = 6`
5. `[ sumaRecursiva(4) ]` → Retorna `4 + 6 = 10`
6. `[ sumaRecursiva(5) ]` → Retorna `5 + 10 = 15` → Entregado a `main()`

## 🛠️ Requisitos e Instalación

Para compilar y ejecutar este proyecto en Windows 10/11:

- **Visual Studio Code:** Con las extensiones oficiales C/C++ de Microsoft.
- **Compilador MinGW (GCC/G++):** Configurado en el `PATH` de Windows.
- **Git for Windows:** Para la gestión del repositorio y sincronización con GitHub/GitLab.

## ▶️ Compilación y Ejecución (PowerShell)

Asegurate de estar parado en la raíz de la carpeta `repasogeneral` en la terminal integrada de VS Code (`Ctrl + Ñ`).

### Compilar el código fuente C++

```bash
g++ src/main.cpp -o src/repasogeneral.exe
```

### Ejecutar la aplicación en Windows

```bash
.\src\repasogeneral.exe
```

## 🌐 Sincronización Dual-Remote (GitHub + GitLab)

Este repositorio está configurado para mantener sincronizados simultáneamente ambos repositorios remotos:

```bash
# Configuración de remotos
git remote add origin https://github.com/Xen-alt10/repasogeneral.git
git remote set-url --add --push origin https://gitlab.com/webapplicationsdevelopmentde/repasogeneral.git

# Envío unificado
git push origin main
```

## 🧪 Evidencias

El repositorio incluye capturas del proceso en la carpeta `capturas/`:

- `ejecucion_repasogeneral.png` - Captura de pantalla de la terminal con la ejecución
- `traza_memoria.png` - Diagrama de distribución en la RAM
- `git_remote.png` - Configuración de remotos duales

## 📚 Documentación

- **Informe:** `docs/InformeEEST1_LPR2026_ACT06_G99_Informe_v1.1.0.pdf`
- **Bitácora:** `docs/CHANGELOG.md`
- **Manuales:** `docs/manuales/manual_del_programador_v1.0.0.pdf`, `docs/manuales/manual_del_usuario_v1.0.0.pdf`

## 👤 Autor

- **Alexander Luca Veit** — Programador / Estudiante  
  GitHub: [Xen-alt10](https://github.com/Xen-alt10)  
  Repositorio: [repasogeneral](https://github.com/Xen-alt10/repasogeneral)

## 📄 Licencia

Este proyecto está bajo licencia [MIT](LICENSE). Copyright (c) 2026 Xen-alt10.
