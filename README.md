# Чек лист ПАК
<!DOCTYPE html>
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

        /* Стили для кастомного чекбокса */
        input[type="checkbox"] {
            display: none; /* Скрываем стандартные чекбоксы */
        }

        /* Стиль для кастомного элемента */
        .custom-checkbox {
            position: relative;
            display: inline-block;
            width: 24px;   /* Размер чекбокса */
            height: 24px;  /* Размер чекбокса */
            border: 2px solid #666; /* Граница чекбокса */
            border-radius: 4px; /* Закругление углов */
            margin-right: 10px; /* Отступ справа */
            cursor: pointer;
        }

        /* Стиль для состояния чекбокса */
        input[type="checkbox"]:checked + .custom-checkbox {
            background-color: green; /* Цвет при выборе */
            border-color: green; /* Цвет границы при выборе */
        }

        input[type="checkbox"]:checked + .custom-checkbox:after {
            content: "✔"; /* Символ галочки */
            color: white; /* Цвет галочки */
            position: absolute; 
            top: 0; 
            left: 0;
            width: 24px; 
            height: 24px; 
            text-align: center; 
            line-height: 24px; /* Центрирование галочки */
        }
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
