# Simulación de Sistemas de Servidores

Este proyecto implementa una simulación en Python para evaluar dos arquitecturas de servidores para una aplicación web: **Mountain Mega Computing** y **Pizzita Computing**. El objetivo es determinar cuál de las dos arquitecturas maneja mejor la carga de solicitudes y cuántos servidores son necesarios para garantizar que no haya esperas en cola en la arquitectura de **Pizzita Computing**.

## Descripción

La simulación está diseñada para:
1. **Evaluar el comportamiento** de ambas arquitecturas de servidores durante 1 hora de operación.
2. **Determinar empíricamente** cuántos servidores en **Pizzita Computing** son necesarios para asegurar que las solicitudes no tengan que esperar en cola.
3. **Simular un aumento de carga** a 6000 solicitudes por minuto a partir del tercer año de lanzamiento de la aplicación.

## Requisitos

- Python 3.x
- Librerías:
  - `simpy`: Para la simulación de eventos.
  - `numpy`: Para la generación de tiempos de llegada y tiempos de servicio.
  - `matplotlib`: Para la visualización de los resultados.

Puedes instalar las dependencias usando `pip`:

```bash
pip install simpy numpy matplotlib
```

## Estructura del Código

### Parámetros del problema

- **Tiempo de simulación**: 1 hora (3600 segundos).
- **Solicitudes por minuto**: 2400 (se incrementa a 6000 a partir del tercer año).
- **Mountain Mega Computing**: 1 servidor capaz de atender 100 solicitudes por segundo.
- **Pizzita Computing**: Varios servidores, cada uno capaz de atender 10 solicitudes por segundo.

### Tareas del Laboratorio

### Task 1: Simulación de los Sistemas de Servidores
Se simula el comportamiento de ambas arquitecturas durante 1 hora, respondiendo a preguntas como:
- ¿Cuántas solicitudes fueron atendidas?
- ¿Cuánto tiempo estuvieron ocupados o desocupados los servidores?
- ¿Cuánto tiempo estuvieron las solicitudes en cola?
  
Se realizan comparaciones visuales de los resultados utilizando gráficos de barras.

### Task 2: Determinación del Número Mínimo de Servidores en Pizzita Computing
Se implementa un algoritmo que incrementa el número de servidores en **Pizzita Computing** hasta encontrar el mínimo necesario para que no haya esperas en cola.

### Task 3: Simulación para 6000 Solicitudes por Minuto
Se repite la simulación del Task 1, pero con una tasa de solicitudes incrementada a 6000 solicitudes por minuto, para evaluar la escalabilidad de los sistemas.

## Ejecución

Puedes ejecutar las celdas del notebook en el siguiente orden:

1. **Task 1**: Ejecuta la simulación para 2400 solicitudes por minuto, generando gráficos comparativos.
2. **Task 2**: Determina cuántos servidores se necesitan en **Pizzita Computing** para evitar esperas en cola.
3. **Task 3**: Ejecuta la simulación para 6000 solicitudes por minuto y compara los resultados.

## Resultados

- **Mountain Mega Computing**: Un servidor con gran capacidad de procesamiento, pero más costoso.
- **Pizzita Computing**: Arquitectura con múltiples servidores, donde el número necesario se determina de acuerdo a la carga proyectada.

## Notas Importantes

- **Lambda del proceso de Poisson**: La tasa de solicitudes por segundo se calcula como `SOLICITUDES_POR_MINUTO / 60`.
- **Lambda de la variable exponencial**: El tiempo de servicio se modela como una distribución exponencial con tasas de 1/100 para **Mountain Mega Computing** y 1/10 para **Pizzita Computing**.
- **Cola FIFO**: Las solicitudes entran en una cola FIFO cuando los servidores están ocupados.

## Gráficos

El proyecto genera gráficos para comparar:
- El número de solicitudes atendidas.
- El tiempo promedio en cola.
- El tiempo ocupado y desocupado de los servidores.

## Autor
Alejandro Azurdia | Angel Castellanos | Diego Morales - CC3039 Modelación y Simulación - Semestre II - 2024

