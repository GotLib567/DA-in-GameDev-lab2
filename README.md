# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Широков Глеб Игоревич
- РИ-210933
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | # | 60 |
| Задание 2 | # | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Познакомиться с программными средствами для организции передачи данных между инструментами google, Python и Unity.

## Задание 1
Ход работы:
Реализовал совместную работу и передачу данных в связке Python - Google-Sheets – Unity. При выполнении задания использовал видео-материалы и
исходные данные, предоставленные преподавателями курса.

![lab1](https://user-images.githubusercontent.com/80561050/192602848-46a88cf6-9fc5-47c5-aa00-fdd1c11ab0d3.png)

- Вывод сообщения "Hello world" в Unity:

![lab1(1)](https://user-images.githubusercontent.com/80561050/192835769-9e2edd94-46ac-4653-a2b2-425f063cf97e.png)

## Задание 2

Возникли технические проблемы с Anaconda и Jupyter Notebook. Выполнил задание в google.colab.

- Произвёл подготовку данных для работы с алгоритмом линейной регрессии:

![task2(1)](https://user-images.githubusercontent.com/80561050/192855951-ecb3562a-b0cd-4d66-99fb-ac7cd22eacee.png)

- Определил связанные функции:

![image](https://user-images.githubusercontent.com/80561050/192857590-c3e7b37f-d50c-4f03-9444-cdda87a23e25.png)

- Начал итерацию:
Шаг 1. Инициализация и модель итеративной оптимизации.

![image](https://user-images.githubusercontent.com/80561050/192857813-94051069-f74b-4ec5-b328-0b5de508dcbb.png)

Шаг 2. На второй итерации отображаются значения параметров, значения
потерь и эффекты визуализации после итерации.

![image](https://user-images.githubusercontent.com/80561050/192858168-2f0ede6c-bc07-4ab9-a77a-1e1b1ebf14cf.png)

Шаг 3. Третья итерация показывает значения параметров, значения потерь и
визуализацию после итерации.

![image](https://user-images.githubusercontent.com/80561050/192858316-3136a853-c58a-456a-9042-91c11cfa96b8.png)

Шаг 4. На четвертой итерации отображаются значения параметров, значения
потерь и эффекты визуализации.

![image](https://user-images.githubusercontent.com/80561050/192858428-41a8c950-62ec-416c-9acc-a81ebf797667.png)

Шаг 5. Пятая итерация показывает значение параметра, значение потерь и
эффект визуализации после итерации.

![image](https://user-images.githubusercontent.com/80561050/192858578-20bee7df-37fe-4c5f-af1a-932d3b6c86f2.png)

Шаг 6. 10000-я итерация, показывающая значения параметров, потери и
визуализацию после итерации.

![image](https://user-images.githubusercontent.com/80561050/192858734-df6ebdbe-a05c-4a4f-b36f-00b88e2b8cbb.png)

Ссылка на google.colab: https://colab.research.google.com/drive/1eagCvqSkHrHkt169l7NNPqewGpX0ReVt?usp=sharing

## Задание 3
### Должна ли величина loss стремиться к нулю при изменении исходных данных?

- Ответ: нет.
При любых значениях прямая стремится в положительную сторону.

![image](https://user-images.githubusercontent.com/80561050/192862388-8ec8dca2-4d8e-4564-9a1d-e9a9333426ef.png)

![image](https://user-images.githubusercontent.com/80561050/192862437-c6f111ac-167e-4e86-9654-06b8b45e5d7c.png)

### Какова роль параметра Lr?

- Ответ: Lr - это коэффициент, который определяет масштаб графика.

![image](https://user-images.githubusercontent.com/80561050/192864087-67c146ee-a1e4-43b4-9fe7-88d6839317b0.png)


## Выводы

Я установил все утилиты (PyCharm, Unity, VS Code, .Net, Anaconda) для работы с заданиями и ознакомился с основными операторами зыка Python на
примере реализации линейной регрессии.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
