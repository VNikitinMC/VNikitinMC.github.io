# CHECKLIST


   <html lang="ru">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <link rel="stylesheet" href="styles.css">
   </head>
   <body>
       <h1>Первоначальная настройка Планшета/Телефона</h1>
       <ul id="checklist">
           <li><input type="checkbox"> Проверка обновления ONE UI на устройстве.</li>
           <li><input type="checkbox"> Проверка включения тумблера"Определение даты и времени по геопозиции"</li>
           <li><input type="checkbox"> Проверка работоспособности определения местоположения через приложение карт </li>
           <li><input type="checkbox"> Проверка установлены ли приложения "MEDCONTROL","Ассистент","MEDCONTROL APP" на устройстве</li>
       </ul>
   </body>
   </html>

<!DOCTYPE html>
   <html lang="ru">
   <head>
       <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <link rel="stylesheet" href="styles.css">
   </head>
   <body>
       <h1>Настройка Ассистента</h1>
       <ul id="checklist">
           <li><input type="checkbox"> Имеется ли у приложения Ассистент все необходимые разрешения</li>
           <li><input type="checkbox"> Провести тестовое подключение к устройству и проверить исправность работы соединения</li>
       </ul>
   </body>
    <h1>Настройка принтера</h1>
       <ul id="checklist">
           <li><input type="checkbox">Переименован ли принтер под номер ПАК</li>
           <li><input type="checkbox">Включен ли Bluetooth у принтера</li>
       </ul>
   </body>
   <h1>Внешний вид ПАК</h1>
       <ul id="checklist">
           <li><input type="checkbox">Имеется ли люфт крепления камеры, порта для зарядки ПАК, подставки, СМК, планшета</li>
           <li><input type="checkbox">На корпусе ПАК нет царапин и потертостей </li>
            <li><input type="checkbox">Плотное ли прилегание трубки манжеты к ПАК?</li>
       </ul>
   </body>
   <h1>MEDCONTROL</h1>
       <ul id="checklist">
           <li><input type="checkbox">Совпадает ли организация к которой привязывается Пак с заявкой? </li>
           <li><input type="checkbox">Правильно ли поставлена точка выпуска ПАК в АРМ</li>
           <li><input type="checkbox">Имеется ли разрешение у внешней камеры ПАК</li>
    <li><input type="checkbox">На СМК стоит последняя версия прошивки</li>
            <li><input type="checkbox">После прохождения тестового осмотра не возникло никаких проишествий, талон исправно напечатался</li>
       </ul>
   </body>
   <h1>GLPI</h1>
       <ul id="checklist">
           <li><input type="checkbox">Все данные устройства, принтера и телефона введены верно и без ошибок. Поставлена галочка "Подчененные организации" </li>
           <li><input type="checkbox">У комплекса поставлена верная организация которая указана в заявке, поставлена галочка "Можно связать с заявкой"</li>
           <li><input type="checkbox">В объекты комплекса введены верное Устройство, принтер и телефон</li>
       </ul>
   </body>
  
          
   const checklistItems = document.querySelectorAll('#checklist input[type="checkbox"]');
   checklistItems.forEach(item => {
       item.addEventListener('change', () => {
           if (item.checked) {
               console.log(`${item.parentElement.textContent} 
