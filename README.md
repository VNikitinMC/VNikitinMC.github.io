# Чек лист ПАК
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background-color: #121212;
            color: #ffffff;
            font-family: Arial, sans-serif;
        }
        .hidden {
            display: none;
        }
        .button {
            padding: 10px 20px;
            background-color: #1f1f1f;
            color: #ffffff;
            border: 1px solid #ffffff;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 0.3s, border 0.3s;
        }
        .button:hover {
            background-color: #444444;
        }
        .completed {
            color: #ffffff;
            font-weight: bold;
            background-color: #121212; /* Цвет совпадает с фоном */
            border: 1px solid red; /* Тонкая красная рамка */
            padding: 10px;
            border-radius: 5px;
            margin-top: 20px;
        }
        .error {
            color: red;
            font-weight: bold;
            background-color: #121212; /* Цвет совпадает с фоном */
            border: 1px solid red; /* Тонкая красная рамка */
            padding: 10px;
            border-radius: 5px;
            margin-top: 20px;
        }
        input[type="checkbox"] {
            display: none;
        }
        .custom-checkbox {
            position: relative;
            display: inline-block;
            width: 24px;
            height: 24px;
            border: 2px solid #666;
            border-radius: 4px;
            margin-right: 10px;
            background-color: #323232;
            transition: background-color 0.3s, border 0.3s;
        }
        input[type="checkbox"]:checked + .custom-checkbox {
            background-color: #4caf50;
            border-color: #4caf50;
        }
        input[type="checkbox"]:checked + .custom-checkbox:after {
            content: "✔";
            color: #ffffff;
            position: absolute;
            top: 0;
            left: 0;
            width: 24px;
            height: 24px;
            text-align: center;
            line-height: 24px;
        }
        #resultMessage {
            margin-top: 20px;
        } 
        .logo {
            width: 200px;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <img src="logo.png" alt="Логотип MedControl" class="logo">
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
            let checkboxes = document.querySelectorAll('input[type="checkbox"]');
            let totalCheckboxes = checkboxes.length;
            let checkedCheckboxes = 0;
            let notCheckedItems = [];

            checkboxes.forEach(checkbox => {
                if (checkbox.checked) {
                    checkedCheckboxes++;
                } else {
                    notCheckedItems.push(checkbox.parentElement.textContent.trim());
                }
            });

            const resultMessage = document.getElementById('resultMessage');

            if (checkedCheckboxes === totalCheckboxes) {
                resultMessage.classList.remove('hidden');
                resultMessage.classList.add('completed');
                resultMessage.textContent = "✅ Отправлено";
                document.getElementById('submitButton').style.display = 'none';
            } else {
                resultMessage.classList.remove('hidden');
                resultMessage.classList.add('error');
                resultMessage.textContent = "❌ Не все выполнено: " + notCheckedItems.join(", ");
                document.getElementById('submitButton').style.display = 'inline-block';
            }
        }
    </script>
</body>
</html>
