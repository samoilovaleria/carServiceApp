# Car Service App

**Курсовая работа на втором семестре обучения**  
**Тема**: Клиент-серверное desktop-приложение для поддержки бизнес-процессов автосервиса.

## 1. Проектирование и разработка

**Язык программирования**: Java с использованием библиотеки `JavaFX`.  
**Архитектура**: MVC (Model-View-Controller).  
**База данных**: MySQL, подключение через `MySQL-connector`.  
**Сервер базы данных**: fit.mospolytech.ru (учебный сервер вуза).

### Основные особенности:
- Использование паттерна **Singleton** для избежания избыточных обращений к базе данных.
- **Графический интерфейс** создан в `SceneBuilder`.
- Проверка параметров через **регулярные выражения**.

## 2. Основная функциональность

**Цель создания приложения**: автоматизация процесса записи на услуги автосервиса.

Клиенту предоставлена возможность выбрать деталь, подходящую конкретно его модели автомобиля и имеющуюся в наличии и заказать услугу после оглашения цены. Сотрудники же имеют графический интерфейс, позволяющий им выбирать детали, над которыми они готовы работать, и указать количество дней, необходимое им для этой работы. Эта система позволяет выбирать работника, который закончит услугу быстрее остальных. В начале проводится сортировка сотрудников, готовых в течение двух дней взять в работу нужную деталь, по возрастанию количества времени, требующегося на работу. Если же таких сотрудников не оказывается, вводится запрос, анализирующий, кто из рабочих сможет раньше закончить данную услугу. Для этого у каждого сотрудника, готового взять деталь в работу, находится крайняя работа с самым поздним днём окончания, прибавляется два дня выходных между услугами и количество дней, требующихся для установки детали. Далее выбирается сотрудник, у которого дата окончания работы будет самой ранней. Так можно быть уверенным в наибольшей эффективности. В случае, если сотрудники, готовые взять в работу деталь, не были найдены, клиенту высвечивается окошко с оповещением, а администраторам отправляется уведомление об инциденте для привлечения мер по улучшению работы салона.

## 3. Модели базы данных

### Инфологическая модель (концептуальная):
<img width="450" alt="Инфологическая (концептуальная) модель" src="https://github.com/user-attachments/assets/8bbf4cb3-550e-4c9e-ac9e-33cea31c361b">

### Реляционная модель:
<img width="450" alt="Реляционная модель" src="https://github.com/user-attachments/assets/bf4e3a9f-42da-412e-97d6-ac275321395c">

## 4. Описание интерфейса

### Авторизация и регистрация:
<img width="450" alt="Авторизация" src="https://github.com/user-attachments/assets/e76596f0-a71e-47a5-b94b-f98d53310250">
<img width="450" alt="Регистрация" src="https://github.com/user-attachments/assets/3fff7226-2c21-4094-8954-99adfb6f5489">

### Личный кабинет клиента:
<img width="450" alt="Личный кабинет клиента" src="https://github.com/user-attachments/assets/e4eb9d64-f09f-4d7d-bbb3-00efcb393cb4">
<img width="450" alt="'Гараж' клиента" src="https://github.com/user-attachments/assets/f35259fc-cdb2-4ae8-8eaa-a244a335fbac">

## 5. Доступ и управление

### Клиент:
- **Раздел "Гараж"**: добавление, удаление и редактирование машин.
- Просмотр завершённых и активных услуг для каждой машины.
- Возможность оформления новой услуги.
- Редактирование своего аккаунта.

### Сотрудник:
- **Раздел "Услуги"**: просмотр выполненных услуг.
- **Раздел "Работа"**: выбор деталей для работы и указание сроков.
- Редактирование своего аккаунта.

### Администратор:
- Управление всеми данными: просмотр, добавление, редактирование и удаление клиентов, сотрудников и услуг через графический интерфейс.


