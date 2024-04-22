# microReader v1.1
[Платы, компоненты и наборы](#parts)  
[Инструкция по сборке проекта](#assembly)  
[Компиляция проекта и прошивка ESP](#compile)  

## Обновление 1.1
- Обновлена [плата](https://oshwlab.com/nich1con/microreader)
- Добавлено отображение картинок в **.itxt / .h** (см. инструкцию)
- Добавлена первая игра - **google dino**
- Добавлено сервисное меню для сброса настроек и форматирования
- Добавлена проверка файлов и файловой системы, поддерживаются файлы **.txt / .itxt / .h**
- Добавлена защита от неверного ввода имени / пароля сети в режимах AP и STA
- Значительно оптимизирована работа с файловой системой (ускорена работа)
- Весь интерфейс русифицирован
- Обновиться можно по воздуху, файл **firmware/BIN/a-microReader-v1.1.ino.bin**

## <a id="parts">Платы, компоненты и наборы</a>
### Наборы
Все необходимое для повторения проекта можно заказать у нас: [OZON](https://clck.ru/3AE6Jm)
![KIT](https://github.com/Nich1con/microReader/blob/main/manual/kit.png)
- Все необходимые компоненты **одной** посылкой
- Модуль ESP12E уже **прошит**  
- Модуль TP4056 **не требует** доработки
- Комплект **SMD + выводных** компонентов на выбор
### Компоненты 
- Дисплей SSD1306 **4-pin** [Aliexpress](https://fas.st/6m9ia)
- Аккумулятор **502025** [Aliexpress](https://fas.st/ScpZv)
- Модуль **ESP12E** [Aliexpress](https://fas.st/B_DJo)
- Модуль **TP4056** [Aliexpress](https://fas.st/myf-5)
- Кнопки **бесшумные** [Aliexpress](https://fas.st/6HQUZr)
- Переключатель **2P2T MSS22D18** [Aliexpress](https://fas.st/a0ehQ)
- Разъем **2P XH2.54** [Aliexpress](https://fas.st/hLyMM)
- Кабель **2P XH2.54** [Aliexpress](https://fas.st/BRWcS)
- Резисторы 10 кОм **выводные 0.25W** или **SMD 1206** 5шт.
- Резистор 220 Ом **выводной 0.25W** или **SMD 1206** 1шт.
- Диод FR107 **выводной DO-41** или **SMD SOD-123** 1шт.
### Плата
- Gerber-файлы для изготовления платы можно найти в папке **PCB**
- Рекомендуемые параметры платы: черная маска, толщина 1.6 мм

## <a id="assembly">Сборка и пайка</a>
### Понадобится для сборки
- Паяльник с тонким жалом
- Припой **ПОС-61**, **KAINA** или аналог
- Нейтральный / безотмывочный флюс для пайки
- Средства для удаления следов флюса - спирт / **FluxOFF** или аналог
- Кусачки, ножницы или канцелярский нож
- Мультиметр 
### Важные моменты
- **Не используйте** активные флюсы на основе кислоты или глицерина!
- Тщательно смывайте остатки флюса после **каждого** этапа сборки!   
- Не рекомендуется использовать дешёвый китайский припой
- Диод и резисторы устанавливаются SMD **или** выводные, на выбор!
### Этапы сборки
![ASM1](https://github.com/Nich1con/microReader/blob/main/manual/Assembly_1.png)
---
![ASM2](https://github.com/Nich1con/microReader/blob/main/manual/Assembly_2.png)
---
![ASM3](https://github.com/Nich1con/microReader/blob/main/manual/Assembly_3.png)
---
![ASM4](https://github.com/Nich1con/microReader/blob/main/manual/Assembly_4.png)
---
![ASM5](https://github.com/Nich1con/microReader/blob/main/manual/Assembly_5.png)
---
![ASM6](https://github.com/Nich1con/microReader/blob/main/manual/Assembly_6.png)
---
![ASM7](https://github.com/Nich1con/microReader/blob/main/manual/Assembly_7.png)


## <a id="compile">Компиляция проекта и прошивка ESP</a>
Если вы повторяете проект с нуля - **необходимо** прошить модуль ESP.  
Подробную инструкцию по загрузке прошивки можно найти в папке manual/**Reader-Flash.pdf** или [тут](https://drive.google.com/file/d/1LpFkYJHQTQy2akt1_XCeqDz1JM2nfgtx/view?usp=sharing)
- Библиотеки копируются **с заменой** и именно из папки проекта
- Прошивка версии 1.1 собиралась на ядре ESP8266 **v3.1.2**
- Обновление прошивки можно произвести по воздуху через **веб-интерфейс**
- ESP в составе наших наборов **не требуют** прошивки

