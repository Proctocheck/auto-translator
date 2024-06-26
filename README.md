# auto-translator
Program for auto translate any video in real time

## ПРЕДИСЛОВИЕ

#### Перед тем, как запускать прогу, необходимо:

1) установить virtual audio cable

2) в sound mixer options для всех выбрать defaul input = Line 1(virtual audio cable) ( можете выбрать любой удобный вам кабель)

3) затем для нужной программы (окна) в output выбрать тот же кабель (Line 1, например) 

4) вызвать код для нахождения подключённых аудиоустройств:

   ```recorder = pyaudio.PyAudio()```

   ```for i in range(recorder.get_device_count()):```
   
   ```    print(i, recorder.get_device_info_by_index(i))```

5) выбрать подходящее аудиоустройство (для записи должно быть устройство Line 1, у которого ```'maxInputChannels' != 0```,
  а для вывода должно быть устройство (наушники, колонки), у которого ```'maxOutputChannels' != 0```

6) и когда открываете потоки для записи/воспроизведения звука в kwargs передаёте нужный вам индекс в переменную ```input_device_index```, аналогично для ```input_device_index``` в воспроизводящем потоке

7) после запуска у нас звук будет перенаправляться так: приложение->Line_1_output->Line_1_input->Наша прога->Вывод на выбранное устройство.
