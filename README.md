# CentralPark

## Загальний огляд
CentralPark є системою для користування парковками міста Львова. Користувачі мають змогу шукати та 
бронювати парковки, що їм найбільше підходять, або прокладати до них маршрут.

## Випадки використання

### Користувачі системи

*Іван* - водій великої вантажівки, йому треба привезти повний кузов важких вантажів, забрати будівельне сміття, тощо. Стати він хоче під саму точку.

*Марічка* - нещодавно стала водієм, живе на Сихові, та щодня їздить на роботу автівкою в центр. Машина стоїть під роботою весь день.

*Марк* - турист з Іспанії, українською не говорить, мандрує Україною на прокатному авті. Зупиняється максимум на 2 години.

*Назар* - водій зі стажем, не уявляє життя без своєї машини, і вважає, що дороги та парковки мають бути безкоштовними. Хитрить.

*Петро* - працівник дорожної служби, слідкує за правильністю паркування, звітує про порушників.

*Надія* - диспетчер дорожної служби, відповідає на дзвінки по гарячій лінії. Слідкує, щоб комп’ютер не начудив.


*Питання:*

* як знати, чи місце вільне?

* Як знати, чи стоянка саме цієї машини оплачена?

### Основні сценарії

- бронювання парковочного місця
- прокладання маршруту до парковки
- пошук підходящої парковки за знаходженням, ціною, наявністю
- повідомлення адміністраторів користувачами про відсутності парковки
- додавання адміном парковок

- бронювання парковочного місця

Користувач має можливість бронювати парковочне місце через платіжні системи.

- прокладання маршруту до парковки

В користувача є можливість прокласти маршрут до парковки, що йому підходить, за допомогою 
геолокаційних служб. 

- пошук підходящої парковки за знаходженням, ціною, наявністю

Користувачі мають змогу накладати фільтр на всі парковки щоб знайти найбільш підходящу за знаходженням,
ціною або наявністю в момент часу.

- повідомлення адміністраторів користувачами про відсутності парковки

В разі відсутності парковочного місця або інших умов користувач може повідомити адміністраторів для
того, щоб внести зміни в карту парковок. 

- зміна мапи парковок адміністратором

В адміністратора є можливість вносити зміни в мапу парковок або характеристик окремих парковок.


## Навантаження системи

За оцінками експертів станом на 2012 рік у м.Львові одночансо використовувалося близько
***150 000*** автомобілів (***200авт/1000осіб***) і згідно прогнозів їхня кількість
повинна зрости до 300 авто на 1000 осіб, тобто до ***300 000*** до 2025 року. 

Офіційно у Львові зареєстровано лише ***50 000*** паркомісць та гаражних приміщень.
Це буде створювати моменти критичного навантаження при пошуку вільних паркомісць у
певні періоди робочого дня. 

Основними годинами пікового навантаження на систему можна виділити насупні години: 

- ***7:20-7:55*** - час так званої "першої хвилі паркування", повязаної з початком робочого дня о 8 ранку;

- ***8:20-8:55*** - час перед почаком робочого дня з 9 години ранку;  

- ***9:30-14:30*** - час основної діяльності комерціїйної діяльності, а також руху транспорту, пов'язаного з обідньою перервою

Якщо припустити, що з усієї кількості автомобілів кожного дня використовуються близько 100 тис, то розрахунки навантаження можна зробити наступні: 

- 40 тис авто - парковка "першої хвилі"

- 60 тис авто - паркова на "другій хвилі"

Пікова навантаженість "першої хвилі" розраховується: 

---

* 1-ша хвиля:  40 000авто / 2 100сек = ***19 зап/сек***



* 2-га хвиля:  60 000авто / 2 100сек = ***29 зап/сек***



Середня навантаженість системи протягом робочого дня: 

---

* Робочий день: 50 000авто / 18 000 =  ***3 зап/сек***

## Інтеграція

Реєстрація користувачів виконується через соціальні мережі. Серед них Приват24 для оплати 
заброньованих парковочних місць, та Яндекс-карти для візуалізації знаходження парковок 
та обрахування маршруту.

##Offline
======================
Види паркомісць
---
Абсолютна більшість автомобілів більшу частину свого експлуатаційного періоду проводять на стоянка. <br>

У Львові місця постійного та тимчасового зберігання авто можна розділити наступним чино: 
1. Гаражні стоянки
2. Приватні парковки (з охороною)
3. Міця стихійних парковок (парковки на тротуарах, під будинками, вздовж вулиці що дозволені ПДР)
4. Місця тимчасових стихійних парковок з порушенням ПДР.

Дана система повинна мати можливість слідкувати за __другим__ і __третім__ типом парковок. <br>
Легкові автомобілі діляться за своїми габаритами на класи (A, B, C, D, E, S, G та ін.). Крім того у Львові велику популярність мають мінібуси, які своїми розмірами часто дорівнюють машинам класу D, E, S (до 5 м. довжини і більше). <br>
<br>
Паркування автомобілів ділиться на два типи: 
- **паралельне** (перепендикулярно до полоси руху)
- **поздовжнє** (паралельно полосі руху)

Кількість парковочних місць для паралельного паркування зазвичай є чітко визначеною. Довжина пакрвовочного місця є достатньою для більшості машин, що попадають в розсіри класу A-S. Проблеми виникають лише з великогабаритними авто (мінібуси, автобуси).  
Паралельне паркування здебільшого використовється на закритих парковках, парковках магазинів, супермаркетів, розважальних центрів. 
<br> Згідно ДСТУ довжина паркомісця для поздовньої парковки повинна становити 7.5 м. Проте, враховуючи тенденції до збільшення навантаженості парковок, у багатьох країнах стандартний розмір паркувальних місць зменшуються і становить всередньому 6.5 м. що є дуже актуальним для Львова. 
Такі парковки використовуються здебільшого у випадках тимчасового паркування вздовж вулиць та на тротуарах. Вони тяжко піддаються регламентації без нанесення спеціальної розмітки. Проте саме вони є доступними для автомобілів, що перевищують своїми габаритами стандартні розміри.
<br>
<br>
