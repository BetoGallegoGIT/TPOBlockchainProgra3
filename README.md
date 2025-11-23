# Blockchain Solver con Backtracking 🔗

> Algoritmo avanzado en Java para la construcción y validación de bloques de una Blockchain simulada, optimizado mediante técnicas de Backtracking y poda.

## 📋 Descripción del Proyecto
Este proyecto implementa un motor de resolución lógica que recibe un pool de transacciones desordenadas y construye una **Blockchain válida** respetando estrictas reglas de negocio y criptografía simulada.

El núcleo del proyecto es un algoritmo de fuerza bruta controlada (**Backtracking**) que explora el árbol de soluciones posibles para encontrar la distribución óptima de transacciones en bloques.

Nota: Este proyecto fue desarrollado como parte de la cursada de Programación III en la Universidad Argentina de la Empresa (UADE).

## 🚀 Características Técnicas
* **Algoritmo de Backtracking:** Implementación recursiva para ensamblar bloques válidos probando combinaciones y descartando caminos inválidos.
* **Validación de "Proof of Work":** Simulación de minería verificando la divisibilidad de valores (Regla de negocio: suma de valores % 10 == 0).
* **Gestión de Dependencias:** Control de grafos de transacciones (una transacción hija no se agrega si su padre no está en la cadena).
* **Optimización de Recursos:** Control estricto de límites de memoria (Max 1MB por bloque) y cantidad de transacciones (Max 3).
* **Persistencia:** Uso de archivos para la lectura y escritura de los estados de la cadena.

## 🛠️ Tecnologías Utilizadas
* **Lenguaje:** Java (JDK 17)
* **Conceptos:** Programación Orientada a Objetos (POO), Recursividad, Estructuras de Datos, Complejidad Algorítmica.
* **Patrones:** Singleton (en la configuración del sistema).

## 🧠 Lógica del Algoritmo (Snippet)
El sistema utiliza una estrategia de "poda" para mejorar la eficiencia:

```java
// Ejemplo simplificado de la lógica de validación
if (bloque.getValorTotal() % 10 != 0) {
    return false; // Poda: El bloque es inválido, retroceder (backtrack)
}
