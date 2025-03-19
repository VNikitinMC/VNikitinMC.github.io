# Чек лист ПАК
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background: #121212; color: #fff; font-family: Arial, sans-serif; position: relative;
        }
        .button {
            padding: 10px 20px; background: #1f1f1f; color: #fff; border: 1px solid #fff; border-radius: 5px; cursor: pointer; margin: 20px 0;
        }
.button:hover {
    background: #4caf50; 
    border: 1px solid #4caf50; 
}
        .completed { color: #fff; background: none; border: 1px solid green; padding: 10px; }
        .error { color: red; background: none; border: 1px solid red; padding: 10px; }
        input[type="checkbox"] { display: none; }
        .custom-checkbox { display: inline-block; width: 24px; height: 24px; border: 2px solid #666; border-radius: 4px; background: #323232; margin-right: 10px; position: relative; }
        input[type="checkbox"]:checked + .custom-checkbox { background: #4caf50; }
        input[type="checkbox"]:checked + .custom-checkbox:after { content: "✔"; color: #fff; position: absolute; top: 0; left: 0; width: 24px; height: 24px; text-align: center; line-height: 24px; }
        .input-container { margin: 20px 0; border: 1px solid #fff; border-radius: 5px; }
        .input-container input { width: 100%; padding: 10px; background: #1f1f1f; color: #fff; border-radius: 5px; }
             #resultMessage {
            opacity: 0;
            transform: translateY(-10px);
            transition: opacity 0.5s ease, transform 0.5s ease;
            visibility: hidden;
            margin-top: 20px; 
        }
        #resultMessage.visible {
            opacity: 1;
            transform: translateY(0);
            visibility: visible;
        }

.corner-image { 
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 200px;
            height: auto;     
        }
<body>

    </style>
</head>
<body>
<div class="input-container">
    <input type="text" id="input1" placeholder="Номер ПАК/СМК">
</div>
<div class="input-container">
    <input type="text" id="input2" placeholder="Номер осмотра">   
</div>
<div class="input-container">
    <input type="text" id="input3" placeholder="Ссылка на комплекс в GLPI">
</div>
<div class="input-container">
    <input type="text" id="input4" placeholder="Номер пломбы наклейки">
</div>
    <h1>GLPI</h1>
    <ul id="checklist">
<li><label><input type="checkbox"> <span class="custom-checkbox"></span> Все данные введены верно, выбор подчиненных организаций</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Верная организация в заявке и связь с ней</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Верные объекты комплекса</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Указан ли конечный пользователь? Если нет, то поставил на головную организацию</label></li>
</ul>
   <h1>Внешний вид ПАК</h1>
<ul>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Люфт крепления камеры, порта и других деталей</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> На корпусе нет царапин и потертостей</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Плотное ли прилегание манжеты к ПАК?</label></li>
</ul>
<h1>Первоначальная настройка Планшета/Телефона</h1>
<li><label><input type="checkbox"> <span class="custom-checkbox"></span> Проверка обновления ONE UI на устройстве.</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Проверка включения тумблера "Определение даты и времени по геопозиции"</label></li>
        <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Проверка работоспособности определения местоположения через приложение карт</label></li>
    <h1>Настройка Ассистента</h1>
<ul id="checklist">
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Имеются ли у приложения Ассистент все необходимые разрешения</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Провести тестовое подключение к устройству и проверить исправность работы соединения</label></li>
</ul>
<h1>Настройка принтера</h1>
<ul>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Переименован ли принтер под номер ПАК</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Включен ли Bluetooth у принтера</label></li>
</ul>
<h1>MEDCONTROL</h1>
<ul>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Совпадает ли организация с заявкой?</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Правильная ли точка выпуска ПАК в АРМ?</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Имеется ли разрешение у внешней камеры ПАК?</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> На СМК стоит эталонная версия прошивки и совпадает с АРМ?</label></li>
</ul>
<h1>Комплектность ПАК</h1>
<ul>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Провода для зарядки ПАК и принтера</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Мундштук для измерения алкоголя</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Все необходимые документы для ПАК</label></li>
</ul>
<h1>Мониторинг</h1>
<ul>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Тестовый осмотр пройден без проишествий </label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Талончик на принтере напечатан верно, не оторван и остался в коробке</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Тестовый осмотр проверен через АРМ: работоспособность камер, звука и медицинского оборудования</label></li>   
</ul> 
<h1>Отчет</h1>
<ul>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Доложено ли начальнику производства о готовности пак к отправке?</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span> Верно ли указаны номера ПАК и адрес отгрузки?</label></li>
    <li><label><input type="checkbox"> <span class="custom-checkbox"></span>Имеется ли промбирующая наклейка на линии среза коробки ПАК?</label></li>
</ul> 
 <button class="button" id="submitButton">Готово</button>
    <div id="resultMessage" class="hidden"></div>

    <script>
        document.getElementById('input2').addEventListener('focus', function() {
            if (this.value === '') { // Проверка, если поле пустое
                this.value = '№';
            }
        });

        document.getElementById('submitButton').onclick = () => {
            const checkboxes = [...document.querySelectorAll('input[type="checkbox"]')];
            const unchecked = checkboxes.filter(cb => !cb.checked).map(cb => cb.parentElement.textContent.trim());

            const value1 = document.getElementById('input1').value;
            const value2 = document.getElementById('input2').value;
            const value3 = document.getElementById('input3').value;
            const value4 = document.getElementById('input4').value;

            const emptyFields = [];
            const inputs = [value1, value2, value3, value4];
            const inputElements = [document.getElementById('input1'), document.getElementById('input2'), document.getElementById('input3'), document.getElementById('input4')];

            inputs.forEach((val, index) => {
                if (!val.trim()) {
                    emptyFields.push(`Поле "${inputElements[index].placeholder}" не заполнено.`);
                    inputElements[index].parentElement.style.border = '1px solid red';
                } else {
                    inputElements[index].parentElement.style.border = '1px solid #fff';
                }
            });

            const resultMessage = document.getElementById('resultMessage');
            if (emptyFields.length || unchecked.length) {
                resultMessage.className = 'error';
                resultMessage.innerHTML = emptyFields.join("<br>") + (unchecked.length ? `<br>❌ Не все выполнено: ${unchecked.join(", ")}` : '');
            } else {
                resultMessage.className = 'completed';
                resultMessage.innerHTML = `✅ Отправлено. Номер ПАК/СМК: ${value1}, Номер пломбы наклейки: ${value4}, Номер осмотра: ${value2}, Ссылка на комплекс в GLPI: <a href="${value3}" target="_blank" style="color: #4caf50;">${value3}</a>`;
            }
            resultMessage.classList.add('visible');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        };
    </script>
</body>
</html>
