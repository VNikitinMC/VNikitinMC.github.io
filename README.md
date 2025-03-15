# Чек лист ПАК
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <style>
        .hidden {
            display: none;
        }

        .button {
            padding: 10px 20px;
            background-color: green;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
        }

        .completed {
            color: green;
            font-weight: bold;
        }

        .error {
            color: red;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Первоначальная настройка Планшета/Телефона</h1>
    <ul id="checklist">
        <li><input type="checkbox"> Проверка обновления ONE UI на устройстве.</li>
        <li><input type="checkbox"> Проверка включения тумблера "Определение даты и времени по геопозиции"</li>
        <li><input type="checkbox"> Проверка работоспособности определения местоположения через приложение карт</li>
        <li><input type="checkbox"> Проверка установлены ли приложения "MEDCONTROL", "Ассистент", "MEDCONTROL APP" на устройстве</li>
    </ul>

    <h1>Настройка Ассистента</h1>
    <ul id="checklist">
        <li><input type="checkbox"> Имеется ли у приложения Ассистент все необходимые разрешения</li>
        <li><input type="checkbox"> Провести тестовое подключение к устройству и проверить исправность работы соединения</li>
    </ul>

    <h1>Настройка принтера</h1>
    <ul id="checklist">
        <li><input type="checkbox"> Переименован ли принтер под номер ПАК</li>
        <li><input type="checkbox"> Включен ли Bluetooth у принтера</li>
    </ul>

    <h1>Внешний вид ПАК</h1>
    <ul id="checklist">
        <li><input type="checkbox"> Имеется ли люфт крепления камеры, порта для зарядки ПАК, подставки, СМК, планшета</li>
        <li><input type="checkbox"> На корпусе ПАК нет царапин и потертостей</li>
        <li><input type="checkbox"> Плотное ли прилегание трубки манжеты к ПАК?</li>
    </ul>

    <h1>MEDCONTROL</h1>
    <ul id="checklist">
        <li><input type="checkbox"> Совпадает ли организация, к которой привязывается ПАК с заявкой?</li>
        <li><input type="checkbox"> Правильно ли поставлена точка выпуска ПАК в АРМ</li>
        <li><input type="checkbox"> Имеется ли разрешение у внешней камеры ПАК</li>
        <li><input type="checkbox"> На СМК стоит последняя версия прошивки</li>
        <li><input type="checkbox"> После прохождения тестового осмотра не возникло никаких происшествий, талон исправно напечатался</li>
    </ul>

    <h1>GLPI</h1>
    <ul id="checklist">
        <li><input type="checkbox"> Все данные устройства, принтера и телефона введены верно и без ошибок. Поставлена галочка "Подчиненные организации"</li>
        <li><input type="checkbox"> У комплекса поставлена верная организация, указанная в заявке, поставлена галочка "Можно связать с заявкой"</li>
        <li><input type="checkbox"> В объекты комплекса введены верные Устройство, принтер и телефон</li>
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
                document.getElementById('submitButton').style.display = 'none'; // скрываем кнопку после отправки
            } else {
                resultMessage.classList.remove('hidden');
                resultMessage.classList.add('error');
                resultMessage.textContent = "❌ Не все выполнено: " + notCheckedItems.join(", ");
                document.getElementById('submitButton').style.display = 'none'; // скрываем кнопку после проверки
            }
        }
    </script>
</body>
</html>
