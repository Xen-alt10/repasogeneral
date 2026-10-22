# Manual del Usuario — Taller Integrador de Repaso

| Campo | Detalle |
|-------|---------|
| **Materia** | Laboratorio de Programación (LPR) — 5° |
| **Institución** | E.E.S.T. N° 20 "Bangtan Sonyeondan" – Vicente López |
| **Estudiante** | Alexander Veit |
| **Archivo** | `src/main.cpp` |
| **Actividad** | 6 — Suite de Taller de Repaso e Integración |
| **Lenguaje** | C++ (C++11 o superior) |

---

## 1. Descripción General

Este programa es un **taller integrador** que repasa tres conceptos fundamentales de C++:

| # | Concepto | Función asociada |
|---|----------|-----------------|
| 1 | Recursividad | `sumaRecursiva(int n)` |
| 2 | Arreglos + Búsqueda secuencial | (bloque en `main`) |
| 3 | Punteros + Intercambio por referencia | `intercambiarValores(int*, int*)` |

---

## 2. Compilación y Ejecución

### Requisitos

- Compilador **g++** (GCC ≥ 7) o **clang++**.
- Sistema operativo: Linux, macOS o Windows (con WSL / MinGW).

### Comandos

```bash
# Compilar
g++ -std=c++17 -Wall -Wextra -o taller src/main.cpp

# Ejecutar
./taller   

```
## Salida Esperada 

```
=====================================================
  TALLER INTEGRADOR REPASO - ESTUDIANTE: Alexander Veit
=====================================================

=== RETO 1: SUMA RECURSIVA ===
Suma acumulada de 1 hasta 5: 15

=== RETO 2: BUSQUEDA EN MEMORIA CONTIGUA ===
[SISTEMA] Valor 18 hallado en el indice [6]
          Direccion RAM Hexadecimal: 0x7ffd...

=== RETO 3: INTERCAMBIO DE CELDAS ===
Valores previos  -> X: 100 | Y: 500
Valores actuales -> X: 500 | Y: 100
=====================================================   
```

## Codigo Fuente Completo

```

/*
   ====================================================================
   Materia: Laboratorio de Programación (LPR) — 5°
   Institución: E.E.S.T. N° 20 "Bangtan Sonyeondan" - Vicente López
   Archivo: src/main.cpp
   Actividad 6: Suite de Taller de Repaso e Integración
   ====================================================================
*/

#include <iostream>

using namespace std;

// Prototipos de funciones modulares
int sumaRecursiva(int n);
void intercambiarValores(int* ptrA, int* ptrB);

int main() {
    cout << "=====================================================" << endl;
    cout << "  TALLER INTEGRADOR REPASO - ESTUDIANTE: Alexander Veit " << endl;
    cout << "=====================================================" << endl;

    // --- RETO 1: RECURSIVIDAD ---
    cout << "\n=== RETO 1: SUMA RECURSIVA ===" << endl;
    int num = 5;
    cout << "Suma acumulada de 1 hasta " << num << ": " << sumaRecursiva(num) << endl;

    // --- RETO 2: ARRAYS Y BÚSQUEDA SECUENCIAL ---
    cout << "\n=== RETO 2: BUSQUEDA EN MEMORIA CONTIGUA ===" << endl;
    const int TAM = 10;
    int vectorDatos[TAM] = {12, 45, 78, 90, 122, 5, 18, 33, 67, 99};
    int numeroBuscar = 18;
    bool hallado = false;

    for (int i = 0; i < TAM; i++) {
        if (vectorDatos[i] == numeroBuscar) {
            cout << "[SISTEMA] Valor " << numeroBuscar << " hallado en el indice [" << i << "]" << endl;
            cout << "          Direccion RAM Hexadecimal: " << &vectorDatos[i] << endl;
            hallado = true;
            break;
        }
    }

    if (!hallado) {
        cout << "[SISTEMA] El valor " << numeroBuscar << " no existe en el arreglo." << endl;
    }

    // --- RETO 3: INTERCAMBIO CON PUNTEROS ---
    cout << "\n=== RETO 3: INTERCAMBIO DE CELDAS ===" << endl;
    int x = 100, y = 500;
    cout << "Valores previos  -> X: " << x << " | Y: " << y << endl;

    intercambiarValores(&x, &y);

    cout << "Valores actuales -> X: " << x << " | Y: " << y << endl;
    cout << "=====================================================" << endl;

    return 0;
}

int sumaRecursiva(int n) {
    if (n <= 0) return 0;
    return n + sumaRecursiva(n - 1);
}

void intercambiarValores(int* ptrA, int* ptrB) {
    int temporal = *ptrA;
    *ptrA = *ptrB;
    *ptrB = temporal;
}

```

