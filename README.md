# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Широков Глеб Игоревич
- РИ-210933
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
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

![image](https://user-images.githubusercontent.com/80561050/195989811-64301b04-e364-465f-985f-fa62fcb68905.png)

- В облачном сервисе google console подключил API для работы с google sheets и google drive:
![image](https://user-images.githubusercontent.com/80561050/195989943-a2fd6281-18b4-40a4-9899-42ae3dca0a97.png)

- Реализовал запись данных из скрипта на python в google-таблицу. Данные описывают изменение темпа инфляции на протяжении 11 отсчётных периодов, с учётом стоимости игрового объекта в каждый период.
![image](https://user-images.githubusercontent.com/80561050/195990110-3e44f9c2-af9c-4678-9166-65b728fd8b74.png)

- Создал новый проект на Unity, который будет получать данные из google-таблицы, в которую были записаны данные в предыдущем пункте:
![image](https://user-images.githubusercontent.com/80561050/195990482-8e3da6c7-c165-4082-85c4-aa464c60f14f.png)

- Написал функционал на Unity, в котором воспризводится аудио-файл в зависимости от значения данных из таблицы:
![image](https://user-images.githubusercontent.com/80561050/195990628-94c0de80-70c2-4241-9cd9-4667bec34fb6.png)

Код:

  using System.Collections;
  using System.Collections.Generic;
  using UnityEngine;
  using UnityEngine.Networking;
  using SimpleJSON;

  public class NewBehaviourScript : MonoBehaviour
  {
      public AudioClip goodSpeak;
      public AudioClip normalSpeak;
      public AudioClip badSpeak;
      private AudioSource selectAudio;
      private Dictionary<string, float> dataSet = new Dictionary<string, float>();
      private bool statusStart = false;
      private int i = 1;

      // Start is called before the first frame update
      void Start()
      {
          StartCoroutine(GoogleSheets());
      }

      // Update is called once per frame
      void Update()
      {
          if (dataSet["Mon_" + i.ToString()] <= 10 & statusStart == false & i != dataSet.Count)
          {
              StartCoroutine(PlaySelectAudioGood());
              Debug.Log(dataSet["Mon_" + i.ToString()]);
          }

          if (dataSet["Mon_" + i.ToString()] > 10 & dataSet["Mon_" + i.ToString()] < 100 & statusStart == false & i != dataSet.Count)
          {
              StartCoroutine(PlaySelectAudioNormal());
              Debug.Log(dataSet["Mon_" + i.ToString()]);
          }

          if (dataSet["Mon_" + i.ToString()] >= 100 & statusStart == false & i != dataSet.Count)
          {
              StartCoroutine(PlaySelectAudioBad());
              Debug.Log(dataSet["Mon_" + i.ToString()]);
          }
      }

      IEnumerator GoogleSheets()
      {
          UnityWebRequest curentResp = UnityWebRequest.Get("https://sheets.googleapis.com/v4/spreadsheets/1JOu06CErjclWFTxy_eix69RQRiOHfnRGU45fWt4UKpc/values/Лист1?key=AIzaSyClT_4CuLT2Gt7OgPUaPt0azF2XyOOx5rU");
          yield return curentResp.SendWebRequest();
          string rawResp = curentResp.downloadHandler.text;
          var rawJson = JSON.Parse(rawResp);
          foreach (var itemRawJson in rawJson["values"])
          {
              var parseJson = JSON.Parse(itemRawJson.ToString());
              var selectRow = parseJson[0].AsStringList;
              dataSet.Add(("Mon_" + selectRow[0]), float.Parse(selectRow[2]));
          }
      }

      IEnumerator PlaySelectAudioGood()
      {
          statusStart = true;
          selectAudio = GetComponent<AudioSource>();
          selectAudio.clip = goodSpeak;
          selectAudio.Play();
          yield return new WaitForSeconds(3);
          statusStart = false;
          i++;
      }

      IEnumerator PlaySelectAudioNormal()
      {
          statusStart = true;
          selectAudio = GetComponent<AudioSource>();
          selectAudio.clip = normalSpeak;
          selectAudio.Play();
          yield return new WaitForSeconds(3);
          statusStart = false;
          i++;
      }

      IEnumerator PlaySelectAudioBad()
      {
          statusStart = true;
          selectAudio = GetComponent<AudioSource>();
          selectAudio.clip = badSpeak;
          selectAudio.Play();
          yield return new WaitForSeconds(4);
          statusStart = false;
          i++;
      }
  }


![image](https://user-images.githubusercontent.com/80561050/195990672-fbf200e4-b092-41d6-ab3d-474893dd706f.png)

## Задание 2

-

## Задание 3

-

## Выводы

Я познакомился с программными средствами для организции передачи данных между инструментами google, Python и Unity и создал новый проект на Unity, который получает данные из google-таблицы и выполняет определённые функции.

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
