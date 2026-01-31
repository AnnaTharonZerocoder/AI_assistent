```mermaid
flowchart TD
    A([Начало диалога]):::start
    B[Приветствие + краткое описание возможностей бота]:::action
    C{Выбор действия:}:::decision
    
    %% Ветка 1: Поиск/вопрос
    C1[Поиск по материалам / Задать вопрос]:::option
    D1[Анализ запроса → Поиск в базе знаний]:::action
    D2{Требуются уточнения?}:::decision
    D3[Задать уточняющий вопрос]:::action
    D4[Сформировать ответ со ссылками на оригинальные страницы <br/>(с сохранением стиля и иронии)]:::action
    
    %% Ветка 2: Навигация
    C2[Помощь с навигацией / освоением интерфейса]:::option
    E1[Показать разделы / инструкции по интерфейсу]:::action
    
    %% Ветка 3: Персонализация
    C3[Персонализированные рекомендации]:::option
    F1[Анализ истории запросов пользователя]:::action
    F2[Подобрать релевантные материалы]:::action
    
    %% Объединение веток
    X[+]:::connector
    
    %% Доп. предложения
    G[Предложить подписаться на канал]:::action
    H[Предложить посетить магазин]:::action
    
    %% Завершение
    I{Продолжить диалог?}:::decision
    J([Завершение]):::end
    
    %% Соединения
    A --> B
    B --> C
    
    C --> C1
    C1 --> D1
    D1 --> D2
    D2 -- "Да" --> D3
    D3 --> D1
    D2 -- "Нет" --> D4
    D4 --> X
    
    C --> C2
    C2 --> E1
    E1 --> X
    
    C --> C3
    C3 --> F1
    F1 --> F2
    F2 --> X
    
    X --> G
    G --> H
    H --> I
    
    I -- "Да" --> C
    I -- "Нет" --> J
    
    %% Стили
    classDef start fill:#4CAF50,stroke:#2E7D32,color:white,stroke-width:2px
    classDef end fill:#F44336,stroke:#C62828,color:white,stroke-width:2px
    classDef decision fill:#FFECB3,stroke:#FFA000,stroke-width:2px
    classDef action fill:#E3F2FD,stroke:#1E88E5,stroke-width:1.5px
    classDef option fill:#F3E5F5,stroke:#7B1FA2,stroke-width:1.5px
    classDef connector fill:#9E9E9E,stroke:#616161,color:white,stroke-width:1px
```
