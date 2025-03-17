# Чек лист ПАК
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background: #121212; color: #fff; font-family: Arial, sans-serif;
        }
        .button {
            padding: 10px 20px; background: #1f1f1f; color: #fff; border: 1px solid #fff; border-radius: 5px; cursor: pointer; margin: 20px 0;
        }
        .completed { color: #fff; background: none; border: 1px solid green; padding: 10px; }
        .error { color: red; background: none; border: 1px solid red; padding: 10px; }
        input[type="checkbox"] { display: none; }
        .custom-checkbox { display: inline-block; width: 24px; height: 24px; border: 2px solid #666; border-radius: 4px; background: #323232; margin-right: 10px; position: relative; }
        input[type="checkbox"]:checked + .custom-checkbox { background: #4caf50; }
        input[type="checkbox"]:checked + .custom-checkbox:after { content: "✔"; color: #fff; position: absolute; top: 0; left: 0; width: 24px; height: 24px; text-align: center; line-height: 24px; }
        .input-container { margin: 20px 0; border: 1px solid #fff; border-radius: 5px; }
        .input-container input { width: 100%; padding: 10px; background: #1f1f1f; color: #fff; border-radius: 5px; }
    </style>
</head>
<body>
    <h1>Первоначальная настройка Планшета/Телефона</h1>
    <ul id="checklist">
<li><label><input type="checkbox"> <span class="custom-checkbox"></span> Проверка обновления ONE UI на устройстве.</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Проверка включения тумблера "Определение даты и времени по геопозиции"</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Проверка работоспособности определения местоположения через приложение карт</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Проверка установлены ли приложения "MEDCONTROL", "Ассистент", "MEDCONTROL APP" на устройстве</label></li>
    </ul>

    <h1>Настройка Ассистента</h1>
    <ul id="checklist">
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Имеется ли у приложения Ассистент все необходимые разрешения</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Провести тестовое подключение к устройству и проверить исправность работы соединения</label></li>
    </ul>

    <h1>Настройка принтера</h1>
    <ul id="checklist">
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Переименован ли принтер под номер ПАК</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Включен ли Bluetooth у принтера</label></li>
    </ul>

    <h1>Внешний вид ПАК</h1>
    <ul id="checklist">
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Имеется ли люфт крепления камеры, порта для зарядки ПАК, подставки, СМК, планшета</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> На корпусе ПАК нет царапин и потертостей</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Плотное ли прилегание трубки манжеты к ПАК?</label></li>
    </ul>

    <h1>MEDCONTROL</h1>
    <ul id="checklist">
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Совпадает ли организация, к которой привязывается ПАК с заявкой?</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Правильно ли поставлена точка выпуска ПАК в АРМ</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Имеется ли разрешение у внешней камеры ПАК</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> На СМК стоит последняя версия прошивки</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> После прохождения тестового осмотра не возникло никаких происшествий, талон исправно напечатался</label></li>
    </ul>

    <h1>GLPI</h1>
    <ul id="checklist">
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Все данные устройства, принтера и телефона введены верно и без ошибок. Поставлена галочка "Подчиненные организации"</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> У комплекса поставлена верная организация, указанная в заявке, поставлена галочка "Можно связать с заявкой"</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> В объекты комплекса введены верные Устройство, принтер и телефон</label></li>
    </ul>
    <h1>Комплектность ПАК</h1>
    <ul id="checklist">
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span>В комплекте имются провода для зарядки ПАК и принтера</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span>В коробке принтера имеется мундштукидля измерения алкоголя в организме</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span>В коробке имеются все необходимые документы для ПАК</label></li>
    </ul>
    <h1>Отчет</h1>
    <ul id="checklist">
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span>Доложено ли начальнику производства что пак готов к отправке?</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> В заявке верно написаны номера ПАК и адрес отгрузки</label></li>
    </ul>
    <button class="button" id="submitButton">Готово</button>
    <div id="resultMessage" class="hidden"></div>

    <script>
        document.getElementById('submitButton').onclick = function () {
            const checkboxes = document.querySelectorAll('input[type="checkbox"]');
            const checked = [...checkboxes].filter(cb => cb.checked);
            const unchecked = [...checkboxes].filter(cb => !cb.checked).map(cb => cb.parentElement.textContent.trim());
            const resultMessage = document.getElementById('resultMessage');

            resultMessage.className = unchecked.length ? 'error' : 'completed';
            resultMessage.textContent = unchecked.length ? `❌ Не все выполнено: ${unchecked.join(", ")}` : "✅ Отправлено";
            document.getElementById('submitButton').style.display = unchecked.length ? 'inline-block' : 'none';
        };
    </script>
</body>
</html>
