# microReader v1.1
[Платы, компоненты и наборы](#parts)  
[Инструкция по сборке проекта](#assembly)  
[Компиляция проекта и прошивка ESP](#compile)    
[Режимы работы устройства](#mods)   
[Поддерживаемые файлы](#files)   
[Подготовка и вывод изображений](#images)   


## Обновление 1.1
- Обновлена [плата](https://oshwlab.com/nich1con/microreader)
- Добавлено отображение картинок в **.itxt / .h** [см. инструкцию](#images) 
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
Преимущества:
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
- Обновление прошивки можно произвести по воздуху через **web-интерфейс**
- ESP в составе наших наборов **не требуют** прошивки

## <a id="mods">Режимы работы устройства</a>
### Режим "Wi-Fi Меню"
- Позволяет конфигурировать и обновлять устройство, загружать и удалять файлы
- Активируется **удержанием** средней кнопки в главном меню
- Автоматически переходит в один из двух режимов сети	
	1. **Режим AP** (точка доступа) запускается по умолчанию или при невозможности подключения к сети,      	
	в режиме точки доступа устройство само создает сеть, к которой необходимо подключиться вручную  
	Название сети, пароль и локальный IP по которому необходимо перейти - выводятся на дисплей  
	2. **Режим STA** (подключение к сети) можно активировать из web-интерфейса, при включенном пункте "автоподключение" устройство 
	попытается подключиться к указанной сети  
	Название сети и назначенный локальный IP - выводятся на дисплей 
- Для перехода в **web-интерфейс** - введите указанный локальный IP в адресную строку браузера, на устройстве в **той же** сети!
- **После** подключения к сети или создания точки доступа можно изменить яркость дисплея кнопками "вверх" и "вниз"	
- Выход в главное меню по нажатию средней кнопки или по тайм-ауту в 5 минут	
### Игровой режим
- Активируется **удержанием** кнопки "вверх" в главном меню
- В версии прошивки 1.1 доступна только одна игра - **google dino**
- Выход в главное меню по нажатию кнопки "вверх" 
### Сервисный режим
- Активируется включением устройства с **зажатой** кнопкой "вверх" 
- Позволяет сбросить настройки устройства и сети к предустановленным
- Позволяет удалить все файлы из файловой системы

## <a id="files">Поддерживаемые файлы</a>
- На дисплей единовременно умещается до **8** строк текста по **21** символу!
- Для вывода текста используются файлы **.txt** в кодировке **UTF-8**
- Для отображения картинок используются файлы **.itxt** и **.h** содержащие **текст с массивом** (см. ниже)
- Файлы должны иметь короткие названия - **до 12 символов** на русском или английском языке  
- Файлы со слишком длинным названием или иным расширением **не будут** отображаться
- Образцы файлов можно найти в папке **test-files**

## <a id="images">Подготовка и вывод изображений</a>
### Особенности отображения картинок
- Дисплей монохромный и имеет разрешение 128х64 точки
- Изображения хранятся и парсятся в текстовом формате (в виде массива)
- Используемый формат файлов - **.itxt** и **.h**
- Для подготовки изображения используется **image-processor** из папки проекта
### Подготовка изображения
1. Запустите **imageProcessor.exe** (при необходимости потребуется установить или обновить java)
2. В левом нижнем углу утилиты установите соответствующие настройки вывода:
![IMGPC1](https://github.com/Nich1con/microReader/blob/main/manual/imgProcSettings.png)
3. Добавьте изображение через **OPEN IMAGE**
4. Настройте **размер** и **порог** до получения оптимального результата, изображение должно быть **черным на белом**: 
![IMGPC2](https://github.com/Nich1con/microReader/blob/main/manual/imgProc.png)
5. Сохраните файл нажав **SAVE**, в папке **image-processor** появится файл **.h** с примерно таким содержанием:
![IMGPC3](https://github.com/Nich1con/microReader/blob/main/manual/imgRes.png)
6. Переименуйте и загрузите файл на устройство
