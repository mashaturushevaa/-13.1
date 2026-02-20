# Практична робота 13.1: Time-Series Analytics з OpenHAB

**Тема:** Інтеграція часових баз даних та аналітика IoT даних

# 1. Опис проекту
Проект демонструє створення системи для збору, тривалого зберігання та статистичного аналізу даних з мультисенсорної мережі. Використано підхід часових рядів (Time-Series) для виявлення закономірностей у роботі 5 віртуальних датчиків температури.

# 2. Архітектура системи
Для реалізації обрано стекову модель: OpenHAB 4.x як сервер автоматизації та rrd4j як база даних часових рядів.



```mermaid
graph LR
    subgraph "Data Sources"
    A[5 Virtual Sensors]
    end
    
    subgraph "Persistence & Storage"
    B[(rrd4j Time-Series DB)]
    end
    
    subgraph "Analytics Engine"
    C{Rules DSL}
    D[Average Calculation]
    E[Trend Detection]
    end

    A -->|everyMinute| B
    B --> C
    C --> D
    C --> E
    D & E --> F[Analytics Dashboard]
