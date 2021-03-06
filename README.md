# GoldResearch
Подготовим прототип модели машинного обучения для «Цифры»
# Описание проекта

Подготовим прототип модели машинного обучения для «Цифры». Компания разрабатывает решения для эффективной работы промышленных предприятий.

Модель должна предсказать коэффициент восстановления золота из золотосодержащей руды. В нашем распоряжении данные с параметрами добычи и очистки. 

Модель поможет оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками.

#### Нам нужно:

* 1. Подготовить данные;
* 2. Провести исследовательский анализ данных;
* 3. Построить и обучить модель.

#### Предсказание коэффициента восстановления золота:
* Необходимо подготовить прототип модели машинного обучение для предсказания коэффициента восстановления золота из золотосодержащей руды.

#### Заказчик: 
* Компания, которая разрабатывает решения для эффективной работы промышленных предприятий. Прототип модели поможет оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками.

#### Чтобы выполнить проект, обратимся к библиотекам *pandas*, *matplotlib* и *sklearn.* 

  - #### [1. Подготовка данных](#part1)
* 1.1. Описание данных
* 1.2. Импорт библиотек
* 1.3. Чтение файлов и изучение данных
* 1.3.1. Расчёт эффективности обогащения
* 1.3.2. Анализ признаков
* 1.4. Предобработка данных
  - #### [2. Анализ данных](#part2)
* 2.1. Анализ концентрации металлов на различных этапах очистки
* 2.2. Анализ размера гранул на обучающей и тестовой выборках
* 2.3. Анализ суммарной концентрации всех металлов на разных стадиях
  - #### [3. Модель](#part3)
* 3.1. Функция для расчета sMAPE
* 3.2. Обучение и сравнение моделей
* 3.3. Проверка модели на тестовой выборке
* 3.4. Проверка модели на адекватность
  - #### [4. Общий вывод](#part4)

## 1. Подготовка данных<a id='part1'></a>

* #### 1.1. Описание данных

#### Технологический процесс
#### Когда добытая руда проходит первичную обработку, получается дроблёная смесь. Её отправляют на флотацию (обогащение) и двухэтапную очистку.
* Rougher feed — исходное сырье
* Rougher additions (или reagent additions) — флотационные реагенты: Xanthate, Sulphate, Depressant
* Xanthate **— ксантогенат (промотер, или активатор флотации);
* Sulphate — сульфат (на данном производстве сульфид натрия);
* Depressant — депрессант (силикат натрия).
* Rougher process (англ. «грубый процесс») — флотация
* Rougher tails — отвальные хвосты
* Float banks — флотационная установка
* Cleaner process — очистка
* Rougher Au — черновой концентрат золота
* Final Au — финальный концентрат золота

#### Параметры этапов

* air amount — объём воздуха
* fluid levels — уровень жидкости
* feed size — размер гранул сырья
* feed rate — скорость подачи

#### Наименование признаков

* Наименование признаков должно быть такое: [этап].[тип_параметра].[название_параметра] 
* Пример: rougher.input.feed_ag

#### Возможные значения для блока [этап]:

* rougher — флотация
* primary_cleaner — первичная очистка
* secondary_cleaner — вторичная очистка
* final — финальные характеристики

#### Возможные значения для блока [тип_параметра]:

* input — параметры сырья
* output — параметры продукта
* state — параметры, характеризующие текущее состояние этапа
* calculation — расчётные характеристики
