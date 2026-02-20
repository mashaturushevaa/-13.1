Практична робота 13.1: Time-Series Analytics з OpenHAB

Тема: Інтеграція часових баз даних та аналітика IoT даних
Архітектура системи (WoT & Analytics)
graph LR
    A[5 Sensors] -->|Update| B[(rrd4j Persistence)]
    B -->|Time-Series Data| C{Analytics Rules}
    C -->|Calculation| D[Average Temp]
    C -->|Comparison| E[Trend Direction]
    D & E --> F[Analytics Dashboard]
