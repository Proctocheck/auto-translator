# auto-translator
Program for auto translate any video in real time

## ПРЕДИСЛОВИЕ

#### Перед тем, как запускать прогу, необходимо:

1) установить virtual audio cable

2) в sound mixer options для всех бырать defaul input = Linme 1(virtual audio cable)

3) затем для нужной программы (окна) в oputput выбрать тот же кабель (Line 1, например) 

4) вызвать код для нахождения подключённых аудиоустройств: ```for i in range(a.recorder.get_device_count()):
       print(i, a.recorder.get_device_info_by_index(i))```

5) выбрать подходящее аудиоустройство (для записи должно быть устройство Line 1, у которого ```'maxInputChannels' != 0```,
  а для вывода должно быть устройство Line 1, у которого ```'maxOutputChannels' != 0```

6) и когда открываете потоки в kwargs передаёте нужный вам индекс в переменную ```input_device_index```

7) после запуска у нас звук будет перенаправляться так: приложение->Line_1_output->Line_1_input->Наша прога.
