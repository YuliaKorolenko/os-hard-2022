# os-hard-2022

1.Определение операционной системы. Отличие между ОС и ядром ОС. Базовые понятия и концепции ОС. Общая архитектура ОС.

2.Системные вызовы. Особенности параметризации системных вызовов.

3.Режимы (modes) исполнения в ОС. Пространства памяти в ОС.

4.Монолитное и микро-ядро ОС — различия. Модульная структура ядра ОС.

5.Реализации мульти-обработки в ОС. Различие между кооперативным и вытесняющей (preemptive) мульти-обработкой. Кооперативные и вытесняющие ядра (на примере Линукса). Асимметричная и симметричная мульти-обработка (Asymmetric / symmetric multi-processing). Масштабирование ядра ОС по процессорам.

6.Общая структура кода ядра Линукса.

7.Драйверы устройств в архитектуре Линукса.

8.Управление процессами в ОС. Процессы и потоки. Переключение контекста и миграция задач по ядрам процесссора. Контекст процесса. Доступ к текущему процессу. Блокирование и пробуждение. Вытеснение задач в терминах контекста процесса. Системный вызов clone().

9.Пространства имен и контейнеры.

10.Прерывания (Interrupts). Исключительные ситуации (exceptions). Аппаратная концепция прерываний. Программируемый контроллер прерываний. Обработка прерываний в Линуксе. Контекст прерывания. Отложенные действия (deferrable actions). Мягкие запросы на прерывания (Soft IRQ). Тасклеты (Tasklets). Рабочие очереди и таймеры.

11.Что такое управление памятью (memory management). Адресные пространства памяти — физическое и виртуальное. Таблицы трансляции виртуальных адресов. Контексты исполнения. Стеки пользовательского кода, кода яядра и кода прерываний. Страничная организация памяти и вытеснение страниц на диск.

Виртуальные и физические адреса. Устройство управления памятью (MMU). Буфера кэширования трансляции адресов (TLB). Адресные пространства на примере архитектуры ARM. Количество бит в адресе и деления адресов. Линейное отображение адресов. Нелинейное (произвольное) отображение адресов. Фиксированное отображение линейных адресов. Временное/быстрое отображение адресов (страницы в ядре). Постоянное отображение адресов.

Управление физической памятью. Зоны памяти. Неоднородный и однородный доступ к памяти. Кэш страниц в файловом доступе. Выделение физической памяти. kmalloc() & kfree(). Buddy-алгоритм выделения памяти.

Подход к SLAB выделению маленьких фрагментов памяти. Реализация SLAB. Кэши и SLAB.

Управление виртуальной памятью. Анонимная память (анонимное отображение памяти). Переиспользование (reclaim) памяти. Дефрагментация (Compaction) памяти. Обработка нехватки памяти (Out Of Memory Killer). Обработка обращения к отсутствующей странице (page fault). Типы/виды page fault. Влияние page fault на производительность.

Виртуальная файловая система и управление блочным вводом-выводом.

Абстракции файловой системы. Пример простой файловой системы (структура на диске). Операции файловой системы. Кэширование структур данных файловой системы.

Синхронизация — основные идеи и проблемы. Проблема состояния гонки (race condition). Как избегать состояния гонки. Атомарные операции. Спинлоки. Когерентность кэша в многопроцессорных системах. Протоколы когерентности кэша. Вытеснение используемых данных кэша (cache trashing). Синхронизация доступа к данным из контекста процесса и контекста прерывания. Мьютексы. Данные доступа на одном ядре (per CPU data). Упорядочивание доступа к памяти и барьеры. Чтение-копирование-обновление (Read-Copy-Update на примере списка).

Санитайзеры программ. Санитайзеры от Гугла. Санитайзеры EFENCE, KFENCE. Санитайзер KASAN. Теневая память в KASAN. Красные зоны в KASAN.

Сетевая функциональность — история и концепции. TCP/IP. Семейство протоколов в TCP/IP. Протокол ARP. Сетефой стек — диаграмма и уровни. Единицы данных в сетевых протоколах. Блок-схема: Передача — прием данных в сети. Сетевые устройства. IP сервисы: роутинг. Сокеты. Пример использования сокетов для клиент-сервер программ. Сетевой стэк в Линуксе.

Планирование ресурсов в ОС. Планировщик процессов. Типы планировщиков (по горизонту планирования). Диспетчер процессора/процессов. FIFO планировщик. Метрики планирования в мобильной ОС.

Абстракции/концепции планирования. Абстракция/концепция аппаратуры/»железа»/устройства для планирования. Абстракция/концепция задачи/процесса для планирования.

История планировщиков в ядре Линукс. Планировщик CFS. Планировщик процессоров/процессов и формулы потребления энергии. Потребление энергии процессором/памятью. Абстракции управления потреблением энергии.

Что такое DVFS, зачем оно нужно. Архитектура big.LITTLE в контексте планирования процессов. EAS — что это такое, основные принципы. Отслеживание нагрузки для планирования процессов. EAS PELT/WALT. C & P, CC & PC состояния процессора. Управление P состояниями со стороны ОС. Масштибирование производительности в ядре Линукс. Управление частотами в ядре Линукс. Что такое CPUFreq, CPUIdle и гувернеры.

Распределенные системы. Оверлейные сети. Понятие middleware. ОС и middleware. Цели дизайна распределенной ОС. Ошибочные предположения в дизайне распределенной системы. Высокопроизводительные распределенные системы. Кластерные архитектуры. Grid-архитектуры. Облачные архитектуры. Проникующие системы (pervasive systems). Вездесущие (Ubiquitous) системы.

Мобильные ad hoc системы. Концепции архитектуры распределенных систем. Архитектурные стили для распределенных систем. Объектные архитектуры. Распределенные и удаленные обьекты. Ресурсно-ориентированные архитектуры. Архитектура Издатель-Подписчик. Структурированные peer-to-peer системы. Неструктурированные peer-to-peer системы: обмен сообщениями. Иерархические peer-to-peer системы.

Основы программирования для мобильной ОС. Что такое ADB и как им пользоваться. Измерение производительности приложения в инструкциях и циклах. Что такое perf и как им пользоваться.
